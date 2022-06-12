---

title: Plugin Data Storage
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The list of database tables for Git Integration for Jira app can be accessed at Jira Administration ➜ System ➜ (sidebar) Advanced ➜ **Plugin Data Storage**.

The database tables are described in the table below:

| **Table** | **Description** |
| --- | --- |
| AO\_8BA09E\_GIT\_REPOSITORY | This table contains the main repository configuration and repository parameters visible to users. |
| AO\_8BA09E\_MERGE\_REQ\_COMMITS | This table contains information required to support the feature. For more information, see [General Setting: Enable indexing pull/merge requests by commits](/git-integration-for-jira-self-managed/branch-and-pull-request-settings-formerly-git-integration-options-gij-self-managed). |
| AO\_8BA09E\_MERGE\_REQUEST | This table contains information about external merger requests and pull requests from the connected git servers. |
| AO\_8BA09E\_OBJECT\_REGISTRATION | This table contains information about object states for the Scripting feature. The objects are:<br><br>*   commits<br>    <br>*   branches<br>    <br>*   merge/pull requests |
| AO\_8BA09E\_PROJECT\_MAPPING | This table contains project permissions.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/attachments/1598193683/ao-table-02.png?version=1&modificationDate=1620447300176&cacheVersion=1&api=v2) |
| AO\_8BA09E\_PROJECT\_SETTINGS | This table contains projects selected for some general setting options.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/attachments/1598193683/ao-table-01.png?version=1&modificationDate=1620446273338&cacheVersion=1&api=v2) |
| AO\_8BA09E\_REPO\_WATCHERS | This table contains repositories' watchers. |
| AO\_8BA09E\_REPOSITORY\_PARAMS | This table contains internal repository parameters/states. |
| AO\_8BA09E\_SCREGISTRATION | This table contains processed smart commits. |
| AO\_8BA09E\_SCREGISTRATION\_ERROR | This table contains errors that appeared during smart commits processing. |
| AO\_8BA09E\_SSH\_KEY\_ENTRY | This table contains SHH keys used during connection to repositories. |
| AO\_8BA09E\_UNTRCKDCOMM\_NOTF | This table is used to track sent notifications that have no issue key and untracked by indices. |
| AO\_8BA09E\_USERS\_PATS | This table contains users' personal access tokens. |
| AO\_8BA09E\_WEB\_HOOK\_ENTRY | This table contains a secret key of the reindex webhook. It contains only one record. |
| **The following pull request tables are deprecated:** |     |
| AO\_8BA09E\_PULL\_REQUEST | We don't use it anymore. But, Atlassian advised not to delete tables. |
| AO\_8BA09E\_PULL\_REQUEST\_V2 | This table contains pull requests. |
| AO\_8BA09E\_REVIEW\_COMMENT | We don't use it any more. But, Atlassian advised not to delete tables. |
| AO\_8BA09E\_REVIEW\_COMMENT\_V2 | This table contains comments to the pull requests. |