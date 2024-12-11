---

title: Error creating git branches and also using NFS
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- I'm removing the long word from the title because it just clips through the right pane of the HC page -->

<!-- TROUBLESHOOTING -->

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

**Error creating git branches and also using NFS** (this page)

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

[When a GIJ license expires, it shows up as a session error to the user](/git-integration-for-jira-data-center/when-a-license-expires-a-session-error-is-shown-to-the-user-gij-self-managed)

[edDSA provider not supported WARN in logs](/git-integration-for-jira-data-center/edDSA-provider-not-supported-WARN-in-logs-gij-self-managed)

