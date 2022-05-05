---

title: Error while reindexing - Java heap space / Object too large, rejecting the pack
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Error while reindexing - Java heap space / Object too large, rejecting the pack

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/137035882>

* * *

## Problem

The Git Integration for Jira application uses the [JGit](https://www.eclipse.org/jgit/) library which does not support objects over 2GB in size stored in git repositories.

## Diagnosis

Jira admins will see an error in the Git Integration for Jira app interface - for example:  
  

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/137035882/wizard-java-heap-space.png?version=1&modificationDate=1559306844537&cacheVersion=1&api=v2&width=335&height=249)

  

or Jira admins will see a message similar to the one below in the Jira `/application-logs/atlassian-jira.log:`

**Error**

```java
Сan't auto-deploy a new repository https://server/project/repository.git
com.bigbrassband.jira.git.exceptions.InvalidRemoteOperationException: Specified origin https://server/project/repository.git is incorrect or not supported
        at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.setupRepository(MultipleGitRepositoryManagerImpl.java:800)
        at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.deployRepository(MultipleGitRepositoryManagerImpl.java:868)
        at com.bigbrassband.jira.git.services.async.DoSynchronizationOfAggregatedRepoTask.createNewRepository(DoSynchronizationOfAggregatedRepoTask.java:156)
        at com.bigbrassband.jira.git.services.async.DoSynchronizationOfAggregatedRepoTask.run(DoSynchronizationOfAggregatedRepoTask.java:117)
        at com.bigbrassband.jira.git.services.async.BigReindexTask.synchronize(BigReindexTask.java:185)
        at com.bigbrassband.jira.git.services.async.BigReindexTask.run(BigReindexTask.java:95)
        at com.bigbrassband.jira.git.services.async.AsyncProcessorImpl$AsyncTaskWrapper.run(AsyncProcessorImpl.java:110)
        at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
        at java.util.concurrent.FutureTask.run(FutureTask.java:266)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
        at java.lang.Thread.run(Thread.java:748)
Caused by: org.eclipse.jgit.api.errors.TransportException: Object too large (2,271,263,009 bytes), rejecting the pack. Max object size limit is 2,147,483,639 bytes.
        at org.eclipse.jgit.api.FetchCommand.call(FetchCommand.java:254)
        at org.eclipse.jgit.api.CloneCommand.fetch(CloneCommand.java:306)
        at org.eclipse.jgit.api.CloneCommand.call(CloneCommand.java:200)
        at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.runCloneCommand(MultipleGitRepositoryManagerImpl.java:693)
        at com.bigbrassband.jira.git.services.gitmanager.MultipleGitRepositoryManagerImpl.setupRepository(MultipleGitRepositoryManagerImpl.java:789)
        ... 11 more
```

## Solutions

  

Making any change to a git repository's history can result in loss of data. Proceed with care.

*   Remove objects larger than 2GB from the git repository history. See following articles for suggestions:
    *   [Removing large files from Git without losing history](https://support.acquia.com/hc/en-us/articles/360004334093-Removing-large-files-from-Git-without-losing-history)
    *   [GitHub: Removing files from a repository's history](https://help.github.com/en/articles/removing-files-from-a-repositorys-history)
    *   [GitLab: Reducing the repository size using Git](https://docs.gitlab.com/ee/user/project/repository/reducing_the_repo_size_using_git.html)
    *   [BFG Repo-Cleaner](https://rtyley.github.io/bfg-repo-cleaner/)
*   Move large files to [GitLFS](https://git-lfs.github.com) which is supported by the Git Integration for Jira app.
*   Filter out the repository from the special integrations (GitHub, GitLab, AWS CodeCommit, Microsoft TFS/Azure DevOps/VSTS, etc) using [Custom API Path](/wiki/spaces/BBBSUPPORT/pages/133267463) or [JMESPath Filters](/wiki/spaces/BBBSUPPORT/pages/133234739/Working+with+JMESPath+Filters).

  

  

Contact Us

If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com)

## Related articles

*   Page:
    
    [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/wiki/spaces/GIJDC/pages/873332786/Avoid+OutOfMemory+exceptions+by+configuring+or+memory+allocation+with+Jira+to+accommodate+large+repositories)
    
*   Page:
    
    [SQLException 'Incorrect string value' in merge requests](/wiki/spaces/GIJDC/pages/843448333/SQLException+%27Incorrect+string+value%27+in+merge+requests)
    
*   Page:
    
    ["Dangerous use of multiple connections" error on local database](/wiki/spaces/GIJDC/pages/821919745)
    
*   Page:
    
    ["Service proxy has been destroyed" exceptions in log](/wiki/spaces/GIJDC/pages/458883074)
    
*   Page:
    
    [Indexing error - Too many open files](/wiki/spaces/GIJDC/pages/318013497/Indexing+error+-+Too+many+open+files)
    
*   Page:
    
    [SSH key file format is invalid](/wiki/spaces/GIJDC/pages/187957296/SSH+key+file+format+is+invalid)
    
*   Page:
    
    [Why don't I see the Create Branch or Pull Request features?](/wiki/spaces/GIJDC/pages/123633735)
    
*   Page:
    
    [Error while reindexing - Java heap space / Object too large, rejecting the pack](/wiki/spaces/GIJDC/pages/137035882)
    
*   Page:
    
    [Installation fails when installing manually](/wiki/spaces/GIJDC/pages/167247873/Installation+fails+when+installing+manually)
    
*   Page:
    
    [TFS - Not authorized exception when Jira works thru proxy](/wiki/spaces/GIJDC/pages/128188471/TFS+-+Not+authorized+exception+when+Jira+works+thru+proxy)