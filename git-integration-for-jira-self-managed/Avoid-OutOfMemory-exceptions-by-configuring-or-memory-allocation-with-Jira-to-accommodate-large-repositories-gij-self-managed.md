---

title: Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Story

The JGit library loads all index files into the memory and consumes about twice more memory than the size (in bytes) of these files.

### Problem(s)

The one or several of the following issues are encountered:

*   The JIRA application crashes

*   Unable to clone/reindex a repository

*   Unable to perform the Git GC procedure


### Diagnosis

The one or several of the following errors appear in the atlassian-jira.log:

```java
2020-10-20 02:04:37,120-0400 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 0 ERROR      [c.b.j.g.services.gitmanager.SingleGitManagerImpl] Can't perform GC operation: GC overhead limit exceeded
java.lang.OutOfMemoryError: GC overhead limit exceeded
```

```
Can't auto-deploy a new repository <your repository origin> java.lang.OutOfMemoryError: Java heap space
```

```java
2020-04-03 13:20:58,710+0100 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 0 ERROR      [c.b.j.g.s.indexer.revisions.RevisionIndexerImpl] Unable to index repository '<your repository display name>' (repoId: <your repository id>)
org.eclipse.jgit.errors.TransportException: Out of memory loading unknown object
    at org.eclipse.jgit.transport.BasePackFetchConnection.doFetch(BasePackFetchConnection.java:405)
    at org.eclipse.jgit.transport.BasePackFetchConnection.fetch(BasePackFetchConnection.java:328)
    at org.eclipse.jgit.transport.BasePackFetchConnection.fetch(BasePackFetchConnection.java:319)
    at org.eclipse.jgit.transport.FetchProcess.fetchObjects(FetchProcess.java:266)
    at org.eclipse.jgit.transport.FetchProcess.executeImp(FetchProcess.java:163)
    at org.eclipse.jgit.transport.FetchProcess.execute(FetchProcess.java:124)
    at org.eclipse.jgit.transport.Transport.fetch(Transport.java:1292)
    at com.bigbrassband.jira.git.services.gitmanager.SingleGitManagerImpl.fetch(SingleGitManagerImpl.java:1285)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.fetchImpl(GitPluginIndexManagerImpl.java:527)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.callFetch(GitPluginIndexManagerImpl.java:514)
    at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.updateIndex(GitPluginIndexManagerImpl.java:341)
    at com.bigbrassband.jira.git.services.indexer.revisions.RevisionIndexerImpl$1.doRun(RevisionIndexerImpl.java:151)
    at com.bigbrassband.jira.git.services.indexer.revisions.QueueEntry.run(QueueEntry.java:82)
    at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
    at java.util.concurrent.FutureTask.run(FutureTask.java:266)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
    at java.lang.Thread.run(Thread.java:748)
Caused by: org.eclipse.jgit.errors.LargeObjectException$OutOfMemory: Out of memory loading unknown object
    at org.eclipse.jgit.internal.storage.file.PackFile.load(PackFile.java:944)
    at org.eclipse.jgit.internal.storage.file.PackFile.get(PackFile.java:318)
    at org.eclipse.jgit.internal.storage.file.ObjectDirectory.openPackedObject(ObjectDirectory.java:488)
    at org.eclipse.jgit.internal.storage.file.CachedObjectDirectory.openObject(CachedObjectDirectory.java:220)
    at org.eclipse.jgit.internal.storage.file.CachedObjectDirectory.openObject(CachedObjectDirectory.java:210)
    at org.eclipse.jgit.internal.storage.file.WindowCursor$AjcClosure1.run(WindowCursor.java:1)
    at org.aspectj.runtime.reflect.JoinPointImpl.proceed(JoinPointImpl.java:149)
    at com.bigbrassband.common.git.blobmanagement.JGitAspects.interceptFor(JGitAspects.java:109)
    at com.bigbrassband.common.git.blobmanagement.JGitAspects.ajc$inlineAccessMethod$com_bigbrassband_common_git_blobmanagement_JGitAspects$com_bigbrassband_common_git_blobmanagement_JGitAspects$interceptFor(JGitAspects.java:1)
    at com.bigbrassband.common.git.blobmanagement.JGitAspects.intercept4(JGitAspects.java:97)
    at org.eclipse.jgit.internal.storage.file.WindowCursor.open(WindowCursor.java:165)
    at org.eclipse.jgit.lib.ObjectReader.open(ObjectReader.java:236)
    at org.eclipse.jgit.transport.PackParser.resolveDeltasWithExternalBases(PackParser.java:885)
    at org.eclipse.jgit.transport.PackParser.processDeltas(PackParser.java:621)
    at org.eclipse.jgit.transport.PackParser.parse(PackParser.java:584)
    at org.eclipse.jgit.internal.storage.file.ObjectDirectoryPackParser.parse(ObjectDirectoryPackParser.java:201)
    at org.eclipse.jgit.transport.PackParser.parse(PackParser.java:529)
    at org.eclipse.jgit.transport.BasePackFetchConnection.receivePack(BasePackFetchConnection.java:823)
    at org.eclipse.jgit.transport.BasePackFetchConnection.doFetch(BasePackFetchConnection.java:398)
    ... 17 more
Caused by: java.lang.OutOfMemoryError: Java heap space
```

Additionally, go to System ➜ System info ➜ **JAVA VM memory statistics** to see if the allocated memory is running out:

![](/wp-content/uploads/gij-java-vm-memory-statistics-c.png)

&nbsp;

### Cause

The JVM running JIRA applications has hit an OutOfMemory Error (OOME). This is thrown when the Java Virtual Machine cannot allocate an object because it is out of memory, and no more memory can be made available by the garbage collector.

### Solution

[**Follow these instructions**](https://confluence.atlassian.com/adminjiraserver/increasing-jira-application-memory-938847654.html) to increase the memory available to the JIRA application.

Verify if the memory for Jira has changed by going to System ➜ System info ➜ **JAVA VM memory statistics**:

![](/wp-content/uploads/gij-verify-memory-alloc-jira-java-vm.png)

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

**Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories** (this page)

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

[SQLException 'Incorrect string value' in merge requests](/git-integration-for-jira-data-center/sqlexception-incorrect-string-value-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

