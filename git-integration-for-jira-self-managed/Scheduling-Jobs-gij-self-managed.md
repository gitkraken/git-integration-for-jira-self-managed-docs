---

title: Scheduling Jobs
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- ADMINISTRATION -->

### Introduction

Scheduling jobs in the [**Git Integration for Jira**](https://marketplace.atlassian.com/4984) app for Jira Server and Data Center (in the **General settings** page) gives Jira administrators control over when jobs run.

<img src='/wp-content/uploads/gij-gitserver-gencfg-scheduler-jobs.png' style='margin:25px auto;max-width:100%;display:block;' alt='Scheduled jobs showing repository indexing and garbage collection' />

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Scheduling rule types</b><br>
        The Git Integration for Jira app for Jira Server and Jira Data Center uses the Atlassian Jira Scheduling API for scheduling jobs. These jobs can be scheduled in two ways:
        <ul style='margin-bottom:0px'>
            <li><b>Scanning interval:</b> Schedule jobs on a regular interval in minutes. If the job is still running, the job will be skipped (and not added to a job queue).</li>
            <li><b>Cron expression:</b> Schedule jobs via cron expression to schedule the jobs to run at specific times on specific days. (<i>Available starting in Git Integration version 3.7+</i>)</li>
        </ul>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We recommend that scheduled jobs be given sufficient time to run completely on a regular basis. Please see section, <a href='#How-to-find-out-how-long-the-job-takes-to-run'>How to find out how long jobs are running</a>.
    </div>
    </div>
</div>

### Scheduled Jobs

#### Repository reindexing

**JOB DESCRIPTION**<br>
When the repository reindexing job runs, the Git Integration for Jira app performs the following operations:

1.  **Auto-Connect integrations (GitHub, GitLab, etc).**

    a.  Perform API call to git server requesting a list of available repositories;

    b.  Clone/remove repositories based on a response from a git server;
    
    c.  Git fetch changes for existing repositories;
    
    d.  An API call requesting pull/merge requests; and lastly,
    
    e.  Index commits from all repositories in the integration.

2.  **Plain git repositories (single repository connections).**
    
    a.  Perform a git fetch changes for each enabled git repository; and then
    
    b.  Index commits.

**DEFAULT VALUE:** **5 minutes**

Job name in Jira Administration ➜ Scheduler Details:<br>
`com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob`

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Recommendations</b><br>
        We recommend that repository reindexing be scheduled no more often than necessary. Ideally, a repository reindexing is scheduled less often (1-2 times a day) and <a href="/git-integration-for-jira-data-center/webhooks-gij-self-managed">Webhooks</a> are configured to trigger indexing of individual repositories. Reindexing can also be triggered using the <a href="/git-integration-for-jira-data-center/reindex-api-gij-self-managed">Reindexing API</a>.
        <div style='margin-top:8px;margin-bottom:-10px;'>For the most control over when reindexing jobs occur, disable webhooks and schedule the reindexing job using a cron expression for the desired time(s) of day.</div>
    </div>
    </div>
</div>

&nbsp;

#### Garbage collection and Revision validation checkers

**JOB DESCRIPTION**<br>
The garbage collection job performs the 'git gc' calls on the cloned repositories copies. It also performs some cleanup and validation routines.

**DEFAULT VALUE:** 1440 minutes (once a day)

Job name in Jira Administration ➜ Scheduler Details:<br>
`com.bigbrassband.jira.git.jiraservices.jobs.GarbageCollectionJob`

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Recommendations</b><br>
        We recommend the Garbage collection and Revision validation checker's job be run approximately once a day. Some of you may decide to run it less often and during a specific quiet period for your Jira server. Ideally, the job would be scheduled when other significant jobs are not scheduled.
    </div>
    </div>
</div>

&nbsp;

### How to find out how long the job takes to run?

To understand how long the above jobs take to run, use the [Indexing queue viewer](com/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/):

1.  On your Jira dashboard menu Git ➜ **Indexing queue**.

2.  Look for the information displayed on the [indexing queue dashboard](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/#indexing-queue-dashboard).

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-gencfg-dashboard-c.png)


&nbsp;

### Data Center considerations

Job scheduling for the Git Integration app for Jira Data Center is generally the same compared to Jira Server, except for the following differences:

*   The reindexing job runs on a single Jira Data Center node (including API requests, git fetch requests, etc) and stores this data in the Jira Shared Storage (`sharedhome`). Then, each Jira Data Center node is notified to index the changes.

*   The Git Integration app schedules the jobs with the Atlassian Jira Scheduler. The Jira Scheduler controls which node carries out the reindexing job.

&nbsp;

### More related Administration articles

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

[Upgrades and migrations within same servver](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed)

**Scheduling jobs** (this page)

[Recommended Jira memory settings](/git-integration-for-jira-data-center/recommended-jira-memory-settings-gij-self-managed)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed)

[Indexing queue explainer](/git-integration-for-jira-data-center/indexing-queue-explainer-gij-self-managed)

