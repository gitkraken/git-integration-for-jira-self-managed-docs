---

title: Setup GitLab Server to respond to incoming network API calls
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

In order for GitLab to display correct repository clone links to your users, it needs to know the URL under which it is reached by your users (e.g. `http://gitlab.example.com`)

To reconfigure:

1.  Access the GitLab configuration file in `/etc/gitlab/gitlab.rb`.

    ```powershell
    sudo vi /etc/gitlab/gitlab.rb
    ```

2.  Change the `external_url` value to your GitLab server URL.

    ```powershell
    external_url "http://gitlab.example.com" #this is the default URL
    external_url "http://X.X.X.X.local/" #change it to your GitLab Server URL
    ```

3.  Run the reconfigure command to make the change take effect.

    ```powershell
    sudo gitlab-ctl reconfigure
    ```

<br>

Read this [**GitLab documentation**](https://docs.gitlab.com/omnibus/settings/configuration.html#configuring-the-external-url-for-gitlab) to know more about configuring the external URL for GitLab.

You should be able to add the GitLab repositories via Git Integration for Jira app ➜ Manage git repositories:

*   [**Add new integration panel**](/git-integration-for-jira-data-center/using-the-add-new-integration-wizard-gij-self-managed/) (recommended for multiple repository integration)

*   [**Connect to Git Repository**](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed/) (single repository or ssh repository integration)

<br>
<br>

[**Prev:** Getting started for Git administrators (index)](/git-integration-for-jira-data-center/Getting-started-for-Git-administrators-gij-self-managed)

[**Next:** New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More related articles on Git for Jira administrators

**Setup GitLab Server to respond to incoming network API calls** (this page)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

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


