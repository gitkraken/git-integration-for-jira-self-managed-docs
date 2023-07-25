---

title: Connection Reset when Accessing the Database
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Problem

Errors/failures in the Git Integration for Jira application are seen sporadically. Automatic reindexing may stop.

### Diagnosis

Jira admins will see a message similar to the one below in the Jira log: /application-logs/atlassian-jira.log:

```java
2019-08-04 07:11:11,173 Caesium-1-1 ERROR ServiceRunner     [c.a.s.caesium.impl.CaesiumSchedulerService] Unhandled exception during the attempt to execute job 'com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob'; will attempt recovery in 60 seconds
com.atlassian.jira.exception.DataAccessException: org.ofbiz.core.entity.GenericDataSourceException: SQL Exception while executing the following:SELECT ID, JOB_ID, JOB_RUNNER_KEY, SCHED_TYPE, INTERVAL_MILLIS, FIRST_RUN, CRON_EXPRESSION, TIME_ZONE, NEXT_RUN, VERSION, PARAMETERS FROM dbo.clusteredjob WHERE JOB_ID=? (Connection reset by peer: socket write error)
```

### Cause

When a database server reboots or a network failure has occurred, all connections in the database connection pool are broken, and JIRA would normally need restarting to recreate those connections. See Atlassian's [Surviving Connection Closures](https://confluence.atlassian.com/jira/surviving-connection-closures-120050.html) documentation.

### Solution

See [Atlassian's Connection Reset when Accessing the Database](https://confluence.atlassian.com/jirakb/connection-reset-when-accessing-the-database-284366332.html) article.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

&nbsp;

### More articles about troubleshooting, workarounds and solutions

[Why I am getting the error, “git-upload-pack not permitted”?](/git-integration-for-jira-data-center/why-i-am-getting-the-error-git-upload-pack-not-permitted-gij-self-managed/)

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/avoid-outofmemory-exceptions-by-configuring-or-memory-allocation-with-jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

**Connection Reset when Accessing the Database** (this page)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

[Duplicate entry 0 for key PRIMARY exceptions in log](/git-integration-for-jira-data-center/Duplicate-entry-0-for-key-PRIMARY-exceptions-in-log-gij-self-managed)

[Error while reindexing – Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Gitolite integration: Why the Git integration app not see the master branch?](/git-integration-for-jira-data-center/Gitolite-integration--why-the-Git-integration-app-not-see-the-master-branch-gij-self-managed)

[Health Check: Database Collation](/git-integration-for-jira-data-center/Health-check--database-collation-gij-self-managed)

[Indexing error – Too many open files](/git-integration-for-jira-data-center/Indexing-error-Too-many-open-files-gij-self-managed)

[Installation fails when installing manually](/git-integration-for-jira-data-center/Installation-fails-when-installing-manually-gij-self-managed)

[Jira index error: IndexNotFoundException: no segments* file found](/git-integration-for-jira-data-center/Jira-index-error--IndexNotFoundException--no-segments-file-found)

[Malformed input or input contains unmappable characters](/git-integration-for-jira-data-center/Malformed-input-or-input-contains-unmappable-characters-gij-self-managed)

[Personal access token failing Azure DevOps integration with Not Authorized error](/git-integration-for-jira-data-center/Personal-access-token-failing-azure-devops-integration-with-Not-Authorized-error-gij-self-managed)

[Problems with shared home on Azure Storage](/git-integration-for-jira-data-center/Problems-with-shared-home-on-azure-storage-gij-self-managed)

[Pull request index error: org.json.JSONException](/git-integration-for-jira-data-center/Pull-request-index-error--JSONException-gij-self-managed)

[Repositories missing from Azure DevOps integration](/git-integration-for-jira-data-center/Repositories-missing-from-azure-devops-integration-gij-self-managed)

["Service proxy has been destroyed" exceptions in log](/git-integration-for-jira-data-center/service-proxy-has-been-destroyed-exceptions-in-log-gij-self-managed)

[SQLException 'Incorrect string value' in merge requests](/git-integration-for-jira-data-center/sqlexception-incorrect-string-value-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

<br>
<br>

