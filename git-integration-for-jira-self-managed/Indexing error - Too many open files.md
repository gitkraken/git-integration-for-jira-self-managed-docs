---

title: Indexing error - Too many open files
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Indexing error - Too many open files

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/318013497/Indexing+error+-+Too+many+open+files>

* * *

## Problem

Repository is not indexing and errors in Jira logs point to "Too many open files".

## Diagnosis

Jira admins will see a message similar to the one below in the Jira `/application-logs/atlassian-jira.log`:  
  

**Error**

```java
2019-05-07 15:41:13,171 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 0 ERROR      [c.b.j.g.s.indexer.revisions.RevisionIndexerImpl] Unable to index repository 'name' (repoId: 111)
org.eclipse.jgit.errors.TransportException: Failure updating tracking ref refs/...: Too many open files
	at org.eclipse.jgit.transport.FetchProcess.executeImp(FetchProcess.java:229)
	at org.eclipse.jgit.transport.FetchProcess.execute(FetchProcess.java:124)
	at org.eclipse.jgit.transport.Transport.fetch(Transport.java:1271)
	at com.bigbrassband.jira.git.services.gitmanager.SingleGitManagerImpl.fetch(SingleGitManagerImpl.java:1249)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.fetchImpl(GitPluginIndexManagerImpl.java:510)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.callFetch(GitPluginIndexManagerImpl.java:497)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.updateIndex(GitPluginIndexManagerImpl.java:335)
	at com.bigbrassband.jira.git.services.indexer.revisions.RevisionIndexerImpl$1.doRun(RevisionIndexerImpl.java:151)
	at com.bigbrassband.jira.git.services.indexer.revisions.QueueEntry.run(QueueEntry.java:82)
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)
Caused by: java.io.IOException: Too many open files
	at java.io.UnixFileSystem.createFileExclusively(Native Method)
	at java.io.File.createNewFile(File.java:1012)
	at org.eclipse.jgit.util.FS_POSIX.createNewFileAtomic(FS_POSIX.java:446)
	at org.eclipse.jgit.internal.storage.file.LockFile.lock(LockFile.java:164)
	at org.eclipse.jgit.internal.storage.file.PackedBatchRefUpdate.lockLooseRefs(PackedBatchRefUpdate.java:349)
	at org.eclipse.jgit.lib.BatchRefUpdate.execute(BatchRefUpdate.java:635)
	at org.eclipse.jgit.transport.FetchProcess.executeImp(FetchProcess.java:224)
	... 13 more
```

## Solution

See Atlassian help article about [increasing the number of file handles available to Jira](https://confluence.atlassian.com/jirakb/loss-of-functionality-due-to-too-many-open-files-errors-156862102.html)

  

Contact Us

If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com)

## Related articles

*   Page:
    
    [Whitelist BigBrassBand Cloud](/wiki/spaces/BBBSUPPORT/pages/125141005/Whitelist+BigBrassBand+Cloud)
    
*   Page:
    
    [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/wiki/spaces/BBBSUPPORT/pages/878968833/Avoid+OutOfMemory+exceptions+by+configuring+or+memory+allocation+with+Jira+to+accommodate+large+repositories)
    
*   Page:
    
    [(Git Integration: Jira Server/Data Center) "Dangerous use of multiple connections" error on local database](/wiki/spaces/BBBSUPPORT/pages/822050817)
    
*   Page:
    
    ["Service proxy has been destroyed" exceptions in log (Git Integration: Server/Data Center)](/wiki/spaces/BBBSUPPORT/pages/458817592)
    
*   Page:
    
    [Git Integration (Server): Jira index error: IndexNotFoundException: no segments\* file found](/wiki/spaces/BBBSUPPORT/pages/132022367/Git+Integration+%28Server%29%3A+Jira+index+error%3A+IndexNotFoundException%3A+no+segments*+file+found)