---

title: Enforce Git service permissions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Enforce Git service permissions

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2091810842/Enforce+Git+service+permissions>

* * *

NEW FEATURE Available in Git Integration for Jira Server/Data Center v4.1.4

This page is intended for Jira administrators. For Jira users with limited access, please [go to this page](/wiki/spaces/GIJDC/pages/2091810817/Enforced+git+permissions+for+Jira+users) instead.

_Right click_ [**here**](https://bigbrassband.wistia.com/medias/npe76i5nxm) _to open this video in a new tab/window for more viewing options._

## Getting started

Source code is sensitive data and a great deal of effort is taken by development teams to get the permissions right. With the **Enforce Git service permissions** feature, your Git service permissions will be honored when presenting Jira users any Git data.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-02-28%20at%2011.59.57@2x-20220228-170028.png?version=1&modificationDate=1647757588122&cacheVersion=1&api=v2)

  
This setting provides Jira administrators the option of switching to a secure mode. In this mode, a Jira user is prevented from viewing git data, unless they have been authenticated to the Git server to view this specific data.

A Jira user must have the _**View development tools**_ Jira permission to be able to add a personal access token to an integration or repository.

This feature allows users to enter their PATs without accessing the Repository Browser page.

### What Jira users will see when Git service permissions are enabled and they have not yet provided a Personal Access Token

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-03-01%20at%2001.11.27@2x-20220301-061142.png?version=1&modificationDate=1647757587623&cacheVersion=1&api=v2)

### Jira user profile: Entering the Personal Access Token

From the Jira user profile page, the Jira user will enter their Git service Personal Access Token (PAT). For instructions on steps to create the appropriate token, see article [Creating Personal Access Tokens](/wiki/spaces/GITCLOUD/pages/107216897/Creating+Personal+Access+Tokens).

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-03-01%20at%2001.13.39@2x-20220301-061400.png?version=1&modificationDate=1647757587377&cacheVersion=1&api=v2)

### Jira issue view: Git service permissions are enabled and a Jira user has provided a Personal Access Token

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-03-01%20at%2001.17.22@2x-20220301-061737.png?version=1&modificationDate=1647757587117&cacheVersion=1&api=v2)

## Applied permissions

If the **Enforce Git service permissions** setting is enabled, a Jira user will see data only from the integrations for which their PAT has been provided. For example:

|     |     |     |
| --- | --- | --- |
| **Access location** | **Section** | **Condition(s)** |
| Jira issue | Git Commits tab | Git data is only shown if the user has a Git server account, GitHub for example, that has permissions to this repository. |
| Jira issue | Git development panel | Users without permission can see the number of commits but won’t be able to view the commit code diffs, branch name or repository name. |
| Project sidebar | Git Commits | Git data is only shown if the user has a Git server account, GitHub for example, that has permissions to this repository. |
| Repository browser | Repository view | Git data is only shown if the user has provided a Git service account. |

## Supported git platforms

|     |     |     |
| --- | --- | --- |
| **Integration** | **Supported?** | **Result** |
| GitHub git repositories | Yes | GITHUB CLOUD GITHUB SELF-HOSTED  <br>Users will only see the GitHub integration data when a PAT is provided for it. |
| GitLab git repositories | No\* | COMING SOON  <br>\*Support for GitLab on the **Enforce Git service permissions** feature will be added sometime later in 2022. |

## General setting: Enforce Git service permissions (advanced)

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-02-28%20at%2012.01.08@2x-20220228-170131.png?version=1&modificationDate=1647757587877&cacheVersion=1&api=v2)

**Max permission cache age** – This setting grants administrators the ability to set how long Git server permissions are cached in Git Integration for Jira app. The default value for this setting is **24** hours.

The [Require User PAT general setting](/wiki/spaces/GIJDC/pages/1947107395/Require+User+PAT+general+setting) must be enabled to use the **Enforce Git Service permissions** feature.

### More related topics about general settings

*   Page:
    
    [General settings](/wiki/spaces/~493751811/pages/403013670/General+settings) (Shanmarc Florete)
    
*   Page:
    
    [Git server user permissions validation](/wiki/spaces/GITSERVER/pages/1987903509/Git+server+user+permissions+validation) (Git Integration for Jira Server)
    
*   Page:
    
    [General settings for administrators](/wiki/spaces/GITCLOUD/pages/1923025087/General+settings+for+administrators) (Git Integration for Jira Cloud)
    
*   Page:
    
    [General settings](/wiki/spaces/GITSERVER/pages/1923028801/General+settings) (Git Integration for Jira Server)
    
*   Page:
    
    [General settings](/wiki/spaces/GIJDC/pages/1930398111/General+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Enable beta features setting](/wiki/spaces/GITCLOUD/pages/2070216724/Enable+beta+features+setting) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Git roll up issue tab setting](/wiki/spaces/GITCLOUD/pages/1207796128/Git+roll+up+issue+tab+setting) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Git commits issue tab and project page](/wiki/spaces/GITCLOUD/pages/1207829071/Git+commits+issue+tab+and+project+page) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Issue git source code panel setting](/wiki/spaces/GITCLOUD/pages/1207829089/Issue+git+source+code+panel+setting) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Repository browser settings](/wiki/spaces/GITCLOUD/pages/1207829111/Repository+browser+settings) (Git Integration for Jira Cloud)
    
*   Page:
    
    [GitKraken integration settings](/wiki/spaces/GITCLOUD/pages/1980563563/GitKraken+integration+settings) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Git integration options](/wiki/spaces/GITCLOUD/pages/1207829137/Git+integration+options) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Jira development information settings](/wiki/spaces/GITCLOUD/pages/1207796181/Jira+development+information+settings) (Git Integration for Jira Cloud)
    
*   Page:
    
    [Repository Browser general setting](/wiki/spaces/GITSERVER/pages/1944911873/Repository+Browser+general+setting) (Git Integration for Jira Server)
    
*   Page:
    
    [Source Code Diff Viewing general setting](/wiki/spaces/GITSERVER/pages/1946419213/Source+Code+Diff+Viewing+general+setting) (Git Integration for Jira Server)