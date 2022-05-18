---

title: Indexing queue explainer
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Git Integration for Jira (GIJ) Data Center (DC) and Server 4.0 introduces a new reindexing queue based on using the Jira database. This article provides in-depth details about this queue implementation that may be helpful for Jira administrators.

### GIJ architecture

Every connected repository (except local ones and those using the "[Tracked folder](/git-integration-for-jira-self-managed/Tracked-Folders)" feature) is cloned to a sub-folder in the `data/git-plugin` folder inside the shared Jira home.

This cloned repository copy is used for 2 purposes:

1.  The Jira DC nodes scan it and create local Lucene indexes to retrieve commit information quickly.

2.  The "[View file](/git-integration-for-jira-self-managed/Repository-Browser)", "[View diff](/wiki/spaces/GIJDC/pages/1930398768/Viewing+commit+code+diffs)", and "[Compare](/wiki/spaces/GIJDC/pages/1930398705)" features read files data directly from that cloned copy of the repository.


### Indexing process

Integrations are connections to a git service like GitHub, GitLab, etc. Integration indexing consists of the following steps:

1.  The Git server is scanned to retrieve the current list of sub-repositories (repositories inside the integration) based on the Git server credentials provided.

2.  The retrieved list of sub-repositories is compared with the persisted sub-repository list stored in the GIJ plugin.

3.  The persisted sub-repositories that do not exist in the current list retrieved from the Git server are scheduled to be removed.

4.  The new sub-repositories are created and cloned to sub-folders in the `data/git-plugin` folder inside the shared Jira home.

5.  Existing and new sub-repositories are scheduled to be reindexed; integration is indexing -- it may add sub-repositories to the indexing queue in any order, which will be processed at a much later time.


Individual repository indexing consists of the following steps:

1.  The repository-related merge/pull requests are retrieved from the Git server and stored in the database.

2.  The cloned copy of the repository is updated from the Git server with the latest data.

3.  The local Lucene indexes are updated on all Jira nodes.


The local Lucene index update scans all branches and traverses all commits in them. There are a couple of optimizations to avoid all branches scanning every time:

A. New branches are scanned starting from the base branch (usually the 'master' or 'main' branch).

B. The existing branches are scanned from the last branch commit (if it still exists) stored during the previous indexing.

The initial indexing of large repositories can take several hours. Subsequent indexing of repositories is generally very fast (seconds). The amount of time required for indexing depends on the number of branches and commits in the repository.

