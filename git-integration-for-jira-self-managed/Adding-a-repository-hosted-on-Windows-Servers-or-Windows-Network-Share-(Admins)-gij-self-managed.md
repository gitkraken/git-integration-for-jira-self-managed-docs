---

title: Adding a repository hosted on Windows Servers or Windows Network Share (Admins)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Add a new network share or Windows server hosted repository via the Connect to Git Repository wizard.

The wizard will continue without errors if the following conditions are met:

*   The network credentials accessing the git repository must be the same as the user running Jira.

*   The network path is not longer than 255 characters.

*   The user under which Jira is running should have **read** access to network path.


In the Manage git repositories page, edit the repository via &nbsp;![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit repository settings**.

Under **Repository Settings**, set _**Enable Fetches**_ option to `Git repository hosted on the same server as Jira`.

<img src='/wp-content/uploads/gij-gitserver-edit-repocfg-fetches-sel2.png' style='display:block;margin:25px auto;max-width:100%' />

Considering the above conditions, verify if the repository can be cloned successfully using the network path. With the server which hosts Jira, start the command-line session under the same user which Jira is running on.

For example:

```powershell
$ git clone file:////Ws148/Photo/repo
Cloning into ‘network-repo’...
```


If the path is invalid, does not exist or has permission issues, an error similar to the following will be displayed:

```powershell
fatal: '//Ws148/Photo/repo' does not appear to be a git repository
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
and the repository exists.
```

&nbsp;

For more information, see [Integration guide -- Windows Network Share](/git-integration-for-jira-data-center/windows-network-server-share-gij-self-managed).

&nbsp;
* * *

[**Prev:** General settings: Improving Jira performance](/git-integration-for-jira-data-center/General-settings-Improving-Jira-performance-gij-self-managed)

[**Next:** Setting up repository root not located in Jira Home directory \(Admins\)](/git-integration-for-jira-data-center/Setting-up-repository-root-not-located-in-Jira-Home-directory-(Admins)-gij-self-managed)

&nbsp;

### More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

**Adding a repository hosted on Windows Servers or Windows Network Share (Admins)** (this page)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)


