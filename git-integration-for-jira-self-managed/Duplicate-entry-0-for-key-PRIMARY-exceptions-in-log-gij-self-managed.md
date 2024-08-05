---

title: Duplicate entry 0 for key PRIMARY exceptions in log
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Problem

After Jira installation or configuration changes - the following errors appear. Errors/failures in the Git Integration for Jira application are seen sporadically.

### Diagnosis

Jira admins will see a message similar to the one below in the Jira log: /application-logs/atlassian-jira.log:

```java
2014-06-23 10:14:00,319 http-bio-8080-exec-25 ERROR xxx 614x203x2 p1s16e xxx.xxx.xxx.xxx /rest/activityplugin/1.0/usersettings [common.error.jersey.ThrowableExceptionMapper] Uncaught exception thrown by REST service
com.atlassian.activeobjects.internal.ActiveObjectsSqlException: There was a SQL exception thrown by the Active Objects library:
Database:
	- name:MySQL
	- version:5.1.54-rel12.5-log
	- minor version:1
	- major version:5
Driver:
	- name:MySQL-AB JDBC Driver
	- version:mysql-connector-java-5.1.10 ( Revision: ${svn.Revision} )
com.mysql.jdbc.exceptions.jdbc4.MySQLIntegrityConstraintViolationException: Duplicate entry '0' for key 'PRIMARY'
	at com.atlassian.activeobjects.internal.EntityManagedActiveObjects.create(EntityManagedActiveObjects.java:107)
	at com.atlassian.activeobjects.osgi.DelegatingActiveObjects.create(DelegatingActiveObjects.java:63)  <+3>
	at java.lang.reflect.Method.invoke(Unknown Source)
	(...)
	at java.lang.Thread.run(Unknown Source)
Caused by: com.mysql.jdbc.exceptions.jdbc4.MySQLIntegrityConstraintViolationException: Duplicate entry '0' for key 'PRIMARY'
	at sun.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
	(...)
	at com.atlassian.activeobjects.internal.EntityManagedActiveObjects.create(EntityManagedActiveObjects.java:103)
	... 194 more
```

### Cause

In MySQL configuration (my.ini (Windows) or my.cnf (Unix)), parameter of sql_mode is set to  NO_AUTO_VALUE_ON_ZERO.

### Solution

1.  Uninstall the Git Integration for Jira app.
2.  Remove all Git Integration for Jira app tables.
3.  Stop Jira.
4.  Stop MySQL.
5.  Edit the **my.cnf** file (often named **my.ini** on Windows operating systems or **my.cnf** on UNIX operating systems) in your MySQL server.
6.  Remove `NO_AUTO_VALUE_ON_ZERO` from sql_mode.
7.  Start MySQL.
8.  Start Jira.
9.  Install the Git Integration for Jira app.

For more information - see Atlassian help article about [Duplicate entry 0 for key PRIMARY exceptions in log](https://confluence.atlassian.com/jirakb/duplicate-entry-0-for-key-primary-exceptions-in-log-646251198.html).

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

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

**Duplicate entry 0 for key PRIMARY exceptions in log** (this page)

[Error while reindexing – Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Error creating git branches and also using NFS](/git-integration-for-jira-data-center/error-creating-git-branches-gitlabpropertiesnotinitializedexception-and-using-nfs-gij-self-managed)

[Fix performance issues for nested cloned repositories with enabled Git Service Permissions mode](/git-integration-for-jira-data-center/Fix-performance-issues-for-nested-cloned-repositories-with-enabled-secure-mode-gij-self-managed)

[Fixing reindex issues using Indexing Queue Viewer](/git-integration-for-jira-data-center/fixing-reindex-issues-using-indexing-queue-viewer)

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

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