The "Reset index" functionality (![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Reset index**) is used to re-create or repair the repository Lucene index and causes the GIJ plugin to re-read all commits from all repository branches (like the initial indexing does).

### Reindexing queue: Operations

The reindexing queue is used to perform the following operations on repositories:

*   Repository reindexing.

*   Git Garbage Collection (GC).

*   Repository removal.


Git GC is called only on a scheduled basis (please see the "[Garbage collection and Revision validation checkers](/wiki/spaces/GIJDC/pages/1207828777/Repositories+garbage+collection+checker)" option in the plugin "[General settings](/git-integration-for-jira-self-managed/General-Settings)").

The repository removal operation may be called either manually by a Jira administrator through the "[Remove repository"/"Remove integration](/wiki/spaces/GIJDC/pages/1930397738/Removing+integration+or+repository+configuration)" context menu, through [the REST API](/wiki/spaces/GIJDC/pages/380797296/Delete+Existing+Repository), or by the "[Bulk import](/wiki/spaces/GIJDC/pages/1930397888/Import+existing+repositories+via+Bulk+change)" feature. Also, when some repositories are no longer available on the Git server, they are automatically scheduled for removal during integrations scanning.

The repository reindexing operations are initiated in the following cases:

*   A scheduled reindexing (please see the "[Repository reindexing](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1207795958/Scheduled+jobs#Repository-reindexing)" option in the plugin "General settings" and [this article about Scheduled Jobs](/git-integration-for-jira-self-managed/Scheduling-Jobs) for more details).

*   A webhook-based reindexing (please see [Webhooks](/git-integration-for-jira-self-managed/Webhooks) for more details).

*   A manually called reindexing through the "[Reindex repository"/"Reindex integration"/"Reset index](/wiki/spaces/GIJDC/pages/1930397476/Managing+integration+via+Actions)" context menu items, or the "[Reindex all](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930396951/Git+integration+configuration+page#Reindex-all)" button.

*   An automatic repository reindexing after the branch or merge/pull request creation/deletion.

*   An automatic repository reindexing after the ["Bulk import"](/wiki/spaces/GIJDC/pages/1930397888/Import+existing+repositories+via+Bulk+change).

*   A reindex triggered by REST API calls (please see [Reindex API](/git-integration-for-jira-self-managed/Reindex-API) for more details).


### Reindexing queue: Priorities

Tasks from the indexing queue are taken based on the following criteria:

1.  TimeToStart is less than the current time.

2.  The repository is not being processed by any other node/thread yet.

3.  Priority (high priority first).

4.  Insertion time (oldest records first).

5.  Repository ID.


### Reindexing queue: Technical details

1.  The reindexing queue is located in the Jira database. This allows queue reading/writing from any node in the cluster. As a result, any node may display the indexing status for any repository regardless of the node on which it is currently processed.

2.  In addition, this shared queue is processed by all nodes in the cluster in parallel, which improves indexing performance.

3.  Since GIJ 4.0 the initial integration scanning is performed in a separate thread and does not depend on other reindexing operations.

4.  All operations with the queue (putting & getting) are performed under a Cluster Lock provided by the Atlassian Jira library.

5.  There is one thread per Data Center node that processes the queued tasks.

6.  There is a separate thread per Data Center node that performs Lucene indexing on a node.


### Reindexing queue: Database tables

**ReindexQueue** -- This table refers to the indexing queue items. It contains queued tasks, currently indexing ones, and the completed ones. Thus, this table may be used to get the current repository indexing status. For example:

*   is it queued?

*   is it actively indexing?

*   is it successfully/unsuccessfully indexed?


When a new indexing cycle is started for a repository -- all existing entries older than 1 hour are removed for that repository.

**ReindexQueueLog** -- This table refers to the indexing log data. It contains the current indexing state and log messages if any.

**ReindexLock** -- This table refers to the locked repositories. The lock is set when the repository is being processed and then cleared on completion. On the plugin \[re-\]start, all locks are cleared to ensure that locks are released properly.

### Reindexing queue: Task parameters

*   **OperationType**. The code of the operation to be performed on the specified repository.


1 -- Reindexing.
2 -- Git GC.
3 -- Remove repository.

*   **ReindexSource**. The source of the operation. The same sources are used in the [Audit log](/wiki/spaces/GIJDC/pages/1207828866/Audit+log+settings) records.


INITIAL\_REINDEX
MANUAL
BRANCH\_OPERATION
ON\_RESET\_REPOSITORY
PERIODIC\_JOB
PULL\_REQUEST\_OPERATION
COMMIT\_OPERATION
REPOSITORY\_UPDATE
WEB\_HOOK

*   **Priority**. The priority of the operation. Tasks in the queue are executed in descending order of priority. GIJ plugin internally uses the following priorities for operations:


24 -- Manual reindex.
22 -- Webhook reindex.
20 -- Scheduled reindex.
10 -- Remove repository.
2 -- Git GC.

When a sub-repository (a repository inside an integration) is pushed into the queue - it gets the priority of the base (i.e. – integration) request +1.

*   **TimeToStart**. The “Unix time” for the operation start. The operation will be executed no earlier than the specified time. This is used by the "[Webhook sleeping](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930399378/Integration+webhooks#Advanced-settings)" feature.


### "Task skipping" feature

The "Task skipping" feature guarantees that each operation for every repository will be queued only once. This prevents queue flooding if the incoming indexing requests arrive too often to be processed in time.

When a task is queued, GIJ looks for that type of task and repository ID in the queue. If there is no such task in the queue -- the new task is simply placed in the queue.

But in the case when there is a similar task (i.e. that has the same repository ID and code of the operation) in the queue, the plugin behavior is more complex -- it combines and stores the data from the incoming and the existing tasks:

*   The highest "Priority" is used.

*   The nearest "TimeToStart" is used.


Such behavior allows raising the task priority or removing the task delay. This is applicable for queued scheduled or webhook tasks when a user calls the same repository reindexing manually.

As a result, if a repository is queued, it doesn’t matter how the re-indexing request arrived in the queue – manual reindex, scheduled reindex, webhook reindex, REST API request reindex – only one entry for the repository will be stored in the queue.

### "Webhook sleeping" feature

When webhooks are used, it is possible that some large and frequently used repository fills the queue with the webhook reindexing requests. As a result, other scheduled reindexing or maintenance tasks will be unable to run due to being pushed to low priority. In that case, the "Webhook sleeping" feature helps.

If the "[Min repository reindex interval](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930399378/Integration+webhooks#Advanced-settings)" is set to a value greater than 0 (zero) minutes, then on webhook arrival, the "TimeToStart" field for the queued task is set to the "Last indexing time" for the repository plus the specified sleeping interval.

If the repository is indexing right now -- the "TimeToStart" field for the queued task is set to the current time plus the specified sleeping interval.

This feature is used only for webhooks. The scheduled and manual (including the ones made through REST API) reindexing requests are unaffected by this feature and always have "TimeToStart" equal to 0, i.e. run immediately without any delay.

This feature gives Jira administrators more control, especially on Jira instances with large numbers of busy repositories where they’re likely managing rate limiting issues.

### Logging

When troubleshooting indexing issues it may be useful to [enable the logging](/wiki/spaces/GIJDC/pages/2038792196) for the following packages:

*   Queue operations - DEBUG for `com.bigbrassband.jira.git.ao.dao.ReindexQueueDaoImpl`.

*   Indexing task - INFO/DEBUG for `com.bigbrassband.jira.git.services.async.ReindexQueueReindexTask`.

*   Main/local node indexing - INFO/DEBUG for `com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl`.

*   Git GC task - INFO/DEBUG for `com.bigbrassband.jira.git.services.async.ReindexQueueGCTask`.

*   Repository removing - INFO/DEBUG for `com.bigbrassband.jira.git.services.gitmanager.visitors.RemoveVisitor`.


## ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Related articles

*   Page:

    [The git notes are still not visible in Jira. What should I do?](/wiki/spaces/GIJDC/pages/2054225956)

*   Page:

    [Is there a URL I can call to trigger fetch and re-index? Would be nice to add as service hook to GitHub/Gitlab.](/wiki/spaces/GIJDC/pages/2053832750)

*   Page:

    [Is it possible to track the specified branches when reindexing?](/wiki/spaces/GIJDC/pages/2053406744)

*   Page:

    [How do I clear the Git Integration for Jira app cache manually?](/wiki/spaces/GIJDC/pages/2053406737)

*   Page:

    [How do I completely rebuild plugin indexes?](/wiki/spaces/GIJDC/pages/2053734434)

*   Page:

    [Commits are not showing right away. Can they show up faster?](/wiki/spaces/GIJDC/pages/2053570566)

*   Page:

    [Is there any way to control the reindex?](/wiki/spaces/GIJDC/pages/2053275662)

*   Page:

    [What does re-index do?](/wiki/spaces/GIJDC/pages/2054291457)

*   Page:

    [Indexing queue explainer](/wiki/spaces/GIJDC/pages/2047902017/Indexing+queue+explainer)

*   Page:

    [Reindexing](/git-integration-for-jira-self-managed/Reindexing)

*   Page:

    [Reindex POST API](/wiki/spaces/GIJDC/pages/380666409/Reindex+POST+API)

*   Page:

    [Webhooks](/git-integration-for-jira-self-managed/Webhooks)

*   Page:

    [Hooks and Webhooks](/wiki/spaces/GIJDC/pages/94208056/Hooks+and+Webhooks)

*   Page:

    [Reindex and cache](/wiki/spaces/GIJDC/pages/92209341/Reindex+and+cache)