---

title: Recommended reindex interval setting
description: Set the automatic reindex interval in General settings and compare it with the last run duration in the indexing queue to improve Jira performance.
product: Git Integration for Jira Data Center
feature: Indexing (Reindex)
content_type: how-to
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [reindex interval, scheduled jobs, indexing queue, last run duration, performance]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Recommended reindex interval setting"
    nav_order: 70
    nav_parent: "getting-started-for-git-administrators-gij-self-managed"
    page_type: "content"
---

The configuration of the scheduler jobs are no longer accessible in the Jira administration page. For this case, the Git Integration for Jira app offers Jira administrators this capability via the [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed) page.

> **Note:** <b>VERSION 3.7+</b><br>
> The <b><i>Repository reindexing</i></b> and <b><i>Garbage collection and revision validation checkers</i></b> settings are now moved into the <a href='/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed'><b>Scheduled Jobs</b></a> settings group.

&nbsp;

![](/wp-content/uploads/gij-gitserver-gencfg-scheduled-jobs-repo-ridx-cfg.png)

Set the automatic reindex interval frequency value in minutes as required. The default value is **5 minutes**.  Min = **1**, Max = **76,861,433,640,456**.

> **Info:** <b>VERSION 4.0+</b><br>
> Starting from v4.0+ of the Git Integration for Jira app, the Reindex All task became much simplier. Reindex tasks are added for each repository and finishes all tasks without waiting for the completion of the new index tasks.

&nbsp;

Since indexing queue does not allow duplicate tasks, Reindex All task will not be processed twice.

> **Info:** Improving Jira performance depends on the duration value of the scheduled jobs. That's why, it's important to set the Reindex interval to greater than the Last run duraton value.

&nbsp;

To see the `Last run duration` value, do the following steps:

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.13+</b>

1.  Go to **Indexing queue viewer** (Jira dashboard menu Git ➜ _**Indexing queue**_).

    ![](/wp-content/uploads/gij-gitserver-indexing-queue-mgr-loc-01.png)

2.  On the indexing queue dashboard, look under **Scheduled time for indexing, minutes** or **Garbage collection, minutes** panels to see the `Last run duration` value.

    ![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-gencfg-dashboard-c.png)

&nbsp;

If the `Last run duration` value shows `3 minutes` _or greater_, we recommend to increase the reindex interval.

> **Tip:** The reindex interval must be greater or equal to the <code>Last run duration</code> value of <i>RevisionIndexJob</i> to improve Jira performance. For example, if the <code>Last run duration</code> value is <b>19 minutes</b>, set the Reindex interval value to <b>20 minutes or more</b> in the General settings page.

&nbsp;
* * *

[**Prev:** Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-api-to-trigger-indexing-gij-self-managed)

[**Next:** Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

&nbsp;

### More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

**Recommended reindex interval setting** (this page)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)


