---

title: Scheduled jobs
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>
<br>

This setting allows administrators to configure duration of jobs and the GC checkers.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795958/gitserver-gencfg-scheduler-jobs.png?version=2&modificationDate=1647774645146&cacheVersion=1&api=v2&width=680&height=317)

<br>

Scheduling jobs gives administrators control over when jobs run. These jobs can be scheduled in two ways:

*   **Scanning interval** – where jobs are scheduled on regular interval in minutes.

*   **Cron expression** – where jobs are scheduled via cron expression to run at specific timetables.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We recommend that scheduled jobs be given sufficient time to run completely on a regular basis.<br><br>
        Look at the Git Integration app job names in Jira Administration ➜ System ➜ <b>Scheduler details</b>:
        <ul>
            <li><code>com.bigbrassband.jira.git.jiraservices.jobs.GarbageCollectionJob</code></li>
            <li><code>com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob</code></li>
        </ul>
        Expand them to observe schedule, duration, last run, duration, and next run.
    </div>
    </div>
</div>
<br>

## Scheduled Jobs

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 3.7+</b><br>
        <b>Repository reindexing</b> and <b>Garbage collection and revision validation checkers</b> settings are now moved into the <i>Scheduled Jobs</i> settings group.
    </div>
    </div>
</div>
<br>

### Repository reindexing

**Reindex interval**  –  Set the automatic reindex interval frequency value in minutes as required. Default value is _**5 minutes**_.

Configuration of the scheduler jobs are no longer accessible in the Jira administration page. For this case, the Git for Jira app offers Jira administrators this capability via the **General** screen. Minimum value is **1**. Maximum value is **76,861,433,640,456**. Only whole numbers are allowed.

### Garbage collection and revision validation checkers

**Job interval**  –  Set the number of minutes that will elapse before a repository is checked to see if it should be garbage collected.  The default value is _**1440 minutes**_.

For detailed information, see introductory article on [Scheduling Jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed).

