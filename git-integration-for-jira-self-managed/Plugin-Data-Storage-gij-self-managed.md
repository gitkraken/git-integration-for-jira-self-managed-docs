---

title: Plugin Data Storage
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The list of database tables for Git Integration for Jira app can be accessed at ![](/wp-content/uploads/actions-icon.png) Jira Administration ➜ System ➜ (sidebar) Advanced ➜ **Plugin Data Storage**.

The database tables are described in the table below:

| DB Table | Description |
| :--- | :--- |
| AO\_8BA09E\_GITHUB\_APPS | This table is a temporal place to persist all configurations specifically for integrations over GitHub App. Values are kept there until the integration is fully established. |
| AO\_8BA09E\_GIT\_REPOSITORY | This table contains the main repository configuration and repository parameters visible to users. |
| AO\_8BA09E\_INTEGRATION\_USER | This table contains information on external users, such as the Pull Request author. |
| AO\_8BA09E\_MERGE\_REQ\_COMMITS | This table contains information required to support the feature. For more information, see [General Setting: Enable indexing pull/merge requests by commits](/git-integration-for-jira-data-center/branch-and-pull-request-settings-formerly-git-integration-options-gij-self-managed). |
| AO\_8BA09E\_MERGE\_REQUEST | This table contains information about external merger requests and pull requests from the connected git servers. |
| AO\_8BA09E\_MERGE\_REQUEST\_EVENT | This table persists additional information about Pull Requests like events on a timeline. E.g. someone has commented or reviewed a PR. |
| AO\_8BA09E\_OBJECT\_REGISTRATION | This table contains information about object states for the Scripting feature. The objects are:<br><br>*   commits<br><br>*   branches<br><br>*   merge/pull requests |
| AO\_8BA09E\_PROJECT\_MAPPING | This table contains project permissions.<br><br>![](/wp-content/uploads/gij-ao-table-02.png) |
| AO\_8BA09E\_PROJECT\_SETTINGS | This table contains projects selected for some general setting options.<br><br>![](/wp-content/uploads/gij-ao-table-01.png) |
| AO\_8BA09E\_REINDEX\_LOCK | This table is used to lock a repository which is being currently processed by an indexer to avoid two or more indexers to process the repository simultaneously. |
| AO\_8BA09E\_REINDEX\_QUEUE | This table stores the queued and processing/processed items. When an item is extracted from the queue, it is not removed, but marked as executed instead. |
| AO\_8BA09E\_REINDEX\_QUEUE\_LOG | This table contains records for status data from all nodes. This table is introduced to avoid concurrent changes from different nodes. Each node adds/modifies its own record. |
| AO\_8BA09E\_REPOSITORY\_PARAMS | This table contains internal repository parameters/states. |
| AO\_8BA09E\_REPO\_WATCHERS | This table contains repositories' watchers. |
| AO\_8BA09E\_SCREGISTRATION | This table contains processed smart commits. |
| AO\_8BA09E\_SCREGISTRATION\_ERROR | This table contains errors that appeared during smart commits processing. |
| AO\_8BA09E\_SSH\_KEY\_ENTRY | This table contains SHH keys used during connection to repositories. |
| AO\_8BA09E\_TAGS\_TOPOLOGY | This table stores tags chains per connected repository. It is used for an internal optimization of a repository indexing. |
| AO\_8BA09E\_UNTRCKDCOMM\_NOTF | This table is used to track sent notifications that have no issue key and untracked by indices. |
| AO\_8BA09E\_USERS\_PATS | This table contains users' personal access tokens. |
| AO\_8BA09E\_WEB\_HOOK\_ENTRY | This table contains a secret key of the reindex webhook. It contains only one record. |

&nbsp;

**The following pull request tables are deprecated:**

| DB Table | Description |
| :--- | :--- |
| AO\_8BA09E\_PULL\_REQUEST | We don't use it anymore. But, Atlassian advised not to delete tables. |
| AO\_8BA09E\_PULL\_REQUEST\_V2 | This table contains pull requests. |
| AO\_8BA09E\_REVIEW\_COMMENT | We don't use it any more. But, Atlassian advised not to delete tables. |
| AO\_8BA09E\_REVIEW\_COMMENT\_V2 | This table contains comments to the pull requests. |

&nbsp;

## More related Administration articles

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

[Upgrades and migrations within same servver](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed)

[Scheduling jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed)

[Recommended Jira memory settings](/git-integration-for-jira-data-center/recommended-jira-memory-settings-gij-self-managed)

**Plugin Data Storage** (this page)

[Indexing queue explainer](/git-integration-for-jira-data-center/indexing-queue-explainer-gij-self-managed)

