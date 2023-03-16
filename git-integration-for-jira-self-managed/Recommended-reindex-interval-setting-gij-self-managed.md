---

title: Recommended reindex interval setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The configuration of the scheduler jobs are no longer accessible in the Jira administration page. For this case, the Git Integration for Jira app offers Jira administrators this capability via the [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed) page.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 3.7+</b><br>
        The <b><i>Repository reindexing</i></b> and <b><i>Garbage collection and revision validation checkers</i></b> settings are now moved into the <a href='/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed'><b>Scheduled Jobs</b></a> settings group.
    </div>
    </div>
</div>

![](/wp-content/uploads/gij-gitserver-gencfg-scheduled-jobs-repo-ridx-cfg.png)

Set the automatic reindex interval frequency value in minutes as required. The default value is **5** minutes.  Min = **1**, Max = **76,861,433,640,456**.

Regardless of the time to index, the reindex interval is the amount of time between the currently completed reindex task until the next reindex.

Improving Jira performance depends on the duration value of the _RevisionIndexJob_. To see the `Last run duration` value, do the following steps:

1.  Go to <img src='/wp-content/uploads/actions-icon.png' /> Jira Administration ➜ **System**.

2.  On the sidebar, select **Scheduler details**.

3.  Scroll to `com.xiplink.jira.git.revisions.RevisionIndexJob`.

    ![](/wp-content/uploads/gij-ira-system-sched-details-revidxjob-item-c.png)

4.  Click **Show more** under the Actions column.

    ![](/wp-content/uploads/gij-jira-system-sched-details-revisionindexjob-c.png)

<br>

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.13+</b> The other recommended method to see the value of the <code>Last run duration</code> is to use the <a href='/git-integration-for-jira-data-center/Indexing-queue-viewer-gij-self-managed'>Indexing queue viewer</a>.

<br>

If the `Last run duration` value shows `3 minutes` _or greater_, we recommend to increase the reindex interval.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The reindex interval must be greater or equal to the <code>Last run duration</code> value of <i>RevisionIndexJob</i> to improve Jira performance. For example, if the <code>Last run duration</code> value is <b>20 minutes</b>, set the Reindex interval value to <b>20 minutes or more</b> in the General settings page.
    </div>
    </div>
</div>
<br>

<br>
<br>

[**Prev:** Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-api-to-trigger-indexing-gij-self-managed)

[**Next:** Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More related articles on Git for Jira administrators

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


