---

title: Scheduling Jobs
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Introduction

Scheduling jobs in the [**Git Integration for Jira**](https://marketplace.atlassian.com/4984) app for Jira Server and Data Center (in the **General settings** page) gives Jira administrators control over when jobs run.

![Scheduled jobs showing repository indexing and gc](https://bigbrassband.atlassian.net/wiki/download/attachments/756056197/general-settings-scheduled-jobs.png?version=1&modificationDate=1600179577661&cacheVersion=1&api=v2)

**Scheduling rule types**
The Git Integration for Jira app for Jira Server and Jira Data Center uses the Atlassian Jira Scheduling API for scheduling jobs. These jobs can be scheduled in two ways:

*   **Scanning interval:** Schedule jobs on a regular interval in minutes. If the job is still running, the job will be skipped (and not added to a job queue).

*   **Cron expression:** Schedule jobs via cron expression to schedule the jobs to run at specific times on specific days**.** (_Available starting in Git Integration version 3.7+)_


We recommend that scheduled jobs be given sufficient time to run completely on a regular basis. Please see section, [How to find out how long jobs are running](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/750288897/Scheduling+jobs#How-to-find-out-how-long-the-job-takes-to-run).

# Scheduled Jobs

### Repository reindexing
**JOB DESCRIPTION**<br><br>When the repository reindexing job runs, the Git Integration for Jira app performs the following operations:
1.  **Auto-Connect integrations (GitHub, GitLab, etc).**
    1.  Perform API call to git server requesting a list of available repositories;
    2.  Clone/remove repositories based on a response from a git server;
    3.  Git fetch changes for existing repositories;
    4.  An API call requesting pull/merge requests; and lastly,
    5.  Index commits from all repositories in the integration.
2.  **Plain git repositories (single repository connections).**
    1.  Perform a git fetch changes for each enabled git repository; and then
    2.  Index commits.

**DEFAULT VALUE:** **5 minutes**
Job name in Jira Administration ➜ Scheduler Details:<br><br>```java<br>com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob<br>```
**Recommendations**
We recommend that repository reindexing be scheduled no more often than necessary. Ideally, a repository reindexing is scheduled less often (1-2 times a day) and [Webhooks](/git-integration-for-jira-self-managed/webhooks-gij-self-managed) are configured to trigger indexing of individual repositories. Reindexing can also be triggered using the [Reindexing API](/git-integration-for-jira-self-managed/reindex-api-gij-self-managed).<br><br>For the most control over when reindexing jobs occur, disable webhooks and schedule the reindexing job using a cron expression for the desired time(s) of day.

### Garbage collection and Revision validation checkers |
**JOB DESCRIPTION**<br><br>The garbage collection job performs the ‘git gc’ calls on the cloned repositories copies. It also performs some cleanup and validation routines.

**DEFAULT VALUE:** 1440 minutes (once a day)
Job name in Jira Administration ➜ Scheduler Details:<br><br>```java<br>com.bigbrassband.jira.git.jiraservices.jobs.GarbageCollectionJob<br>```

**Recommendations**  <br>We recommend the Garbage collection and Revision validation checker's job be run approximately once a day. Some of you may decide to run it less often and during a specific quiet period for your Jira server. Ideally, the job would be scheduled when other significant jobs are not scheduled.

# How to find out how long the job takes to run

To understand how long the above jobs take to run:

1.  Navigate to the Jira Administration ➜ **Scheduler Details** page.

2.  Look up the `Job name` posted above.

3.  Expand the job name (show more) and observe the schedule, duration, last run, duration, and next run. The duration indicates how long the **last scheduled job** required to run completely **Note:** manually or API reindexed jobs will not show here).


When the Reindex job duration is measured in a few tens of milliseconds, this means that the reindex job was still running from the last scheduled reindex job. We recommend that the scheduled job be given more time so that jobs do not overlap.

# Data Center considerations

Job scheduling for the Git Integration app for Jira Data Center is generally the same compared to Jira Server, except for the following differences:

*   The reindexing job runs on a single Jira Data Center node (including API requests, git fetch requests, etc) and stores this data in the Jira Shared Storage (`sharedhome`). Then, each Jira Data Center node is notified to index the changes.

*   The Git Integration app schedules the jobs with the Atlassian Jira Scheduler. The Jira Scheduler controls which node carries out the reindexing job.


