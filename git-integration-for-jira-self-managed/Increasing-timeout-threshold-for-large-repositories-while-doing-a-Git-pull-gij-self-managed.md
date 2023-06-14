---

title: Increasing timeout threshold for large repositories while doing a Git pull
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

For this workaround to work, the user must have an access to a Jira hosting instance:

1.  Login to the hosting server.

2.  Create a new directory in the path different from the `JIRA HOME` directory. For example, `~/Image-repo/`

3.  Go to a directory and perform a clone of a repository:

    ```powershell
    git clone --mirror git@gitserver.com:repo/url.git  **1
    ```

    Or use the generic clone:

    ```powershell
    git clone git@gitserver.com:repo/url.git  **2
    ```

    <sup><b>1</b></sup> Modify the git repository URL to the correct one.<br>
    <sup><b>2</b></sup> Using the generic clone may take a bit longer and requires more disk space to store.

4.  For `~/Image-repo/` directory, give read and write permissions to the same user running Jira.
    For example, to make the user named _user_ be an owner of a folder, perform the following command:

    ```powershell
    sudo chown user ~/Image-repo
    ```

5.  Using the local path, connect the repository via the [Git Integration for Jira app Advanced setup wizard](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed). Use the correct local path for the Git for Jira app to successfully detect the repository.

    ![](/wp-content/uploads/gij-connect-git-repo-advanced-local-path-c.png)

6.  Click **Detect** to specify the origin value.

7.  Configure other settings if required. Click **Add** to proceed.


The repository is added and indexing should work.

&nbsp;

### Git operations timeout

<img src='/wp-content/uploads/gij-git-serverdc-repo-cfg-git-operations-timeout.png' style='display:block;margin:25px auto;max-width:100%' />

This setting affects how long will Git Integration for Jira app waits for connections performed during git clone and git fetch. We recommend to increase the time value if you have large repositories, and in some cases, when connecting to them mostly results in timeout.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you have several large repositories and have a problem with exceeded timeout, we recommend that you use our <a href='/git-integration-for-jira-data-center/working-with-tracked-folders'>Tracked folders</a> feature to scan local folders at once and import repositories automatically.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[**Next:** Working with Tracked folders](/git-integration-for-jira-data-center/working-with-tracked-folders-gij-self-managed)

&nbsp;

### More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

**Increasing timeout threshold for large repositories while doing a Git pull** (this page)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)

