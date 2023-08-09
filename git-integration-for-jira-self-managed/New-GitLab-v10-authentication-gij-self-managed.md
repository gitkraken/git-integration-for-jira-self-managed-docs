---

title: New GitLab v10+ authentication
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

GitLab v10+ stopped accepting username/password credentials for API access and will only recognize Personal Access Tokens (PAT) and OAuth authentications. Service users are strongly advised to switch from using username/password for GitLab.com and newer versions of GitLab Server (CE/EE) to using Personal Access Tokens.

For GitLab Server service users, they won't see the issue until they upgrade their GitLab Servers to version 10 and higher. Git Integration for Jira app offers pre-v10 GitLab Server users as a Legacy connection option.

To access a Git repository over HTTP, use the **username** as the username and the **PAT** for the password.

To pass the private access token (for example: `XpigzF1JxMnAZ7mn9qgN`) to an API call with GitLab.com:

```powershell
curl --header "Private-Token: XpigzF1JxMnAZ7mn9qgN" https://gitlab.com/api/v4/projects?membership=true
```

&nbsp;

For more information on GitLab personal access token, see [**GitLab: Personal Access Token**](https://docs.gitlab.com/ce/user/profile/personal_access_tokens.html).

&nbsp;
* * *

[**Prev:** Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/Setup-GitLab-Server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[**Next:** General settings - Improving Jira performance](/git-integration-for-jira-data-center/General-settings-Improving-Jira-performance-gij-self-managed)

&nbsp;

### More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

**New GitLab v10+ authentication** (this page)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)


