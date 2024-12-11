---

title: Your token has not been granted the required scopes
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- TROUBLESHOOTING -->

### Problem

Encountered some new errors on the Github PAT integration having issues indexing pull requests. The errors were pinpointing to insufficient roles on the personal access token.

Error message:
```java
Error retrieving merge/pull requests events for the repository 'John-Smith/Staging' (repoId=3594): External service error
External service error
com.bigbrassband.jira.git.exceptions.external.WrappedGithubAPIException: External service error
	at com.bigbrassband.jira.git.services.integration.github.GitHubApi.getMergeRequestsTimeline(GitHubApi.java:301)
	at com.bigbrassband.jira.git.services.integration.github.GitHubApiService$GitHubRepoApi.getMergeRequestsTimeline(GitHubApiService.java:136)
	at com.bigbrassband.jira.git.services.indexer.pullrequests.MergeRequestEventRetrieverImpl$EventsLoaderAfterTimestamp.load(MergeRequestEventRetrieverImpl.java:285)
	at com.bigbrassband.jira.git.services.indexer.pullrequests.MergeRequestEventRetrieverImpl.updateMergeRequestsEvents(MergeRequestEventRetrieverImpl.java:107)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.innerUpdateIndexMainNode(GitPluginIndexManagerImpl.java:361)
	at com.bigbrassband.jira.git.services.indexer.revisions.GitPluginIndexManagerImpl.updateIndexMainNode(GitPluginIndexManagerImpl.java:309)
	at com.bigbrassband.jira.git.services.async.ReindexQueueReindexTask.doRepositoryUpdate(ReindexQueueReindexTask.java:380)
	at com.bigbrassband.jira.git.services.async.ReindexQueueReindexTask.visit(ReindexQueueReindexTask.java:149)
	at com.bigbrassband.jira.git.services.gitmanager.SubGitManager.accept(SubGitManager.java:124)
	at com.bigbrassband.jira.git.services.async.ReindexQueueReindexTask.doRun(ReindexQueueReindexTask.java:133)
	at com.bigbrassband.jira.git.services.async.ReindexQueueTask.run(ReindexQueueTask.java:37)
	at com.bigbrassband.jira.git.services.async.ReindexQueueManagerImpl$QueueTask.doRun(ReindexQueueManagerImpl.java:227)
	at com.bigbrassband.jira.git.utils.concurrent.cancel.CancellableTask.run1(CancellableTask.java:38)
	at com.bigbrassband.jira.git.utils.concurrent.cancel.CancellableTask.call(CancellableTask.java:25)
	at com.bigbrassband.jira.git.utils.concurrent.cancel.CancellableTask.call(CancellableTask.java:8)
	at java.base/java.util.concurrent.FutureTask.run(Unknown Source)
	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(Unknown Source)
	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(Unknown Source)
	at com.bigbrassband.jira.git.utils.concurrent.JiraAdaptedThreadFactory.lambda$wrap$1(JiraAdaptedThreadFactory.java:42)
	at com.bigbrassband.jira.git.utils.concurrent.cancel.CancellableJiraAdaptedThreadFactory.lambda$wrap$0(CancellableJiraAdaptedThreadFactory.java:24)
	at java.base/java.lang.Thread.run(Unknown Source)
Caused by: com.bigbrassband.jira.git.exceptions.internal.ExternalServiceException: {"type":"INSUFFICIENT_SCOPES","locations":[{"line":1,"column":1613}],"message":"Your token has not been granted the required scopes to execute this query. The 'id' field requires one of the following scopes: ['read:org'], but your token has only been granted the: ['repo'] scopes. Please modify your token's scopes at: https://github.com/settings/tokens."}
{"type":"INSUFFICIENT_SCOPES","locations":[{"line":1,"column":1616}],"message":"Your token has not been granted the required scopes to execute this query. The 'login' field requires one of the following scopes: ['read:org'], but your token has only been granted the: ['repo'] scopes. Please modify your token's scopes at: https://github.com/settings/tokens."}
{"type":"INSUFFICIENT_SCOPES","locations":[{"line":1,"column":1622}],"message":"Your token has not been granted the required scopes to execute this query. The 'name' field requires one of the following scopes: ['read:org'], but your token has only been granted the: ['repo'] scopes. Please modify your token's scopes at: https://github.com/settings/tokens."}
{"type":"INSUFFICIENT_SCOPES","locations":[{"line":1,"column":1627}],"message":"Your token has not been granted the required scopes to execute this query. The 'email' field requires one of the following scopes: ['read:org'], but your token has only been granted the: ['repo'] scopes. Please modify your token's scopes at: https://github.com/settings/tokens."}

	at com.bigbrassband.jira.git.services.integration.utils.graphql.BaseResponseHandler.parseError(BaseResponseHandler.java:104)
	at com.bigbrassband.jira.git.services.integration.utils.graphql.BaseResponseHandler.parseResponse(BaseResponseHandler.java:64)
	at com.bigbrassband.jira.git.services.integration.utils.graphql.BaseResponseHandler.handle(BaseResponseHandler.java:52)
	at com.bigbrassband.jira.git.services.integration.github.GitHubGraphQLClient.lambda$wrapByRateLimitHandler$7(GitHubGraphQLClient.java:371)
	at com.bigbrassband.jira.git.services.integration.utils.GraphQlClient.runRequest(GraphQlClient.java:97)
	at com.bigbrassband.jira.git.services.integration.utils.GraphQlClient.executeQuery(GraphQlClient.java:84)
	at com.bigbrassband.jira.git.services.integration.github.GitHubGraphQLClient.executeQuery(GitHubGraphQLClient.java:361)
	at com.bigbrassband.jira.git.services.integration.github.GitHubGraphQLClient.getPullRequestsTimeline(GitHubGraphQLClient.java:270)
	at com.bigbrassband.jira.git.services.integration.github.GitHubGraphQLClient.getPullRequestsTimeline(GitHubGraphQLClient.java:158)
	at com.bigbrassband.jira.git.services.integration.github.GitHubApi.getMergeRequestsTimeline(GitHubApi.java:296)
	... 20 more
```

