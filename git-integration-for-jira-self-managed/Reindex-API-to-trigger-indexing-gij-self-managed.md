---

title: Reindex API to trigger indexing
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- getting started for git admins -->

Call the [Reindex REST API](/git-integration-for-jira-data-center/reindex-api-gij-self-managed) to have more control on indexing.

&nbsp;

### Reindex POST API

Use this method to start the reindex process in a separate thread.

**Example:**

```powershell
http://jira.yourorg.com/rest/gitplugin/2.0/reindex
```

For more detailed information, see [Reindex POST API documentation](/git-integration-for-jira-data-center/reindex-post-api-gij-self-managed).

&nbsp;

### Reindex GET API

**Example #1:**
Use this method to retrieve the reindex status for a particular repository.

```powershell
http://jira.yourorg.com/rest/gitplugin/1.0/index.json?repoId=113
```

**Example #2:**
Use this method to retrieve reindex status of all repositories.

```powershell
http://jira.yourorg.com/rest/gitplugin/1.0/index.json
```

For more detailed information, see [Reindex GET API documentation](/git-integration-for-jira-data-center/reindex-get-api-gij-self-managed)

&nbsp;
* * *

[**Prev:** Setting up repository root not located in Jira Home directory \(Admins\)](/git-integration-for-jira-data-center/Setting-up-repository-root-not-located-in-Jira-Home-directory-(Admins)-gij-self-managed)

[**Next:** Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

&nbsp;

### More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

**Reindex API to trigger indexing** (this page)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)


