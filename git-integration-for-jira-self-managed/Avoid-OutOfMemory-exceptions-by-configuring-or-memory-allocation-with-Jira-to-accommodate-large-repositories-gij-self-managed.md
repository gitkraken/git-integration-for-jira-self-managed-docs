---

title: Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

## Story

The JGit library loads all index files into the memory and consumes about twice more memory than the size (in bytes) of these files.

## Problem(s)

The one or several of the following issues are encountered:

*   The JIRA application crashes
    
*   Unable to clone/reindex a repository
    
*   Unable to perform the Git GC procedure
    

## Diagnosis

The one or several of the following errors appear in the atlassian-jira.log:

```java
2020-10-20 02:04:37,120-0400 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 0 ERROR      [c.b.j.g.services.gitmanager.SingleGitManagerImpl] Can't perform GC operation: GC overhead limit exceeded
java.lang.OutOfMemoryError: GC overhead limit exceeded
```

```java
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

Additionally, go to **System** ➜ **System info** ➜ **JAVA VM memory statistics** to see if the allocated memory is running out:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/824803329/java-vm-memory-statistics(c).png?version=1&modificationDate=1604907189839&cacheVersion=1&api=v2)

## Cause

The JVM running JIRA applications has hit an OutOfMemory Error (OOME). This is thrown when the Java Virtual Machine cannot allocate an object because it is out of memory, and no more memory can be made available by the garbage collector.

## Solution

[**Follow these instructions**](https://confluence.atlassian.com/adminjiraserver/increasing-jira-application-memory-938847654.html) to increase the memory available to the JIRA application.

Verify if the memory for Jira has changed by going to **System ➜ System info ➜ JAVA VM memory statistics**:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/824803329/verify-memory-alloc-jira-java-vm.png?version=1&modificationDate=1604907612234&cacheVersion=1&api=v2)

