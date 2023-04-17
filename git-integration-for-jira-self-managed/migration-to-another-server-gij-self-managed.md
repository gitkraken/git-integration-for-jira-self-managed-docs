---

title: Migration to another server
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- ADMINISTRATION -->

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

### Before you migrate

We recommend Jira admins to upgrade to the latest version of [Git Integration app from the Atlassian Marketplace](https://marketplace.atlassian.com/apps/4984/git-integration-for-jira?hosting=server&tab=versions).

Run the instance for some time (a few days or weeks) and once the testing is stable – then do the migration.

### Upgrade/migrate

Follow the [standard instructions from Atlassian on migrating to another server](https://confluence.atlassian.com/adminjiraserver073/migrating-jira-applications-to-another-server-861253107.html) (select your Jira version).

No extra steps are required.

### After you migrate

Verify that configured integrations and repositories in the **Manage Git repositories** screen are correct and index properly.

<p>&nbsp;</p>

## More related Administration articles

[Tips for Jira Administrators](/git-integration-for-jira-data-center/tips-for-jira-admins-gij-self-managed/)

[Migrating from Jira 8 to Jira 9](/git-integration-for-jira-data-center/migrating-jira7-to-jira9-gij-self-managed/)

[Upgrades and migrations within same servver](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed)

**Migration to another server** (this page)

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

[Recommended Jira memory settings](/git-integration-for-jira-data-center/recommended-jira-memory-settings-gij-self-managed)

[Scheduling jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed)

[Administration FAQ](/git-integration-for-jira-self-managed/administration-faq-gij-self-managed)

[Indexing queue explainer](/git-integration-for-jira-data-center/indexing-queue-explainer-gij-self-managed)

