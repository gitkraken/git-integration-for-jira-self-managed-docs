---

title: Malformed input or input contains unmappable characters
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
## Problem

Errors/failures in the Git Integration for Jira application indexing.

## Diagnosis

Jira admins will see a message similar to the one below in the Jira log: `/application-logs/atlassian-jira.log`:

**Error**

```java
2019/10/01 12:34:56 Malformed input or input contains unmappable characters: /var/jira/data/git-plugin/150_repository_name/refs/heads/hølaf
java.nio.file.InvalidPathException: Malformed input or input contains unmappable characters: /var/jira/data/git-plugin/150_repository_name/refs/heads/hølaf
	at sun.nio.fs.UnixPath.encode(UnixPath.java:147)
	at sun.nio.fs.UnixPath.<init>(UnixPath.java:71)
	at sun.nio.fs.UnixFileSystem.getPath(UnixFileSystem.java:281)
	at java.io.File.toPath(File.java:2234)
	at org.eclipse.jgit.util.FileUtils.fileAttributes(FileUtils.java:672)
	at org.eclipse.jgit.util.FS.fileAttributes(FS.java:457)
	at org.eclipse.jgit.internal.storage.file.FileSnapshot.save(FileSnapshot.java:118)
	at org.eclipse.jgit.internal.storage.file.RefDirectory.scanRef(RefDirectory.java:1153)
	at org.eclipse.jgit.internal.storage.file.RefDirectory.readRef(RefDirectory.java:1125)
	at org.eclipse.jgit.internal.storage.file.RefDirectory.pack(RefDirectory.java:764)
	at org.eclipse.jgit.internal.storage.file.RefDirectory.pack(RefDirectory.java:736)
	at org.eclipse.jgit.internal.storage.file.PackedBatchRefUpdate.execute(PackedBatchRefUpdate.java:180)
	at org.eclipse.jgit.lib.BatchRefUpdate.execute(BatchRefUpdate.java:635)
	at org.eclipse.jgit.transport.FetchProcess.executeImp(FetchProcess.java:224)
	at org.eclipse.jgit.transport.FetchProcess.execute(FetchProcess.java:124)
	at org.eclipse.jgit.transport.Transport.fetch(Transport.java:1271)
	at com.bigbrassband.jira.git.services.gitmanager.SingleGitManagerImpl.fetch(SingleGitManagerImpl.java:1260)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.fetchImpl(GitPluginIndexManagerImpl.java:515)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.callFetch(GitPluginIndexManagerImpl.java:502)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.updateIndex(GitPluginIndexManagerImpl.java:339)
	at com.bigbrassband.jira.git.services.indexer.revisions.RevisionIndexerImpl$1.doRun(RevisionIndexerImpl.java:151)
	at com.bigbrassband.jira.git.services.indexer.revisions.QueueEntry.run(QueueEntry.java:82)
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)
```

## Cause

Atlassian recommends UTF-8 or Unicode encoding, and case-insensitive collation. In most cases, problems are due to a misconfiguration in one of the components.

## Solutions

See Atlassian help article: [Troubleshoot character display issues in Jira server](https://confluence.atlassian.com/jirakb/troubleshoot-character-display-issues-in-jira-server-203394762.html).

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

<br>

## More articles about troubleshooting, workarounds and solutions

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/Avoid-OutOfMemory-exceptions-by-configuring-or-memory-allocation-with-Jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

["Dangerous use of multiple connections" error on local database](/git-integration-for-jira-data-center/Dangerous-use-of-multiple-connections-error-on-local-database-gij-self-managed)

[Duplicate entry 0 for key PRIMARY exceptions in log](/git-integration-for-jira-data-center/Duplicate-entry-0-for-key-PRIMARY-exceptions-in-log-gij-self-managed)

[Error while reindexing - Java heap space / Object too large, rejecting the pack](/git-integration-for-jira-data-center/Error-while-reindexing-Java-heap-space-Object-too-large,-rejecting-the-pack-gij-self-managed)

[Gitolite integration: Why the Git integration app not see the master branch?](/git-integration-for-jira-data-center/Gitolite-integration--why-the-Git-integration-app-not-see-the-master-branch-gij-self-managed)

[Health Check\: Database Collation](/git-integration-for-jira-data-center/Health-check--database-collation-gij-self-managed)

[Indexing error - Too many open files](/git-integration-for-jira-data-center/Indexing-error-Too-many-open-files-gij-self-managed)

[Installation fails when installing manually](/git-integration-for-jira-data-center/Installation-fails-when-installing-manually-gij-self-managed)

[Jira index error: IndexNotFoundException: no segments\* file found](/git-integration-for-jira-data-center/Jira-index-error--IndexNotFoundException--no-segments-file-found)

**Malformed input or input contains unmappable characters** (this page)

[Personal access token failing Azure DevOps integration with Not Authorized error](/git-integration-for-jira-data-center/Personal-access-token-failing-azure-devops-integration-with-Not-Authorized-error-gij-self-managed)

[Problems with shared home on Azure Storage](/git-integration-for-jira-data-center/Problems-with-shared-home-on-azure-storage-gij-self-managed)

[Pull request index error: org.json.JSONException](/git-integration-for-jira-data-center/Pull-request-index-error--JSONException-gij-self-managed)

[Repositories missing from Azure DevOps integration](/git-integration-for-jira-data-center/Repositories-missing-from-azure-devops-integration-gij-self-managed)

[Service proxy has been destroyed  exceptions in log](/git-integration-for-jira-data-center/Service-proxy-has-been-destroyed-exceptions-in-log-gij-self-managed)

[SQLException Incorrect string value in merge requests](/git-integration-for-jira-data-center/SQLException-'Incorrect-string-value'-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/SSH-key-file-format-is-invalid-gij-self-managed)

[TFS - Not Authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/TFS-Not-authorized-exception-when-Jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

