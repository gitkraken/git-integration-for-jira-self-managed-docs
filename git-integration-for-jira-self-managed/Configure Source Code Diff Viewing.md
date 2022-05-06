---

title: Configure Source Code Diff Viewing
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Configure Source Code Diff Viewing

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2054881287/Configure+Source+Code+Diff+Viewing>

* * *

By default - integrations (GitLab, GitHub, etc) and individual repositories have _Source Code Diff Viewing_ enabled. Jira administrators can disable all user's access to source code viewing by integration or individual repository.

**Related features**  
Enabling or disabling the _Source Code Diff Viewing_ setting for an integration or repository will limit repository source code displaying in:

*   **Git Commits** issue tab: **View full commit** button is removed.
    
*   **Git Roll Up** issue tab: **Diff** page: shows information message.
    
*   **Repository Browser: Browse** page: shows information message.
    
*   **Repository Browser: Compare** page: **View full commit** button is removed.
    
*   **Git Commits** project tab: **View full commit** button is removed.
    

Jira users must have the **View Development Tools** permission in the context of a Jira project to view content from the Git Integration for Jira app.

## Instructions for integrations (GitLab, GitHub, etc)

To enable/disable the _Source Code Diff Viewing_ setting for all repositories within an integration:

1.  Navigate to **Manage Git repositories**.
    
2.  Add a new integration or edit existing integration's settings
    
3.  Locate the **Source Code Diff Viewing** setting.
    
4.  Select **Enabled** or **Disabled**.
    
5.  Click **Update**.
    

### Example: Disabling _Source Code Diff Viewing_ for an existing GitLab integration

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/qgatwyyv2m) _to open this video in a new tab/window for more viewing options._

### Example: Disabling _Source Code Diff Viewing_ at the repository level for an existing GitLab integration

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/4vpnakdzpf) _to open this video in a new tab/window for more viewing options._

## Instructions for individual repositories

To enable/disable the Repository Browser for individual repositories:

1.  Navigate to **Manage Git repositories**.
    
2.  Add a new repository or edit existing repository's settings.
    
3.  Locate the **Source Code Diff Viewing** setting.
    
4.  Select **Enabled** or **Disabled**.
    
5.  Click **Update**.
    

### Example: Disabling _Source Code Diff Viewing_ for a repository

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/mtwnmihirc) _to open this video in a new tab/window for more viewing options._

## More how-to articles

*   Page:
    
    [Creating Personal Access Tokens](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens)
    
*   Page:
    
    [Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters)
    
*   Page:
    
    [Working with Custom API Path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path)
    
*   Page:
    
    [Creating and configuring SSH keys (Windows/MacOS/Linux)](/wiki/spaces/GIJDC/pages/183271450)
    
*   Page:
    
    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849)
    
*   Page:
    
    [Setting Project Permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions)
    
*   Page:
    
    [How to get a quote?](/wiki/spaces/GIJDC/pages/1165721603)
    
*   Page:
    
    [Ways to Index Git Data to Jira Issues](/wiki/spaces/GIJDC/pages/1207828916/Ways+to+Index+Git+Data+to+Jira+Issues)
    
*   Page:
    
    [Proxy settings on adding integrations (except AWS CodeCommit)](/wiki/spaces/GIJDC/pages/1808007195)
    
*   Page:
    
    [Configure Source Code Diff Viewing](/wiki/spaces/GIJDC/pages/2054881287/Configure+Source+Code+Diff+Viewing)