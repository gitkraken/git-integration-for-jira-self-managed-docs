---

title: Error creating git branches and also using NFS
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- I'm removing the long word from the title because it just clips through the right pane of the HC page -->

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>JIRA SELF-MANAGED</b>

Also relates to the following exception errors:

*   `GitLabPropertiesNotInitializedException`
*   `GitHubPropertiesNotInitializedException`
*   `GerritPropertiesNotInitializedException`

&nbsp;

### Problem

An error is encountered with the next exception ( `GitLabPropertiesNotInitializedException` ) and you are using NFS.

**Example Error log**

```java
/rest/gitplugin/1.0/repository/12300/pullRequest [c.b.j.g.rest.exceptionmappers.LoggerHolder] REST API has thrown exception.
com.bigbrassband.jira.git.exceptions.operations.GitLabPropertiesNotInitializedException: Initialization
at com.bigbrassband.jira.git.services.integration.gitlab.GitLabApiService$GitLabRepoApi.getExternalRepoProps(GitLabApiService.java:107)
at com.bigbrassband.jira.git.services.integration.gitlab.GitLabApiService$GitLabRepoApi.getRepoExternalIdForMergeRequests(GitLabApiService.java:113)
at com.bigbrassband.jira.git.services.integration.gitlab.GitLabApiService$GitLabRepoApi.createMergeRequest(GitLabApiService.java:68)
at com.bigbrassband.jira.git.rest.repository.RepositoryResource.createPullRequest(RepositoryResource.java:832)
at com.bigbrassband.jira.git.rest.repository.RepositoryResource.restCreatePullRequest(RepositoryResource.java:796)
at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
at java.base/java.lang.reflect.Method.invoke(Method.java:566)
```

&nbsp;

### Diagnosis

Check the root of the reason by [turning on DEBUG logging](https://help.gitkraken.com/git-integration-for-jira-data-center/faq-logging-gij-self-managed/#how-do-i-enable-debug-logging-level-for-git-integration-for-jira-app) for the package – **com.bigbrassband.jira.git.services.integration**.

The root reason of the exception error can be one of the following:

1.  not a valid json entry in `repo.auto.json`

2.  incapability to lock file (`java.io.IOException: No locks available`)

&nbsp;

### Solution 1

Make sure that `repo.auto.json` (`jira/data/git-plugin/###-somerepo/repo.auto.json`) contains a valid json.

&nbsp;

### Solution 2

The lock daemon (lockd) may not be running on the **NFS** server. Check whether your NFS server supports locking. Update the NFS version, if required.

NFSv4 supporting locking by default was [released in 2000](https://en.wikipedia.org/wiki/Network_File_System). So, it's a rare case to encounter an NFS server which is not able to lock the `/jira/data/git-plugin/###-somerepo/repo.auto.json` file these days.

