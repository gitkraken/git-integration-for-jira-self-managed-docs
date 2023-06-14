---

title: Recommended upgrade method for Git Integration for Jira
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- getting started -->

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

If you have installed the Git Integration for Jira app with versions prior to v2.10.2, perform the following steps to upgrade with minimal risk:

1.  Do the upgrade at night – when the number of Jira users is minimal.

2.  Make backups (see [below](#making-backups)).

3.  Upgrade the Git for Jira app to the latest version.

&nbsp;

### Making backups

**We strongly advise to make backups to avoid operations disaster.**

&nbsp;

#### Make a Jira backup (recommended)

The Git for Jira app upgrade only updates its components. Thus, it has no adverse effect to Jira. It is still better to make a backup of your Jira before any app upgrade as a safety measure.

&nbsp;

#### Make a Git Integration for Jira app configuration backup (recommended)

Make sure to do a backup of the Git repositories connection configuration.

1.  Perform a bulk export of your existing repositories or integration via the Git Integration for Jira app repositories configuration page.

    *   On your Jira dashboard menu Git ➜ **Manage repositories**.

    *   Click the **Bulk Change** button drop down then select **1\. Export configuration**. For detailed steps, see [Bulk Change - Export Configuration](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed).

        ![](/wp-content/uploads/gij-gitserver-gitcfg-bulk-change-menu-export.png)

2.  Make sure that you have all the required SSH keys uploaded to the Git Integration for Jira app

    *   On your Jira dashboard, go to menu Git ➜ **Manage repositories**.

    *   Click **SSH keys** on the sidebar. This will make seamless connection of the SSH git repositories to Jira via [Bulk Change - Import Configuration](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed).

        ![](/wp-content/uploads/gij-add-ssh-key-loc-test-c.png)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you have several large repositories and have a problem with exceeded timeout, we recommend that you use our <a href='/git-integration-for-jira-data-center/tracked-folders-gij-self-managed'>Tracked folders integration</a> feature to scan local folders at once and import repositories automatically.
    </div>
    </div>
</div>

&nbsp;

### Unisntall \| Reinstall (Not recommended)

Another option is to completely uninstall then reinstall the Git for Jira app. However, this will result in Jira running on a clean state:

1.  Backup the Git repositories configuration via the Git for Jira app Bulk Export.

2.  Fully uninstall the Git Integration for Jira app  – follow [these instructions](/git-integration-for-jira-data-center/uninstall-and-reinstall-gij-self-managed).

3.  Install the Git Integration for Jira app via UPM.

4.  Add all required SSH keys again by uploading them into Git Integration for Jira app ➜ **SSH keys**.

5.  Using the file from Bulk Export, import all your repositories via Bulk Change ➜ **Import Configuration**.

6.  Manually reindex the repositories based on its usage priority or click **Reindex all** to reindex them all at once.

&nbsp;
* * *

[**Prev:** Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[**Next:** Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)

&nbsp;

### More related topics on Getting started for Git administrators

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

**Recommended upgrade method for Git Integration for Jira** (this page)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)

