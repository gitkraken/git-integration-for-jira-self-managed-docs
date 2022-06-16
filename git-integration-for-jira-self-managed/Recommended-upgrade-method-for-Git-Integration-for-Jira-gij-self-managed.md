---

title: Recommended upgrade method for Git Integration for Jira
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For full list of features, version history and supported Jira version of the Git for Jira app, see <a href='https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions'><b>Git Integration for Jira app Version History</b></a>.
    </div>
    </div>
</div>

If you have installed the Git Integration for Jira app with versions prior to v2.10.2, perform the following steps to upgrade with minimal risk:

1.  Do the upgrade at night – when the number of Jira users is minimal.

2.  Make backups (see [below](#making-backups)).

3.  Upgrade the Git for Jira app to the latest version.

## Making backups

We strongly advise to make backups to avoid operations disaster.

### Make a Jira backup (recommended)

The Git for Jira app upgrade only updates its components.  Thus, it has no adverse effect to Jira. It is still better to make a backup of your Jira before any app upgrade as a safety measure.

### Make a Git Integration for Jira app configuration backup (recommended)

Make sure to do a backup of the Git repositories connection configuration.

1.  Perform a bulk export of your existing repositories or integration via the Git Integration for Jira app repositories configuration page.

    *   On your Jira dashboard menu Git ➜ **Manage repositories**.

    *   Click the **Bulk Change** button drop down then select **1\. Export configuration**. For detailed steps, see [Bulk Change - Export Configuration](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed/).

        ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396509/bulk-export-loc-test(c).png?version=1&modificationDate=1630642797003&cacheVersion=1&api=v2)
2.  Make sure that you have all the required SSH keys uploaded to the Git Integration for Jira app

    *   On your Jira dashboard, go to menu Git ➜ **Manage repositories**.

    *   Click **SSH keys** on the sidebar. This will make seamless connection of the SSH git repositories to Jira via [Bulk Change - Import Configuration](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed/).

        ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396509/add-ssh-key-loc-test(c).png?version=1&modificationDate=1630642797244&cacheVersion=1&api=v2)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you have several large repositories and have a problem with exceeded timeout, we recommend that you use our <a href='/git-integration-for-jira-data-center/tracked-folders-gij-self-managed/'>Tracked folders integration</a> feature to scan local folders at once and import repositories automatically.
    </div>
    </div>
</div>
<br>

## Unisntall | Reinstall (Not recommended)

Another option is to completely uninstall then reinstall the Git for Jira app. However, this will result in Jira running on a clean state:

1.  Backup the Git repositories configuration via the Git for Jira app Bulk Export.

2.  Fully uninstall the Git Integration for Jira app  – follow [these instructions](/git-integration-for-jira-data-center/uninstall-and-reinstall-gij-self-managed/).

3.  Install the Git Integration for Jira app via UPM.

4.  Add all required SSH keys again by uploading them into Git Integration for Jira app ➜ **SSH keys**.

5.  Using the file from Bulk Export, import all your repositories via Bulk Change ➜ **Import Configuration**.

6.  Manually reindex the repositories based on its usage priority or click **Reindex all** to reindex them all at once.

