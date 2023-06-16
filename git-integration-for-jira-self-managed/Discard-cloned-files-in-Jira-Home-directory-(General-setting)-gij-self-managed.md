---

title: Discard cloned files in Jira Home directory (General setting)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- getting started -->

<img src='/wp-content/uploads/gij-gitserver-discard-cloned-files-gencfg.png' style='margin:25px auto;max-width:100%;display:block;' />

&nbsp;

This feature will reduce Jira server storage by deleting files from cloned git repositories after indexing.  Discarding files can save disk space but may limit some features such as displaying diffs of files.

Access this feature via Jira dashboard menu Git ➜ Manage repositories ➜ **General settings** (sidebar). Alternatively, go to Jira dashboard menu – Jira Administration ➜ Applications ➜ **General settings** (sidebar).

There are three options to choose from:

*   **Keep all cloned binary files. No storage savings. All features available.** This option will leave all cloned repositories intact.

*   **Discard all files that match the mask below. Some features limited.** This option will delete all files in the cloned repositories matching the declared file extensions.

*   **Discard all files EXCEPT those that match the mask below. Some features limited.** This option will delete all other files in the cloned repositories except those files with extensions declared.

&nbsp;

Select any option with the _discard_ label to enable editing of the file mask field.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For full list of features, version history and supported Jira version of the Git for Jira app, see <a href='https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions' target='_blank'><b>Git Integration for Jira app Version History</b></a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Whenever the setting is changed, BigBrassBand recommends to perform a manual re-clone of the repositories to ensure an error-free operation.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Recommended upgrade method for Git Integration for Jira app](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[**Next:** Working with SSH keys](/git-integration-for-jira-data-center/working-with-ssh-keys-gij-self-managed)

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

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

**Discard cloned files in Jira Home directory (General setting)** (this page)