&nbsp;

### Diagnosis

You are getting this error because of missing permission scopes.

Two new options are now available in General Settings. Enabling these options requires an "extended" scope for your PATs.

<img src='/wp-content/uploads/gij-datacenter-git-pull-merge-req-group-gencfg-sel.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

### Solution

To utilize the new GitHub share PR events, we recommend that users must update their personal access token to have the following scopes:
*   `read:discussion`
*   `read:org`
*   `read:user`
*   `repo` (all)
*   `user:email`

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

&nbsp;

### More articles about troubleshooting, workarounds and solutions

[Why I am getting the error, "git-upload-pack not permitted"?](/git-integration-for-jira-data-center/why-i-am-getting-the-error-git-upload-pack-not-permitted-gij-self-managed/)

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

[Problems with shared home on Azure Storage](/git-integration-for-jira-data-center/Problems-with-shared-home-on-azure-storage-gij-self-managed)

[Pull request index error: org.json.JSONException](/git-integration-for-jira-data-center/Pull-request-index-error--JSONException-gij-self-managed)

[Repositories missing from Azure DevOps integration](/git-integration-for-jira-data-center/Repositories-missing-from-azure-devops-integration-gij-self-managed)

["Service proxy has been destroyed" exceptions in log](/git-integration-for-jira-data-center/service-proxy-has-been-destroyed-exceptions-in-log-gij-self-managed)

[SQLException 'Incorrect string value' in merge requests](/git-integration-for-jira-data-center/sqlexception-incorrect-string-value-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

**Your token has not been granted the required scopes** (this page)

[When a GIJ license expires, it shows up as a session error to the user](/git-integration-for-jira-data-center/when-a-license-expires-a-session-error-is-shown-to-the-user-gij-self-managed)

[edDSA provider not supported WARN in logs](/git-integration-for-jira-data-center/edDSA-provider-not-supported-WARN-in-logs-gij-self-managed)

