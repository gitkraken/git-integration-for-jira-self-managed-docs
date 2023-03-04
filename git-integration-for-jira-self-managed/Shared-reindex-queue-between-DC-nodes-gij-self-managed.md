---

title: Shared reindex queue between DC nodes
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>GIT INTEGRATION: DATA CENTER</b>

With Git Integration for Jira app v4.0, the shared reindex queue improvement offers vast performance improvements between DC nodes.

<br>

**What’s on this page:**
- [Main features](#main-features)
  - [The Skipping feature](#the-skipping-feature)
  - [Webhook sleeping](#webhook-sleeping)
- [Before implementation](#before-implementation)
- [Advantages](#advantages)
- [Known issues](#known-issues)
- [See more Git Integration for Jira app features](#see-more-git-integration-for-jira-app-features)

<br>
<br>
<hr>
<br>
<br>

## Main features

This implementation added two new features that handle the reindex queue between DC nodes.

### The Skipping feature

Duplicate reindex requests are filtered out from the queue for the same repository. This does not interrupt and affect repositories currently being indexed. This feature affects all types of reindexing tasks – scheduled, manual and webhook.

### Webhook sleeping

![](/wp-content/uploads/gij-gitserver-webhooks-new-feature.png)

<br>
<br>

New Webhook settings are added under _**Advanced**_:

*   **Ignore non-matching webhooks** – Enable/disable this setting to filter out incoming duplicate webhooks or ignore it.

*   **Minimum repository reindex interval** – Webhooks will not reindex a repository more often than this value (in minutes). To disable the feature, set this value to **0** (zero).


Performing manual reindexing will process the repository and is always unaffected by this setting. Thus, the following operations are not affected:

*   manual reindexing from the plugin UI

*   reindexing via REST API

*   automatic reindexing (scheduled interval)


## Before implementation

Every DC node performs reindexing independently.

The Atlassian ClusterLocks is used to sync indexing between nodes. Thus, this produces warnings if the lock is held for a long time. File locking is required to sync repository access and in the long run, these locks may cause issues.

The lack of synchronization between nodes also affects smart commit processing and e-mail sending.

There is no way to show the current indexing status on nodes other than one that performs the reindexing. If a repository is queued in some node, it will be handled only on this node even if other nodes are idle. For now, there is no way to see the processed repositories in the queue.

The scanning operations for integrations (during the integration connection) go to the same queue. Thus, if some reindexing is currently performed, the scanning is suspended until all indexing operations are completed.

## Advantages

The new implementation eliminates all the above drawbacks. Git Integration for Jira v4.0 introduces a new persistent reindex queue that is shared between nodes.

*   File locks are held only for a short time during the queue handling and will not be used to sync the repository access.

*   Smart commits and e-mail sending are performed only on the 'main' node (the node that took an item from the queue and started to handle it). This node also performs the repository fetching and merge/pull requests retrieved from the Git server.

*   The indexing status is shared between nodes and should be visible in all of them (please note that the **Manage repositories** screen still isn't automatically updated).

*   All nodes may take any requests from the queue regardless of the node that placed the request. For consistency reasons, each repository may be processed only on one node at a time.


## Known issues

The new implementation provides better utility and performance gains. However, it requires cluster lock usage to enforce synchronization between nodes.

<br>

<p>&nbsp;</p>

## See more Git Integration for Jira app features

[Indexing queue viewer](/git-integration-for-jira-data-center/Indexing-queue-viewer-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking to the GitKraken Git client](/git-integration-for-jira-data-center/Deep-Linking-to-the-GitKraken-Git-client-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking into GitLens](/git-integration-for-jira-data-center/Deep-Linking-into-GitLens-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Git Integration + Jira Automation (Jira Server \| DC)](/git-integration-for-jira-data-center/Git-integration-plus-Jira-automation-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating branches](/git-integration-for-jira-data-center/Creating-branches-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/Creating-pull-merge-requests-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/Associate-Pull-Merge-Requests-to-Issues-Based-on-Commits-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Issue Git integration panel](/git-integration-for-jira-data-center/Issue-Git-integration-panel-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/Smart-commits-overview-gij-self-managed) (Git Integration for Jira Server/Data Center)

**Shared reindex queue between DC nodes** (this page)

[Enforced git permissions for Jira users](/git-integration-for-jira-data-center/Enforced-git-permissions-for-Jira-users-gij-self-managed) (Git Integration for Jira Server/Data Center)

