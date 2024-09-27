---

title: Jira index error IndexNotFoundException - no segments\* file found
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- TROUBLESHOOTING -->

### Problem

Some or all repositories are not indexing which may be caused by a system or disk failure.

### Diagnosis

Jira admins will see a message similar to the one below in the Jira `/application-logs/atlassian-jira.log`:

**Error:**

```java
2019/05/08 18:29:06 org.apache.lucene.index.IndexNotFoundException: no segments* file found in MMapDirectory@E:\\Program Files\\Atlassian\\Application Data\\JIRA\\caches\\indexes\\plugins\\jira-git-revisions lockFactory=org.apache.lucene.store.NativeFSLockFactory@4fd7bb9a: files: []
java.lang.RuntimeException: org.apache.lucene.index.IndexNotFoundException: no segments* file found in MMapDirectory@E:\\Program Files\\Atlassian\\Application Data\\JIRA\\caches\\indexes\\plugins\\jira-git-revisions lockFactory=org.apache.lucene.store.NativeFSLockFactory@4fd7bb9a: files: []
at com.bigbrassband.jira.git.jiraservices.compatibility.CompatibilityLuceneService.openIndexReader(CompatibilityLuceneService.java:299)
at com.bigbrassband.jira.git.services.indexer.revisions.DefaultLuceneIndexAccessor.getIndexReader(DefaultLuceneIndexAccessor.java:75)
at com.bigbrassband.jira.git.services.indexer.revisions.IndexManagerImpl.getIndexReader(IndexManagerImpl.java:132)
at com.bigbrassband.jira.git.services.indexer.revisions.RevisionsIndexManagerImpl.updateBranchIndex(RevisionsIndexManagerImpl.java:933)
at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.updateIndex(GitPluginIndexManagerImpl.java:429)
at com.bigbrassband.jira.git.services.indexer.revisions.RevisionIndexerImpl$1.doRun(RevisionIndexerImpl.java:151)
at com.bigbrassband.jira.git.services.indexer.revisions.QueueEntry.run(QueueEntry.java:82)
at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
at java.util.concurrent.FutureTask.run(FutureTask.java:266)
at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
at java.lang.Thread.run(Thread.java:748)
Caused by: org.apache.lucene.index.IndexNotFoundException: no segments* file found in MMapDirectory@E:\\Program Files\\Atlassian\\Application Data\\JIRA\caches\\indexes\\plugins\\jira-git-revisions lockFactory=org.apache.lucene.store.NativeFSLockFactory@4fd7bb9a: files: []
at org.apache.lucene.index.SegmentInfos$FindSegmentsFile.run(SegmentInfos.java:670)
at org.apache.lucene.index.StandardDirectoryReader.open(StandardDirectoryReader.java:79)
at org.apache.lucene.index.DirectoryReader.open(DirectoryReader.java:63)
at sun.reflect.GeneratedMethodAccessor1234.invoke(Unknown Source)
at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
at java.lang.reflect.Method.invoke(Method.java:498)
at com.bigbrassband.jira.git.jiraservices.compatibility.CompatibilityLuceneService.openIndexReader(CompatibilityLuceneService.java:287)
... 11 more
```

### Solution

Perform a Jira System Full re-index option via Administration ➜ System ➜ Advanced ➜ **Indexing**.

For more information - see Atlassian help article about [Search indexing](https://confluence.atlassian.com/adminjiraserver/search-indexing-938847710.html).

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

**Jira index error: IndexNotFoundException: no segments* file found** (this page)

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

