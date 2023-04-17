---

title: Upgrades and migrations within same server
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- ADMINISTRATION -->

The following instructions are for in-place upgrades + migrations of Jira on the same server (typically when upgrading version of Jira). See [Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed) instructions for migrations to another server.


<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We strongly recommend performing your migration in a test environment first. Do not migrate your production Jira server application until you are satisfied that your test environment upgrade is successful.
    </div>
    </div>
</div>
<br>

# GitServer ➜ GitServer

Do note that the steps outlined in this section are also applicable to Jira Data Center instances.

## Migration within the same server when Jira HOME path is unchanged

### Before you upgrade/migrate

1.  We recommend Jira admins to upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

2.  Run the instance for some time (a few days) and once the testing is stable – then do the migration.

### Upgrade/migrate

Please follow the [standard instructions from Atlassian for upgrading on the same server](https://confluence.atlassian.com/adminjiraserver073/migrating-jira-applications-to-another-server-861253107.html) (select your Jira version).

No extra steps are required.

### After you migrate

Verify that configured integrations and repositories in the **Manage Git repositories** screen are correct and indexed properly.

## Migration within the same server when Jira HOME path is changed (Classic)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Pros:</b><br>
        Easy for migration.<br><br>
        <b>Cons:</b><br>
        <ul>
            <li>You will have to set up all your repository settings again (including mapping to projects and repository watchers.</li>
            <li>Users are required to re-setup their PATs after upgrade/migration.</li>
            <li>Afterwards, do a full reindexing for all your repositories.</li>
        </ul>
    </div>
    </div>
</div>

### Before you migrate

1.  We recommend Jira admins to upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

2.  Run it for some time (a few days) and once the testing is stable – then do the migration.

3.  Use the Git Integration [Bulk Change export](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed/) to backup the integration settings and extract/save credentials for repositories.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Please note that bulk export data contains lines for all repositories -- including those that were automatically created within integrations. You need only the data for 'top-level' repositories and integration to reconnect to all your repositories.
    </div>
    </div>
</div>

### Upgrade/migrate

Please follow the [standard instructions from Atlassian for upgrading on the same server](https://confluence.atlassian.com/adminjiraserver073/migrating-jira-applications-to-another-server-861253107.html) (select your Jira version).

No extra steps are required.

### After you migrate

1.  With Git Integration for Jira app, **remove all repositories** in Manage Git repositories.

2.  Remove all repositories data from the `/data/git-plugin/` folder in the new Jira home directory (i.e. remove all folders which have the next format: `'<repositoryID>_<repositoryName>'`)

3.  Reconnect to all integrations/repositories using new or existing credentials. Your stored SSH keys will stil be migrated automatically.

## Migration within the same server when Jira HOME path is changed (Recommended)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Pros:</b><br>
        <ul>
            <li>Repository settings and user’s PATs are preserved.</li>
            <li>Reconnection of all integrations is not required.</li>
            <li>No extra steps after bulk import post-migration</li>
        </ul>
        <b>Cons:</b><br>
        <ul>
            <li>You will have to change internal configuration files for the GitServer plugin. This should be done with extreme care.</li>
        </ul>
    </div>
    </div>
</div>

### Before you migrate

1.  We recommend Jira admins to upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

2.  Run it for some time (a few days) and once the testing is stable – then do the migration.

3.  Use the Git Integration [Bulk Change export](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed/) to backup the integration settings.

4.  Open the backup file with your favorite text editor and replace all occurrences of the **old Jira home path** with the **new Jira home path**.

### Upgrade/migrate

Please follow the [standard instructions from Atlassian for upgrading on the same server](https://confluence.atlassian.com/adminjiraserver073/migrating-jira-applications-to-another-server-861253107.html) (select your Jira version).

No extra steps are required.

### After you migrate

Use Git Integration for Jira app: [Bulk import](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed/) to load the updated backup file with the new Jira home path. This should reconnect all existing integration repositories as it was before the backup.

## GitServer ➜ GitDataCenter

If you are thinking of migrating your server installtion to Data Center, read the guidelines below to help you get up and running.

### Before you migrate

1.  We recommend Jira admins to upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

2.  Run it for some time (a few days) and once the testing is stable – then do the migration.

### Migration

*   [Migrate from Server to Data Center](https://confluence.atlassian.com/enterprise/moving-from-server-to-data-center-953127136.html) – If you currently have apps installed on your server installation, you’ll also need to upgrade your apps to the Data Center version.

*   [Atlassian Data Center migration plan](https://confluence.atlassian.com/enterprise/atlassian-data-center-migration-plan-935363952.html) – Gives some guidance on overall process, organizational preparedness, estimated time frames, and app compatibility.

*   [Atlassian Data Center migration checklist](https://confluence.atlassian.com/enterprise/atlassian-data-center-migration-checklist-935383667.html) – Provides useful tests and checks to perform throughout the moving process.

*   [Getting started with Atlassian Data Center](https://confluence.atlassian.com/enterprise/how-to-set-up-atlassian-data-center-954260161.html) – Migration is done? Read this to learn how to setup and configure Jira Data Center.

### After you migrate

Atlassian recommends using the applicable database backup tools in general BUT for migrations - Atlassian recommends using the [Jira XML backup](https://confluence.atlassian.com/adminjiraserver/backing-up-data-938847673.html) (helps when migrating to new OS / database / version of Jira)

<p>&nbsp;</p>

## More related Administration articles

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

**Upgrades and migrations within same servver** (this page)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed)

[Scheduling jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed)

[Recommended Jira memory settings](/git-integration-for-jira-data-center/recommended-jira-memory-settings-gij-self-managed)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed)

[Indexing queue explainer](/git-integration-for-jira-data-center/indexing-queue-explainer-gij-self-managed)

