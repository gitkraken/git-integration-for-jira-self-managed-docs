---

title: Enforced git permissions for Jira users
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Available in Git Integration for Jira Server/Data Center v4.1.4

This page is intended for Jira users with limited access. If you are a Jira administrator, please [go to this page](/git-integration-for-jira-self-managed/enforce-git-service-permissions-gij-self-managed) instead.


Source code is sensitive data and development teams take a great deal of effort to get the permissions right. When the **Enforce Git service permissions** setting is enabled by your administrator, the Git service permissions will be honored when presenting any Git data to Jira users.

This state is called secure mode – where a Jira user is limited from viewing git data, unless they have been authenticated to the Git server to view this specific data.

**Requirement**
When “Enforce Git service permissions” is enabled, Jira users with the _**View development tools**_ Jira permission will be prompted to provide a Personal Access Token from the Jira user profile page.

### What a Jira user will see while in this mode and has not yet provided a Personal Access Token

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810817/CleanShot2022-03-01%20at%2001.11.27@2x-20220301-061142.png?version=1&modificationDate=1647757485130&cacheVersion=1&api=v2)

### Jira user profile: Entering the Personal Access Token

From the Jira user profile page, the Jira user can enter their Git service Personal Access Token (PAT). For instructions on creating the appropriate token, see article [Creating Personal Access Tokens](/git-integration-for-jira-self-managed/creating-personal-access-tokens-gij-self-managed).

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810817/CleanShot2022-03-01%20at%2001.13.39@2x-20220301-061400.png?version=1&modificationDate=1647757484882&cacheVersion=1&api=v2)

### Jira issue view: Git service permissions setting is enabled and a Jira user has provided a Personal Access Token

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2091810817/CleanShot2022-03-01%20at%2001.17.22@2x-20220301-061737.png?version=1&modificationDate=1647757484614&cacheVersion=1&api=v2)

