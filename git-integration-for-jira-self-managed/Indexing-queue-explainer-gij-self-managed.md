---

title: Indexing queue explainer - Administration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- ADMINISTRATION -->

Git Integration for Jira (GIJ) Data Center (DC) and Server v4.0 introduces a new reindexing queue based on using the Jira database. This article provides in-depth details about this queue implementation that may be helpful for Jira administrators.

## GIJ architecture

Every connected repository (except local ones and those using the "[Tracked folder](/git-integration-for-jira-data-center/tracked-folders-gij-self-managed)" feature) is cloned to a sub-folder in the `data/git-plugin` folder inside the shared Jira home.

This cloned repository copy is used for 2 purposes:

1.  The Jira DC nodes scan it and create local Lucene indexes to retrieve commit information quickly.

2.  The "[View file](/git-integration-for-jira-data-center/repository-browser-gij-self-managed)", "[View diff](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed)", and "[Compare](/git-integration-for-jira-data-center/comparing-branches-tags-in-repository-browser-gij-self-managed)" features read files data directly from that cloned copy of the repository.


## Indexing process

Integrations are connections to a git service like GitHub, GitLab, etc. Integration indexing consists of the following steps:

1.  The Git server is scanned to retrieve the current list of sub-repositories (repositories inside the integration) based on the Git server credentials provided.

2.  The retrieved list of sub-repositories is compared with the persisted sub-repository list stored in the GIJ plugin.

3.  The persisted sub-repositories that do not exist in the current list retrieved from the Git server are scheduled to be removed.

4.  The new sub-repositories are created and cloned to sub-folders in the `data/git-plugin` folder inside the shared Jira home.

5.  Existing and new sub-repositories are scheduled to be reindexed; integration is indexing -- it may add sub-repositories to the indexing queue in any order, which will be processed at a much later time.

<br>

Individual repository indexing consists of the following steps:

1.  The repository-related merge/pull requests are retrieved from the Git server and stored in the database.

2.  The cloned copy of the repository is updated from the Git server with the latest data.

3.  The local Lucene indexes are updated on all Jira nodes.


The local Lucene index update scans all branches and traverses all commits in them. There are a couple of optimizations to avoid all branches scanning every time:

*   New branches are scanned starting from the base branch (usually the 'master' or 'main' branch).

*   The existing branches are scanned from the last branch commit (if it still exists) stored during the previous indexing.

The initial indexing of large repositories can take several hours. Subsequent indexing of repositories is generally very fast (seconds). The amount of time required for indexing depends on the number of branches and commits in the repository.

The "Reset index" functionality (<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Reset index**) is used to re-create or repair the repository Lucene index and causes the GIJ plugin to re-read all commits from all repository branches (like the initial indexing does).

## Reindexing queue: Operations

The reindexing queue is used to perform the following operations on repositories:

*   Repository reindexing.

*   Git Garbage Collection (GC).

*   Repository removal.


Git GC is called only on a scheduled basis (please see the "[Garbage collection and Revision validation checkers](/git-integration-for-jira-data-center/repositories-garbage-collection-checker-gij-self-managed)" option in the plugin "[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)").

The repository removal operation may be called either manually by a Jira administrator through the "[Remove repository"/"Remove integration](/git-integration-for-jira-data-center/removing-integration-or-repository-configuration-gij-self-managed)" context menu, through [the REST API](/git-integration-for-jira-data-center/rest-api-gij-self-managed), or by the "[Bulk import](/git-integration-for-jira-data-center/import-new-repositories-via-bulk-change-gij-self-managed)" feature. Also, when some repositories are no longer available on the Git server, they are automatically scheduled for removal during integrations scanning.

The repository reindexing operations are initiated in the following cases:

*   A scheduled reindexing (please see the "[Repository reindexing](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed#Repository-reindexing)" option in the plugin "General settings" and [this article about Scheduled Jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed) for more details).

*   A webhook-based reindexing (please see [Webhooks](/git-integration-for-jira-data-center/webhooks-gij-self-managed) for more details).

*   A manually called reindexing through the "[Reindex repository"/"Reindex integration"/"Reset index](/git-integration-for-jira-data-center/managing-integration-via-actions-gij-self-managed)" context menu items, or the "[Reindex all](/git-integration-for-jira-data-center/git-integration-configuration-page-gij-self-managed)" button.

*   An automatic repository reindexing after the branch or merge/pull request creation/deletion.

*   An automatic repository reindexing after the ["Bulk import"](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed).

*   A reindex triggered by REST API calls (please see [Reindex API](/git-integration-for-jira-data-center/reindex-api-gij-self-managed) for more details).

## Reindexing queue: Priorities

Tasks from the indexing queue are taken based on the following criteria:

1.  TimeToStart is less than the current time.

2.  The repository is not being processed by any other node/thread yet.

3.  Priority (high priority first).

4.  Insertion time (oldest records first).

5.  Repository ID.

## Reindexing queue: Technical details

1.  The reindexing queue is located in the Jira database. This allows queue reading/writing from any node in the cluster. As a result, any node may display the indexing status for any repository regardless of the node on which it is currently processed.

2.  In addition, this shared queue is processed by all nodes in the cluster in parallel, which improves indexing performance.

3.  Since Git Integration for Jira v4.0, the initial integration scanning is performed in a separate thread and does not depend on other reindexing operations.

