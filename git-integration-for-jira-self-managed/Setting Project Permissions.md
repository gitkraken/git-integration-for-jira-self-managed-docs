---

title: Setting Project Permissions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Setting Project Permissions

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions>

* * *

**What’s on this page:**

* * *

## Introduction

By default - integrations (GitLab, GitHub, etc) and individual repositories are associated with all Jira projects. Jira administrators can limit which Jira projects are associated to integrations or individual repositories.

**Related Features**  
Associating a Jira project with an integration or repository will limit repository content displaying in:

*   **Git Commits** issue tab
    
*   **Git Roll Up** issue tab
    
*   **Git Source Code** issue side panel 
    
*   **View all repositories** page
    
*   **Repository Browser: Browse** page
    
*   **Repository Browser: Commits** page
    
*   **Repository Browser: Compare** page
    
*   **Create branch issue** dialog
    
*   **Create pull/merge request** issue dialog
    

Jira users must have the **View Development Tools** permission in the context of a Jira project to view content from the Git Integration for Jira app.

## Instructions for integrations (GitLab, GitHub, etc)

To limit which Jira projects are associated with an integration's repositories:

1.  Navigate to Jira dashboard menu Git ➜ **Manage repositories.**
    
2.  Add a new integration or edit existing integration's settings.
    
3.  Locate the **Project Permissions** setting.
    
4.  Uncheck **Associate with all projects.**
    
5.  Select one or more Jira projects (at least one must be selected).
    
6.  Click **Update.**
    

### **Video Example 1:** Setting project permissions for an existing GitLab integration

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/rnm5t639cz) _to open this video in a new browser tab for more viewing options._

### **Video Example 2:** Setting project permissions at the repository level for an existing GitLab integration

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/fder2qnpgw) _to open this video in a new browser tab for more viewing options._

## Instructions for individual repositories

To limit which Jira projects are associated for individual repositories:

1.  Navigate to Jira dashboard menu Git ➜ **Manage repositories.**
    
2.  Add a new repository or edit existing repository's settings.
    
3.  Locate the **Project Permissions** setting.
    
4.  Uncheck **Associate with all projects.**
    
5.  Select one or more Jira projects (at least one must be selected).
    
6.  Click **Update.**
    

### **Video Example:** Setting project permissions for a repository 

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/xvzj32nxou) _to open this video in a new browser tab for more viewing options._

## Related articles

*   Page:
    
    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849)
    
*   Page:
    
    [Permissions](/wiki/spaces/GIJDC/pages/408453129/Permissions)
    
*   Page:
    
    [Setting Project Permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions)
    

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