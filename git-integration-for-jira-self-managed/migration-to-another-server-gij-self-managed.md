---

title: Migration to another server
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The following instructions are for migrations of Jira to a different server. See [Upgrades and migrations within same server](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed) instructions for in-place upgrades or migrations.


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

## Before you migrate

1.  We recommend Jira admins upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

2.  Verify that configured integrations and repositories in **Manage Git repositories** screen are correct and index properly.

3.  If you are upgrading the version of Jira during the migration - review the [**Upgrading Jira Applications article from Atlassian**](https://confluence.atlassian.com/adminjiraserver/upgrading-jira-applications-938846936.html).

4.  Backup your Git Integration for Jira integration and repository configurations using the [Export function of the Bulk Change feature](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed/).

## Upgrade/migrate

Follow the [standard instructions from Atlassian for upgrading on the same server](https://confluence.atlassian.com/adminjiraserver/upgrading-jira-applications-938846936.html) (select your Jira version).

## After you migrate

Verify that configured integrations and repositories in the **Manage Git repositories** screen are correct and index properly.