4.  All operations with the queue (putting & getting) are performed under a Cluster Lock provided by the Atlassian Jira library.

5.  There is one thread per Data Center node that processes the queued tasks.

6.  There is a separate thread per Data Center node that performs Lucene indexing on a node.

## Reindexing queue: Database tables

**ReindexQueue** -- This table refers to the indexing queue items. It contains queued tasks, currently indexing ones, and the completed ones. Thus, this table may be used to get the current repository indexing status. For example:

*   is it queued?

*   is it actively indexing?

*   is it successfully/unsuccessfully indexed?

When a new indexing cycle is started for a repository -- all existing entries older than 1 hour are removed for that repository.

**ReindexQueueLog** -- This table refers to the indexing log data. It contains the current indexing state and log messages if any.

**ReindexLock** -- This table refers to the locked repositories. The lock is set when the repository is being processed and then cleared on completion. On the plugin \[re-\]start, all locks are cleared to ensure that locks are released properly.

## Reindexing queue: Task parameters

*   **OperationType**. The code of the operation to be performed on the specified repository.

1 -- Reindexing.
2 -- Git GC.
3 -- Remove repository.

*   **ReindexSource**. The source of the operation. The same sources are used in the [Audit log](/git-integration-for-jira-data-center/audit-log-settings-gij-self-managed) records.

INITIAL\_REINDEX<br>
MANUAL<br>
BRANCH\_OPERATION<br>
ON\_RESET\_REPOSITORY<br>
PERIODIC\_JOB<br>
PULL\_REQUEST\_OPERATION<br>
COMMIT\_OPERATION<br>
REPOSITORY\_UPDATE<br>
WEB\_HOOK<br>
TAGS\_CALCULATION<br>

*   **Priority**. The priority of the operation. Tasks in the queue are executed in descending order of priority. GIJ plugin internally uses the following priorities for operations:

24 -- Manual reindex.
22 -- Webhook reindex.
20 -- Scheduled reindex.
10 -- Remove repository.
2 -- Git GC.

When a sub-repository (a repository inside an integration) is pushed into the queue - it gets the priority of the base (i.e. – integration) request +1.

*   **TimeToStart**. The “Unix time” for the operation start. The operation will be executed no earlier than the specified time. This is used by the "[Webhook sleeping](/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed#advanced-settings)" feature.

## "Task skipping" feature

The "Task skipping" feature guarantees that each operation for every repository will be queued only once. This prevents queue flooding if the incoming indexing requests arrive too often to be processed in time.

When a task is queued, GIJ looks for that type of task and repository ID in the queue. If there is no such task in the queue -- the new task is simply placed in the queue.

But in the case when there is a similar task (i.e. that has the same repository ID and code of the operation) in the queue, the plugin behavior is more complex -- it combines and stores the data from the incoming and the existing tasks:

*   The highest "Priority" is used.

*   The nearest "TimeToStart" is used.

Such behavior allows raising the task priority or removing the task delay. This is applicable for queued scheduled or webhook tasks when a user calls the same repository reindexing manually.

As a result, if a repository is queued, it doesn’t matter how the re-indexing request arrived in the queue – manual reindex, scheduled reindex, webhook reindex, REST API request reindex – only one entry for the repository will be stored in the queue.

## "Webhook sleeping" feature

When webhooks are used, it is possible that some large and frequently used repository fills the queue with the webhook reindexing requests. As a result, other scheduled reindexing or maintenance tasks will be unable to run due to being pushed to low priority. In that case, the "Webhook sleeping" feature helps.

If the "[Min repository reindex interval](/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed#Advanced-settings)" is set to a value greater than 0 (zero) minutes, then on webhook arrival, the "TimeToStart" field for the queued task is set to the "Last indexing time" for the repository plus the specified sleeping interval.

If the repository is indexing right now -- the "TimeToStart" field for the queued task is set to the current time plus the specified sleeping interval.

This feature is used only for webhooks. The scheduled and manual (including the ones made through REST API) reindexing requests are unaffected by this feature and always have "TimeToStart" equal to 0, i.e. run immediately without any delay.

This feature gives Jira administrators more control, especially on Jira instances with large numbers of busy repositories where they’re likely managing rate limiting issues.

## Logging

When troubleshooting indexing issues it may be useful to [enable the logging](/git-integration-for-jira-data-center/faq-logging-gij-self-managed#how-do-i-enable-debug-logging-level-for-git-integration-for-jira-app) for the following packages:

*   Queue operations - DEBUG for <br>`com.bigbrassband.jira.git.ao.dao.ReindexQueueDaoImpl`.

*   Indexing task - INFO/DEBUG for <br>`com.bigbrassband.jira.git.services.async.ReindexQueueReindexTask`.

*   Main/local node indexing - INFO/DEBUG for <br>`com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl`.

*   Git GC task - INFO/DEBUG for <br>`com.bigbrassband.jira.git.services.async.ReindexQueueGCTask`.

*   Repository removing - INFO/DEBUG for <br>`com.bigbrassband.jira.git.services.gitmanager.visitors.RemoveVisitor`.

<p>&nbsp;</p>

## More related Administration articles

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

[Upgrades and migrations within same servver](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed)

[Scheduling jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed)

[Recommended Jira memory settings](/git-integration-for-jira-data-center/recommended-jira-memory-settings-gij-self-managed)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed)

**Indexing queue explainer** (this page)

