---

title: Problems with shared home on Azure Storage
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- TROUBLESHOOTING -->

## Problem

Сan't auto-deploy a new repository. UnknownErrorException: Internal plugin error.

```java
Сan't auto-deploy a new repository https://example.org/example-path/example-git-repository.git
com.bigbrassband.jira.git.exceptions.UnknownErrorException: Internal plugin error.
      at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.setupRepository(MultipleGitRepositoryManagerImpl.java:817)
      at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.deployRepository(MultipleGitRepositoryManagerImpl.java:880)
      at com.bigbrassband.jira.git.services.async.DoSynchronizationOfAggregatedRepoTask.createNewRepository(DoSynchronizationOfAggregatedRepoTask.java:156)
      at com.bigbrassband.jira.git.services.async.DoSynchronizationOfAggregatedRepoTask.run(DoSynchronizationOfAggregatedRepoTask.java:117)
      at com.bigbrassband.jira.git.services.async.BigReindexTask.synchronize(BigReindexTask.java:195)
      at com.bigbrassband.jira.git.services.async.BigReindexTask.run(BigReindexTask.java:103)
      at com.bigbrassband.jira.git.services.async.AsyncProcessorImpl$AsyncTaskWrapper.run(AsyncProcessorImpl.java:114)
      at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
      at java.util.concurrent.FutureTask.run(FutureTask.java:266)
      at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
      at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
      at java.lang.Thread.run(Thread.java:748)
Caused by: org.eclipse.jgit.api.errors.JGitInternalException: /var/atlassian/application-data/jira/data/git-plugin/example/HEAD.lock.ace055a41a2e4w392k2k9d -> /var/atlassian/application-data/jira/data/git-plugin/example/HEAD.lock: Operation not supported
      at org.eclipse.jgit.api.InitCommand.call(InitCommand.java:128)
      at org.eclipse.jgit.api.CloneCommand.init(CloneCommand.java:274)
      at org.eclipse.jgit.api.CloneCommand.call(CloneCommand.java:195)
      at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.runCloneCommand(MultipleGitRepositoryManagerImpl.java:700)
      at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.setupRepository(MultipleGitRepositoryManagerImpl.java:796)
      ... 11 more
Caused by: java.nio.file.FileSystemException: /var/atlassian/application-data/jira/data/git-plugin/example/HEAD.lock.ace055a41a2e442bba91d3 -> /var/atlassian/application-data/jira/data/git-plugin/example/HEAD.lock: Operation not supported
      at sun.nio.fs.UnixException.translateToIOException(UnixException.java:91)
      at sun.nio.fs.UnixException.rethrowAsIOException(UnixException.java:102)
      at sun.nio.fs.UnixFileSystemProvider.createLink(UnixFileSystemProvider.java:476)
      at java.nio.file.Files.createLink(Files.java:1086)
      at org.eclipse.jgit.util.FS_POSIX.createNewFileAtomic(FS_POSIX.java:455)
      at org.eclipse.jgit.internal.storage.file.LockFile.lock(LockFile.java:164)
      at org.eclipse.jgit.internal.storage.file.RefDirectoryUpdate.tryLock(RefDirectoryUpdate.java:89)
      at org.eclipse.jgit.lib.RefUpdate.link(RefUpdate.java:708)
      at org.eclipse.jgit.internal.storage.file.FileRepository.create(FileRepository.java:309)
      at org.eclipse.jgit.api.InitCommand.call(InitCommand.java:125)
      ... 15 more
```

## Diagnosis

The root problem is that the modern **jgit** (the Java git library) does not recognize **cifs** mounts on Linux. It thinks they are NFS and must support hard links. The same behavior is also present with the jgit command line on Ubuntu with a **cifs** mount in Azure.


## Solutions

It is possible to suppress that behavior by adding a setting to the Linux users **.gitconfig**. The Linux user will be the one that Jira runs under (normally jira). You can switch to the user with `sudo su jira`:

```powershell
jira@MLS:/mnt/cifs$ cat $HOME/.gitconfig
[core]
supportsatomicfilecreation = true
```

<br>

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
<br>

<p>&nbsp;</p>

## More articles about troubleshooting, workarounds and solutions

[Why I am getting the error, “git-upload-pack not permitted”?](/git-integration-for-jira-data-center/why-i-am-getting-the-error-git-upload-pack-not-permitted-gij-self-managed/)

[Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/avoid-outofmemory-exceptions-by-configuring-or-memory-allocation-with-jira-to-accommodate-large-repositories-gij-self-managed)

[Cannot auto-deploy some tracked repositories: Specified origin is incorrect or not supported](/git-integration-for-jira-data-center/Cannot-auto-deploy-some-tracked-repositories-gij-self-managed)

[Connection Reset when Accessing the Database](/git-integration-for-jira-data-center/Connection-reset-when-accessing-the-database-gij-self-managed)

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

**Problems with shared home on Azure Storage** (this page)

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

