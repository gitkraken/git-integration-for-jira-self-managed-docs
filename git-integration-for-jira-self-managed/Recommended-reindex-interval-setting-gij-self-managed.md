---

title: Recommended reindex interval setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The configuration of the scheduler jobs are no longer accessible in the Jira administration page. For this case, the Git Integration for Jira app offers Jira administrators this capability via the [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed/) page.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 3.7+</b><br>
        The <b><i>Repository reindexing</i></b> and <b><i>Garbage collection and revision validation checkers</i></b> settings are now moved into the <a href='/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed/'><b>Scheduled Jobs</b></a> settings group.
    </div>
    </div>
</div>

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396353/gitserver-gencfg-scheduled-jobs-repo-ridx-cfg.png?version=1&modificationDate=1630642790933&cacheVersion=1&api=v2&width=680&height=269)

Set the automatic reindex interval frequency value in minutes as required. The default value is **5** minutes.  Min = **1**, Max = **76,861,433,640,456**.

Regardless of the time to index, the reindex interval is the amount of time between the currently completed reindex task until the next reindex.

Improving Jira performance depends on the duration value of the _RevisionIndexJob_. To see the `Last run duration` value, do the following steps:

1.  Go to Jira Administration ➜ **System**.

2.  On the sidebar, select **Scheduler details**.

3.  Scroll to `com.xiplink.jira.git.revisions.RevisionIndexJob`.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396353/ira-system-sched-details-revidxjob-item(c).png?version=1&modificationDate=1630642790449&cacheVersion=1&api=v2&width=646&height=163)
4.  Click **Show more** under the Actions column.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396353/jira-system-sched-details-revisionindexjob(c).png?version=1&modificationDate=1630642790693&cacheVersion=1&api=v2&width=646&height=202)

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

