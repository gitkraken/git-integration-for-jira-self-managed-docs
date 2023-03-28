---

title: Migrating from Jira 8 to Jira 9
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Upgrading from Jira 8 to Jira 9 provides new features, performance and stability. However, there are some small things that need to be considered for the transition.

## Resetting indexes

After upgrading from Jira 8 to Jira 9, administrators must re-create all indexes using the Reset index action command for all repositories or integrations.

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small'>DATA CENTER</b> Upgrading to Jira 9 in a clustered Data Center configuration will involve some downtime on the primary node, This allows Jira 9 to generate and reindex versions for all issues, comments, and worklogs in the system while also performing a full foreground reindex. For minimal downtime upgrade procedure, See Atlassian upgrade tips – [Learn how to perform a minimal downtime upgrade to Jira 9.0](https://confluence.atlassian.com/jirakb/jira-8-to-jira-9-minimal-downtime-upgrade-1115137250.html).

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>From Atlassian:</b><br>
        Legacy index snapshots are not compatible with Jira 9.0 and using them to restore the index may cause search consistency and performance issues. As such, we recommend that you delete the legacy snapshot directories and their content manually when the upgrade is completed.
    </div>
    </div>
</div>
<br>

## Commit tab sort order

In Jira 9.x, comments are now sorted from newest to oldest by default. If the Git Integration for Jira _**Reverse commit tab sort order**_ General setting is **enabled**, this results in git commits sorted from oldest to newest. This behavior is technically correct because it corresponds to the settings. However, the sort order where you get used to after the upgrade becomes reversed.

<img src='/wp-content/uploads/gij-gitserver-general-settings-reverse-commit-order-c.png' height=291 width=677 style='display:block;margin:25px auto;max-width:100%' />

This is because:

*   Jira 8 sorts issue comments from oldest to newest by default.
*   Jira 9 sorts issue comments from newest to oldest by default

We recommend that after migration from Jira 8 to Jira 9, administrators should turn off the "**Reverse commit tab sort order**" option in General settings. If this is a new Jira 9 installation then nothing is required.

## Other Jira 9 migration preparations

See more information on preparing for Jira 9 migration at [Atlassian Jira 9 transition](https://confluence.atlassian.com/jiracore/preparing-for-jira-9-0-1115661092.html).

