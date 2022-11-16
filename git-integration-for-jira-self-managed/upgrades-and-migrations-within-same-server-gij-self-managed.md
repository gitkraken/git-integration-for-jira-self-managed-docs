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

## Before you upgrade/migrate

1.  We recommend Jira admins upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

2.  Verify that configured integrations and repositories in **Manage Git repositories** screen are correct and index properly.

3.  If you are upgrading the version of Jira during the migration - review the [**Upgrading Jira Applications article from Atlassian**](https://confluence.atlassian.com/adminjiraserver/upgrading-jira-applications-938846936.html).

4.  Backup your Git Integration for Jira integration and repository configurations using the [Export function of the Bulk Change feature](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed).

## Upgrade/migrate

Follow the [standard instructions from Atlassian for upgrading on the same server](https://confluence.atlassian.com/adminjiraserver/upgrading-jira-applications-938846936.html) (select your Jira version).

## After you migrate

Verify that configured integrations and repositories in the **Manage Git repositories** screen are correct and index properly.

<p>&nbsp;</p>

## More related Administration articles

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

**Upgrades and migrations within same servver** (this page)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed)

[Scheduling jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed)

[Recommended Jira memory settings](/git-integration-for-jira-data-center/recommended-jira-memory-settings-gij-self-managed)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed)

[Indexing queue explainer](/git-integration-for-jira-data-center/indexing-queue-explainer-gij-self-managed)

