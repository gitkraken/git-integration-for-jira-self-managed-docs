---

title: Scheduled jobs
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This setting is part of the [**General Settings**](/wiki/spaces/GIJDC/pages/966852655/General+Settings) configuration page.


This setting allows administrators to configure duration of jobs and the GC checkers.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795958/gitserver-gencfg-scheduler-jobs.png?version=2&modificationDate=1647774645146&cacheVersion=1&api=v2&width=680&height=317)

JIRA SERVER DATA CENTER

Scheduling jobs gives administrators control over when jobs run. These jobs can be scheduled in two ways:

*   **Scanning interval** – where jobs are scheduled on regular interval in minutes.

*   **Cron expression** – where jobs are scheduled via cron expression to run at specific timetables.


We recommend that scheduled jobs be given sufficient time to run completely on a regular basis.

Look at the Git Integration app job names in **Jira Administration** ➜ **System** ➜ **Scheduler details**:

1.  `com.bigbrassband.jira.git.jiraservices.jobs.GarbageCollectionJob`

2.  `com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob`


Expand them to observe schedule, duration, last run, duration, and next run.

## Scheduled Jobs

VERSION 3.7+ **Repository reindexing** and **Garbage collection and revision validation checkers** settings are now moved into the _Scheduled Jobs_ settings group.

### Repository reindexing

**Reindex interval**  –  Set the automatic reindex interval frequency value in minutes as required.  Default value is _**5 minutes**_.

Configuration of the scheduler jobs are no longer accessible in the Jira administration page.  For this case, the Git for Jira app offers Jira administrators this capability via the **General** screen.  Minimum value is **1**.  Maximum value is **76,861,433,640,456**.  Only whole numbers are allowed.

### Garbage collection and revision validation checkers

**Job interval**  –  Set the number of minutes that will elapse before a repository is checked to see if it should be garbage collected.  The default value is _**1440 minutes**_.

For detailed information, see introductory article on [Scheduling Jobs](/wiki/spaces/GIJDC/pages/756056197/Scheduling+Jobs).

* * *

### More on general settings

*   Page:

    [Git roll up issue tab](/wiki/spaces/GIJDC/pages/1207828678/Git+roll+up+issue+tab) (Git Integration for Jira Data Center)

*   Page:

    [Git commits issue and project tabs](/wiki/spaces/GIJDC/pages/1207828697/Git+commits+issue+and+project+tabs) (Git Integration for Jira Data Center)

*   Page:

    [Git integration features](/wiki/spaces/GIJDC/pages/1207795905/Git+integration+features) (Git Integration for Jira Data Center)

*   Page:

    [Branch and pull request settings (formerly Git Integration Options)](/wiki/spaces/GIJDC/pages/1207828745) (Git Integration for Jira Data Center)

*   Page:

    [Email settings](/wiki/spaces/GIJDC/pages/1207795941/Email+settings) (Git Integration for Jira Data Center)

*   Page:

    [Scheduled jobs](/wiki/spaces/GIJDC/pages/1207795958/Scheduled+jobs) (Git Integration for Jira Data Center)

*   Page:

    [Audit log settings](/wiki/spaces/GIJDC/pages/1207828866/Audit+log+settings) (Git Integration for Jira Data Center)

*   Page:

    [General settings](/wiki/spaces/GIJDC/pages/1930398111/General+settings) (Git Integration for Jira Data Center)

*   Page:

    [Repository Browser general setting](/wiki/spaces/GIJDC/pages/1947140158/Repository+Browser+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Source Code Diff Viewing general setting](/wiki/spaces/GIJDC/pages/1947140173/Source+Code+Diff+Viewing+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Require User PAT general setting](/wiki/spaces/GIJDC/pages/1947107395/Require+User+PAT+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Enable Automation for Jira general setting](/wiki/spaces/GIJDC/pages/2045149338/Enable+Automation+for+Jira+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Enforce Git service permissions](/wiki/spaces/GIJDC/pages/2091810842/Enforce+Git+service+permissions) (Git Integration for Jira Data Center)

*   Page:

    [Per Node Repository Indexing](/wiki/spaces/GIJDC/pages/2095775749/Per+Node+Repository+Indexing) (Git Integration for Jira Data Center)