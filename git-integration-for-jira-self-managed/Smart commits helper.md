---

title: Smart commits helper
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
VERSION 2.9.3+ Introduced the smart commit helper and is available at the following locations in Jira:

*   Issue ➜ **Git Commits tab**

*   Projects (sidebar) ➜ **Git Commits**

*   Repository Browser (View all repositories) ➜ click a repository ➜ **Latest commits**


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398529/smart-commit-helper-example.png?version=1&modificationDate=1630642893155&cacheVersion=1&api=v2&width=680&height=353)


A smart commit helper indicator is displayed to the right of the user/commit author:

|     |     |
| --- | --- |
| **Status** | **Description** |
| COMMIT | The Smart Commits setting is enabled for the repository but there is no smart commit keyword in the commit message. |
| SMART COMMIT | The commit message has a valid smart commit structure and was successfully processed. |
| SMART COMMIT ERROR | There was an error during smart commit processing. For example, invalid keyword; commit author and Jira user are not the same; permission issues or wrong values. |


**The smart commit helper status are not shown:**

*   for any smart commits that were made before VERSION 2.9.3 of Git Integration for Jira app.

*   for smart commits that were ignored due to **Smart commits** setting for that repository is disabled.

*   for smart commits that have not been processed yet.

*   for processed commits with ticket ID but without smart commit keyword when **Smart commits** setting is disabled for that repository.


When **Smart commits** setting is `Disabled` for that repository, the Git Integration for Jira app will not show the COMMIT indicators.


Refer to the commit message case examples below:

|     |     |
| --- | --- |
| **Commit ID** | **Commit Message** |
| Commit1 | Merged to master |
| (This commit message does not contain a Jira issue key) |
| Commit2 | **TST-1** Merged to master |
| (This commit message has a Jira issue key but does not have a smart commit keyword) |
| Commit3 | **TST-1** Merged to master **#done** |
| (This commit message has an issue key and a valid smart commit transition keyword) |
| Commit4 | **TST-1** Merged to master **#unknownSCkeyword** |
| (This commit message has an invalid smart commit keyword) |


**When Smart commits setting (SC) was set to ENABLED:**

|     |     |     |
| --- | --- | --- |
| **Commit ID** | **Status after SC=Disabled** | **Status after SC=Enabled** |
| Commit1 | Commit is ignored since issue key is not provided. | Commit is ignored since issue key is not provided. |
| Commit2 | No status indicator. | COMMIT |
| Commit3 | SMART COMMIT | SMART COMMIT |
| Commit4 | SMART COMMIT ERROR | SMART COMMIT ERROR |


**When Smart commits setting (SC) was set to DISABLED:**

|     |     |     |
| --- | --- | --- |
| **Commit ID** | **Status after SC=Disabled** | **Status after SC=Enabled** |
| Commit1 | Commit is ignored since issue key is not provided. | Commit is ignored since issue key is not provided. |
| Commit2 | No status indicator. | No status indicator because it was marked as ignored. |
| Commit3 | No status indicator. | No status indicator because it was marked as ignored. |
| Commit4 | No status indicator. | No status indicator because it was marked as ignored. |

The commit status shown on the Issue page depends on the **Smart commits** setting that was set at the time the commits were processed.

