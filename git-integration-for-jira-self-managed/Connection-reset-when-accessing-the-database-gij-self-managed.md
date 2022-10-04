---

title: Connection Reset when Accessing the Database
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## Problem

Errors/failures in the Git Integration for Jira application are seen sporadically. Automatic reindexing may stop.

## Diagnosis

Jira admins will see a message similar to the one below in the Jira log: /application-logs/atlassian-jira.log:

```java
2019-08-04 07:11:11,173 Caesium-1-1 ERROR ServiceRunner     [c.a.s.caesium.impl.CaesiumSchedulerService] Unhandled exception during the attempt to execute job 'com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob'; will attempt recovery in 60 seconds
com.atlassian.jira.exception.DataAccessException: org.ofbiz.core.entity.GenericDataSourceException: SQL Exception while executing the following:SELECT ID, JOB_ID, JOB_RUNNER_KEY, SCHED_TYPE, INTERVAL_MILLIS, FIRST_RUN, CRON_EXPRESSION, TIME_ZONE, NEXT_RUN, VERSION, PARAMETERS FROM dbo.clusteredjob WHERE JOB_ID=? (Connection reset by peer: socket write error)
```

## Cause

When a database server reboots or a network failure has occurred, all connections in the database connection pool are broken, and JIRA would normally need restarting to recreate those connections. See Atlassian's [Surviving Connection Closures](https://confluence.atlassian.com/jira/surviving-connection-closures-120050.html) documentation.

## Solution

See [Atlassian's Connection Reset when Accessing the Database](https://confluence.atlassian.com/jirakb/connection-reset-when-accessing-the-database-284366332.html) article.


<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='gijsupport@bigbrassband.com'>gijsupport@bigbrassband.com</a>.
    </div>
    </div>
</div>
<br>

