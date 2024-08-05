---

title: Personal access token failing Azure DevOps integration with Not Authorized error
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Problem

The Personal Access Token created in Azure DevOps is not valid for authentication.

### Diagnosis

Jira admins will see a Not authorized error (with the following full error) when connecting to Azure DevOps with a Personal Access Token if the token was created for a specific Azure DevOps organization:

![](/wp-content/uploads/gij-personal-access-token-failing-azure-devops.png)

&nbsp;

**Technical info: Error:**

```java
2019-07-08 12:21:09,997 http-nio-8080-exec-436 ERROR sfj 741x4276982x1 a7oa8 192.168.143.212 /rest/gitplugin/1.0/trackedfolders/scan/4994-Bpv7dj9zmeyFAAf6 [c.b.j.g.rest.exceptionmappers.WrappedIntegrationAPIExceptionMapper] Rest API has thrown exception.
com.bigbrassband.jira.git.exceptions.external.WrappedMicrosoftAPIException: External service error
at com.bigbrassband.jira.git.services.integration.microsoft.MicrosoftApi.getRepositoriesMS(MicrosoftApi.java:134)
at com.bigbrassband.jira.git.services.integration.microsoft.MicrosoftApi.getRepositories(MicrosoftApi.java:93)
at com.bigbrassband.jira.git.services.integration.microsoft.MicrosoftApiService.scan(MicrosoftApiService.java:132)
at com.bigbrassband.jira.git.services.integration.microsoft.MicrosoftApiService.fastScan(MicrosoftApiService.java:137)
at com.bigbrassband.jira.git.services.async.ScanTrackedRepoTask.run(ScanTrackedRepoTask.java:61)
at com.bigbrassband.jira.git.services.async.AsyncProcessorImpl$AsyncTaskWrapper.run(AsyncProcessorImpl.java:114)
at java.util.concurrent.Executors$RunnableAdapter.call(Unknown Source)
at java.util.concurrent.FutureTask.run(Unknown Source)
at java.util.concurrent.ThreadPoolExecutor.runWorker(Unknown Source)
at java.util.concurrent.ThreadPoolExecutor$Worker.run(Unknown Source)
at java.lang.Thread.run(Unknown Source)
Caused by: com.bigbrassband.common.indexer.sources.clients.RequestException: Microsoft https://app.vssps.visualstudio.com/_apis/profile/profiles/me?api-version=1.0 Unauthorized (401)
at com.bigbrassband.common.indexer.sources.clients.MicrosoftClient.runRequest(MicrosoftClient.java:288)
at com.bigbrassband.common.indexer.sources.clients.MicrosoftClient.callSingleApi(MicrosoftClient.java:239)
at com.bigbrassband.common.indexer.sources.clients.MicrosoftClient.getUserId(MicrosoftClient.java:173)
at com.bigbrassband.jira.git.services.integration.microsoft.MicrosoftApi.getRepositoriesMS(MicrosoftApi.java:125)
... 10 more
```

### Solution

Azure DevOps Personal Access Tokens must be created using the All accessible organizations in the **Organization** dropdown. Additionally - the token must either have _**Full access**_ scope or _**Code: Read & Write**_ (as shown below). Minimum requirement is _**Code: Read**_.

1.  Create new Personal Access Token:

    ![](/wp-content/uploads/gij-azure-devops-personal-access-token-all-accessible-organizations.png)

2.  Copy token:

    ![](/wp-content/uploads/gij-example-pat-azure-devops.png)

3.  Verify token uses All accessible organizations, has sufficient scopes, is not expired and is active:

    ![](/wp-content/uploads/gij-verify-scopes-orgs-azure-devops.png)

4.  Paste newly created token:

    ![](/wp-content/uploads/gij-manage-git-repos-azure-devops-tokens.png)

5.  Click **Connect**.

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

**Personal access token failing Azure DevOps integration with Not Authorized error** (this page)

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

