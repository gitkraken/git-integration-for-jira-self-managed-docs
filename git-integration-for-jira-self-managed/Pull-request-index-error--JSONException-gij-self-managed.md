---

title: Pull request index error -- org.json.JSONException
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- TROUBLESHOOTING -->

### Problem

Pull requests (or merge requests in GitLab) do not index and the pull request index (pullreqsIndexInfo.json inside `jira/home/caches/indexes/plugins/jira-git-pull-requests`) is broken.

**Example locations:**

`jira/home/caches/indexes/plugins/jira-git-pull-requests/2/pullreqs/pullreqsIndexInfo.json`

`jira/home/caches/indexes/plugins/jira-git-pull-requests/3/pullreqs/pullreqsIndexInfo.json`

&nbsp;

### Diagnosis

Jira admins will see a message similar to the one below in the Jira `/application-logs/atlassian-jira.log`:

```java
2018/01/16 22:30:20 Can't do reindex of merge requests java.io.IOException: Can't do reindex of merge requests
    at com.xiplink.jira.git.revisions.PullRequestIndexManagerImpl.pullRequestException(PullRequestIndexManagerImpl.java:157)
    at com.xiplink.jira.git.revisions.PullRequestIndexManagerImpl.updatePullReqIndex(PullRequestIndexManagerImpl.java:151)
    at com.xiplink.jira.git.revisions.GitPluginIndexManagerImpl.updateIndexImpl(GitPluginIndexManagerImpl.java:409)
    at com.xiplink.jira.git.revisions.GitPluginIndexManagerImpl.updateIndex(GitPluginIndexManagerImpl.java:431)
    at com.xiplink.jira.git.revisions.RevisionIndexerImpl$1.doRun(RevisionIndexerImpl.java:300)
    at com.xiplink.jira.git.revisions.RevisionIndexerImpl$QueueEntry.run(RevisionIndexerImpl.java:123)
    at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
    at java.util.concurrent.FutureTask.run(FutureTask.java:266)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
    at java.lang.Thread.run(Thread.java:745)
Caused by: org.json.JSONException: A JSONObject text must begin with '{' at 1 [character 2 line 1]
    at org.json.JSONTokener.syntaxError(JSONTokener.java:433)
    at org.json.JSONObject.<init>(JSONObject.java:194)
    at org.json.JSONObject.<init>(JSONObject.java:321)
    at com.bigbrassband.common.indexer.PullreqIndexer.indexPullRequests(PullreqIndexer.java:60)
    at com.xiplink.jira.git.revisions.PullRequestIndexManagerImpl.updatePullReqIndex(PullRequestIndexManagerImpl.java:149)
    ... 9 more
```

&nbsp;

### Solutions

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This issue should be resolved in <b>v3.5.0.2+</b>. If similar issue is found in later versions, please contact us at <a href='gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

1.  Verify that the Git Integration for Jira app does not have a reindex process in progress.

2.  Disable the Git Integration for Jira app in Jira Administration ➜ **Manage apps**.

3.  Remove the folder `/jira/home/caches/indexes/plugins/jira-git-pull-requests/` from the file system.

4.  Enable the Git Integration for Jira app in Jira Administration ➜ **Manage apps**.

5.  Start a reindex of the Git Integration for Jira app.

&nbsp;

### Resolution

`jira/home/caches/indexes/plugins/jira-git-pull-requests/` will be recreated.

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

[Personal access token failing Azure DevOps integration with Not Authorized error](/git-integration-for-jira-data-center/Personal-access-token-failing-azure-devops-integration-with-Not-Authorized-error-gij-self-managed)

[Problems with shared home on Azure Storage](/git-integration-for-jira-data-center/Problems-with-shared-home-on-azure-storage-gij-self-managed)

**Pull request index error: org.json.JSONException** (this page)

[Repositories missing from Azure DevOps integration](/git-integration-for-jira-data-center/Repositories-missing-from-azure-devops-integration-gij-self-managed)

["Service proxy has been destroyed" exceptions in log](/git-integration-for-jira-data-center/service-proxy-has-been-destroyed-exceptions-in-log-gij-self-managed)

[SQLException 'Incorrect string value' in merge requests](/git-integration-for-jira-data-center/sqlexception-incorrect-string-value-in-merge-requests-gij-self-managed)

[SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed)

[TFS - Not authorized exception when Jira works thru proxy](/git-integration-for-jira-data-center/tfs-not-authorized-exception-when-jira-works-thru-proxy-gij-self-managed)

[Unexpected exception parsing XML document from URL error in log](/git-integration-for-jira-data-center/Unexpected-exception-parsing-XML-document-from-URL-error-in-log-gij-self-managed)

[Why don't I see the Create Branch or Pull Request features?](/git-integration-for-jira-data-center/why-dont-i-see-the-create-branch-or-pull-request-features-gij-self-managed)

[Your token has not been granted the required scopes](/git-integration-for-jira-data-center/Your-token-has-not-been-granted-the-required-scopes-gij-self-managed)

