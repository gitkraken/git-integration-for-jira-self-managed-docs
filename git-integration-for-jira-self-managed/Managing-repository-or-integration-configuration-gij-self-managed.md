---

title: Managing repository or integration configuration
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Manage connected repositories or integration via the ![](/wp-content/uploads/actions-icon.png) **Actions** commands on the git configuration page.

## Introduction

After successfully connecting your git repositories or integrating your git host via Git Integration for Jira app, you can change repository settings depending on the connection protocol of the repository or integration.

## Getting started

On the git repository configuration page, you can manage connected repositories and integration such as enabling/disabling repository connection/integration (Jira Server only), edit/update repository/integration settings or disconnect repositories/integrations.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397435/manage-repositories-list-server.png?version=1&modificationDate=1630642841201&cacheVersion=1&api=v2&width=674&height=213)

## Repository/integration list

For the repository/integration list, utilize the following references for the column items:

| **Column** | **Description** | **Platform** |
| :--- | :--- | :--- |
| _**Enabled**_ | Enables/disables an integration for use in Jira. For disabled integrations, repository information and function such as commits, pull/merge request, git viewer and etc. are not available. | JIRA SERVER DATA CENTER |
| _**Location**_ | Displays a short identifier where the integration is located. For example, Some supported git host integration are also displayed here. | JIRA SERVER DATA CENTER |
| _**Repository / Integration**_ | Displays the repository name, integration name or integration URL.<br><div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">While you can change the name displayed for this column, some integration names does not allow to be changed.</div></div></div> | JIRA SERVER DATA CENTER JIRA CLOUD |
| **Last indexed** | Shows how long the time the integration was last indexed. | JIRA SERVER DATA CENTER |
| **Last indexer check** | Shows the date and time the indexing service has checked if the repository should be examined for changes.<br><br>For more information on Jira Cloud indexer, see [**Jira Cloud: Indexing Explainer**](/git-integration-for-jira-cloud/jira-cloud-indexing-explainer-gij-cloud/). | JIRA CLOUD |
| **Status** | Shows the index status of the integration.<br>*   It shows **UPDATED** if _Repository Root_ is configured correctly and the Jira instance can access it.<br>* It shows **DISABLED** if the Enabled status of connected repository is unchecked.<br>* It shows **REINDEXING**, **RUNNING**, or **QUEUED** during reindexing of the connected repository or tracked folder/repositories.<br>*   It shows ERROR if the connected repository has connection issues with the configured git host. | JIRA SERVER DATA CENTER JIRA CLOUD |
| **Actions** | To the right of the **Status** column are actions that can be performed for the selected connected repository/integration.<br><br>Clicking the Actions ![](/wp-content/uploads/actions-icon.png) icon will open a context menu with a set of functions for managing integrations. The Actions sub-menu functions will depend on the type of integration you were working on.<br><br>For more information, see **Managing Integration via Actions** for your specific platform:<br>*   [Jira Cloud](/git-integration-for-jira-cloud/managing-integrations-via-actions-jira-cloud-gij-cloud/)<br>*    [Jira Server/Data Center](/git-integration-for-jira-data-center/managing-integration-via-actions-gij-self-managed/). | JIRA SERVER DATA CENTER JIRA CLOUD |

