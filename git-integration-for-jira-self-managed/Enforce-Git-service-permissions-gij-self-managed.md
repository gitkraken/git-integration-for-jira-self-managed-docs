---

title: Enforce Git service permissions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
NEW FEATURE Available in Git Integration for Jira Server/Data Center v4.1.4

This page is intended for Jira administrators. For Jira users with limited access, please [go to this page](/git-integration-for-jira-self-managed/enforced-git-permissions-for-jira-users-gij-self-managed) instead.

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

From the Jira user profile page, the Jira user will enter their Git service Personal Access Token (PAT). For instructions on steps to create the appropriate token, see article [Creating Personal Access Tokens](/git-integration-for-jira-self-managed/creating-personal-access-tokens-gij-self-managed).

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-03-01%20at%2001.13.39@2x-20220301-061400.png?version=1&modificationDate=1647757587377&cacheVersion=1&api=v2)

### Jira issue view: Git service permissions are enabled and a Jira user has provided a Personal Access Token

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-03-01%20at%2001.17.22@2x-20220301-061737.png?version=1&modificationDate=1647757587117&cacheVersion=1&api=v2)

## Applied permissions

If the **Enforce Git service permissions** setting is enabled, a Jira user will see data only from the integrations for which their PAT has been provided. For example:

| **Access location** | **Section** | **Condition(s)** |
| --- | --- | --- |
| Jira issue | Git Commits tab | Git data is only shown if the user has a Git server account, GitHub for example, that has permissions to this repository. |
| Jira issue | Git development panel | Users without permission can see the number of commits but won’t be able to view the commit code diffs, branch name or repository name. |
| Project sidebar | Git Commits | Git data is only shown if the user has a Git server account, GitHub for example, that has permissions to this repository. |
| Repository browser | Repository view | Git data is only shown if the user has provided a Git service account. |

## Supported git platforms

| **Integration** | **Supported?** | **Result** |
| --- | --- | --- |
| GitHub git repositories | Yes | GITHUB CLOUD GITHUB SELF-HOSTED  <br>Users will only see the GitHub integration data when a PAT is provided for it. |
| GitLab git repositories | No\* | COMING SOON  <br>\*Support for GitLab on the **Enforce Git service permissions** feature will be added sometime later in 2022. |

## General setting: Enforce Git service permissions (advanced)

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810842/CleanShot2022-02-28%20at%2012.01.08@2x-20220228-170131.png?version=1&modificationDate=1647757587877&cacheVersion=1&api=v2)

**Max permission cache age** – This setting grants administrators the ability to set how long Git server permissions are cached in Git Integration for Jira app. The default value for this setting is **24** hours.

The [Require User PAT general setting](/git-integration-for-jira-self-managed/require-user-pat-general-setting-gij-self-managed) must be enabled to use the **Enforce Git Service permissions** feature.
