---

title: Setting up repository root not located in Jira Home directory (Admins)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

There are three possible ways to setup a repository root that is not located in the Jira home directory:

1.  Clone the repository outside of Jira then connect to it via Manage git repositories page ➜ Connect to Git Repository ➜ **Advanced Setup**.

2.  Clone the repository with the standard **Connect to Git Repository** wizard into the Jira home directory.  Soon afterwards, move the cloned repository and update the settings on the repository.

3.  You could symlink the `{$JIRA_HOME}/data/git-plugin` directory to a different volume. The standard **Connect to Git Repository** wizard will still write there, but the data will reside on the different volume. But be aware, that the Git Integration for Jira app treats anything in the `git-plugin` folder as a clone that it owns.

<br>
<br>

[**Prev:** Adding a repository hosted on Windows Servers or Windows Network Share \(Admins\)](/git-integration-for-jira-data-center/Adding-a-repository-hosted-on-Windows-Servers-or-Windows-Network-Share-(Admins)-gij-self-managed)

[**Next:** Reindex API to trigger indexing](/git-integration-for-jira-data-center/Reindex-API-to-trigger-indexing-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

**Setting up repository root not located in Jira Home directory (Admins)** (this page)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)


