---

title: SQLException Incorrect string value in merge requests
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- TROUBLESHOOTING -->

### Problem

Pull/merge requests no longer show in the app after updating beyond Git Integration version **3.7.0+**.

The following errors are encountered:

```java
2020-09-28 15:12:01,087+0200 bigbrassband-gitplugin-AsyncProcessorImpl:thread - 0 ERROR      [c.b.j.g.services.async.BigReindexTask] Error retrieving merge/pull requests for repoId = 119
java.lang.reflect.UndeclaredThrowableException
	at com.sun.proxy.$Proxy5398.save(Unknown Source)
	at com.bigbrassband.jira.git.ao.dao.MergeRequestDao.update(MergeRequestDao.java:38)
	at com.bigbrassband.jira.git.services.indexer.pullrequests.MergeRequestRetrieverImpl.updateIfChanged(MergeRequestRetrieverImpl.java:185)
	at com.bigbrassband.jira.git.services.indexer.pullrequests.MergeRequestRetrieverImpl.lambda$updateMergeRequestsFull$2(MergeRequestRetrieverImpl.java:122)
	at com.bigbrassband.jira.git.ao.dao.MergeRequestDaoImpl.lambda$streamByQuery$1(MergeRequestDaoImpl.java:47)
	at net.java.ao.EntityManager.stream(EntityManager.java:825)
	at com.atlassian.activeobjects.internal.EntityManagedActiveObjects.stream(EntityManagedActiveObjects.java:164)
	at com.atlassian.activeobjects.osgi.TenantAwareActiveObjects.stream(TenantAwareActiveObjects.java:316)
	... 2 filtered
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.springframework.aop.support.AopUtils.invokeJoinpointUsingReflection(AopUtils.java:302)
	at org.eclipse.gemini.blueprint.service.importer.support.internal.aop.ServiceInvoker.doInvoke(ServiceInvoker.java:56)
	at org.eclipse.gemini.blueprint.service.importer.support.internal.aop.ServiceInvoker.invoke(ServiceInvoker.java:60)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:179)
	at org.springframework.aop.support.DelegatingIntroductionInterceptor.doProceed(DelegatingIntroductionInterceptor.java:133)
	at org.springframework.aop.support.DelegatingIntroductionInterceptor.invoke(DelegatingIntroductionInterceptor.java:121)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:179)
	at org.eclipse.gemini.blueprint.service.util.internal.aop.ServiceTCCLInterceptor.invokeUnprivileged(ServiceTCCLInterceptor.java:70)
	at org.eclipse.gemini.blueprint.service.util.internal.aop.ServiceTCCLInterceptor.invoke(ServiceTCCLInterceptor.java:53)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:179)
	at org.eclipse.gemini.blueprint.service.importer.support.LocalBundleContextAdvice.invoke(LocalBundleContextAdvice.java:57)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:179)
	at org.springframework.aop.support.DelegatingIntroductionInterceptor.doProceed(DelegatingIntroductionInterceptor.java:133)
	at org.springframework.aop.support.DelegatingIntroductionInterceptor.invoke(DelegatingIntroductionInterceptor.java:121)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:179)
	at org.springframework.aop.framework.JdkDynamicAopProxy.invoke(JdkDynamicAopProxy.java:208)
	at com.sun.proxy.$Proxy2382.stream(Unknown Source)
	at com.bigbrassband.jira.git.ao.dao.MergeRequestDaoImpl.streamByQuery(MergeRequestDaoImpl.java:46)
	at com.bigbrassband.jira.git.ao.dao.MergeRequestDaoImpl.streamByRepoId(MergeRequestDaoImpl.java:37)
	at com.bigbrassband.jira.git.services.indexer.pullrequests.MergeRequestRetrieverImpl.updateMergeRequestsFull(MergeRequestRetrieverImpl.java:118)
	at com.bigbrassband.jira.git.services.indexer.pullrequests.MergeRequestRetrieverImpl.updateMergeRequests(MergeRequestRetrieverImpl.java:90)
	at com.bigbrassband.jira.git.services.async.BigReindexTask.reindexMergeRequests(BigReindexTask.java:245)
	at com.bigbrassband.jira.git.services.async.BigReindexTask.run(BigReindexTask.java:133)
	at com.bigbrassband.jira.git.services.async.AsyncProcessorImpl$1.doRun(AsyncProcessorImpl.java:86)
	at com.bigbrassband.jira.git.services.indexer.revisions.QueueEntry.run(QueueEntry.java:90)
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)
Caused by: java.sql.SQLException: Incorrect string value: '\\xF0\\x9F\\x8E\\x84 C...' for column 'TITLE' at row 1
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:965)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.PreparedStatement.executeInternal(PreparedStatement.java:1858)
	at com.mysql.jdbc.PreparedStatement.executeUpdateInternal(PreparedStatement.java:2079)
	at com.mysql.jdbc.PreparedStatement.executeUpdateInternal(PreparedStatement.java:2013)
	at com.mysql.jdbc.PreparedStatement.executeLargeUpdate(PreparedStatement.java:5104)
	at com.mysql.jdbc.PreparedStatement.executeUpdate(PreparedStatement.java:1998)
	at org.apache.commons.dbcp2.DelegatingPreparedStatement.executeUpdate(DelegatingPreparedStatement.java:98)
	at org.apache.commons.dbcp2.DelegatingPreparedStatement.executeUpdate(DelegatingPreparedStatement.java:98)
	at net.java.ao.EntityProxy.save(EntityProxy.java:579)
	at net.java.ao.EntityProxy.invoke(EntityProxy.java:115)
	... 41 more
```

&nbsp;

### Diagnosis

The reason for these errors – some pull/merge requests may use 4-byte UTF-8 characters (like emojis) which not supported in MySQL database collation 'utf8\_bin'.

Some useful references for this issue:

*   [https://confluence.atlassian.com/kb/how-to-fix-the-collation-and-character-set-of-a-mysql-database-744326173.html](https://confluence.atlassian.com/kb/how-to-fix-the-collation-and-character-set-of-a-mysql-database-744326173.html)

*   [https://community.atlassian.com/t5/Jira-Software-questions/The-database-setup-is-not-supporting-utf8mb4/qaq-p/1012877](https://community.atlassian.com/t5/Jira-Software-questions/The-database-setup-is-not-supporting-utf8mb4/qaq-p/1012877)

*   [https://community.atlassian.com/t5/Jira-Software-questions/The-database-setup-is-not-supporting-utf8mb4-but-it-is/qaq-p/1037415](https://community.atlassian.com/t5/Jira-Software-questions/The-database-setup-is-not-supporting-utf8mb4-but-it-is/qaq-p/1037415)

*   [https://confluence.atlassian.com/fishkb/migrate-mysql-database-to-utf8mb4-character-encoding-962356253.html](https://confluence.atlassian.com/fishkb/migrate-mysql-database-to-utf8mb4-character-encoding-962356253.html)

&nbsp;

### Solution

Switch the character encoding in the MySQL Jira database to `utf8mb4` and collation to `utf8mb4_bin` as described in the first article listed above.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
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

**SQLException 'Incorrect string value' in merge requests** (this page)

[SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

[When a GIJ license expires, it shows up as a session error to the user](/git-integration-for-jira-data-center/when-a-license-expires-a-session-error-is-shown-to-the-user-gij-self-managed)

[edDSA provider not supported WARN in logs](/git-integration-for-jira-data-center/edDSA-provider-not-supported-WARN-in-logs-gij-self-managed)

