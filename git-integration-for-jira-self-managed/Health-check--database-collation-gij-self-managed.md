---

title: Health Check - Database Collation
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Problem

Incorrect database collation setting can cause errors/failures in the Git Integration for Jira application.

### Diagnosis

Jira admins will see a message similar to the one below in the Jira log: `/healthchecks/healthcheckResults.txt`:

**Health Check: Collation**

```json
Name: Collation
Is healthy: false
Failure reason: The database collation 'utf8_bin' and table collation 'utf8_bin' are not supported by Jira.
Severity: CRITICAL
```

### Cause

From Atlassian:

>   This check retrieves the collation of the database and determines if it is within the list of collations supported by Atlassian. The Check will not assess collation when using an embedded (H2/HSQL) database and will fail if it cannot successfully identify the database (MariaDB is being used, for example). It fails if the collation does not match what we expect, or it cannot be retrieved due to an exception checking it. This health check does not report any warnings for Postgres database users. If you experience an error on this health check, the steps in the resolution should be applied.

[Atlassian - Health Check: Database Collation](https://confluence.atlassian.com/jirakb/health-check-database-collation-790955315.html)

### Solution

Follow instructions from Atlassian:

1.  MySQL: [Health Check: Database Collation in MySQL](https://confluence.atlassian.com/jirakb/health-check-database-collation-in-mysql-943951422.html)

2.  Microsoft SQL Server: [Health Check: Database Collation in Microsoft SQL Server](https://confluence.atlassian.com/display/JIRAKB/Health+Check%3A+Database+Collation+in+Microsoft+SQL+Server)

3.  PostgreSQL: [Health Check: Database Collation in PostgreSQL](https://confluence.atlassian.com/display/JIRAKB/Health+Check%3A+Database+Collation+in+PostgreSQL)

4.  Oracle: Health Check: [Database Collation in Oracle](https://confluence.atlassian.com/display/JIRAKB/Health+Check%3A+Database+Collation+in+Oracle)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

&nbsp;

### More articles about troubleshooting, workarounds and solutions

[Why I am getting the error, “git-upload-pack not permitted”?](/git-integration-for-jira-data-center/why-i-am-getting-the-error-git-upload-pack-not-permitted-gij-self-managed/)

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/avoid-outofmemory-exceptions-by-configuring-or-memory-allocation-with-jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

[Duplicate entry 0 for key PRIMARY exceptions in log](/git-integration-for-jira-data-center/Duplicate-entry-0-for-key-PRIMARY-exceptions-in-log-gij-self-managed)

[Error while reindexing – Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Error creating git branches and also using NFS](/git-integration-for-jira-data-center/error-creating-git-branches-gitlabpropertiesnotinitializedexception-and-using-nfs-gij-self-managed)

[Fix performance issues for nested cloned repositories with enabled Git Service Permissions mode](/git-integration-for-jira-data-center/Fix-performance-issues-for-nested-cloned-repositories-with-enabled-secure-mode-gij-self-managed)

[Fixing reindex issues using Indexing Queue Viewer](/git-integration-for-jira-data-center/fixing-reindex-issues-using-indexing-queue-viewer)

[Gitolite integration: Why the Git integration app not see the master branch?](/git-integration-for-jira-data-center/Gitolite-integration--why-the-Git-integration-app-not-see-the-master-branch-gij-self-managed)

**Health Check: Database Collation** (this page)

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

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

