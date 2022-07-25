---

title: Class GIJFacade
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.services](README.html)
* [GIJFacade](GIJFacade-gij-self-managed)

This is the main facade to be used in ScriptRunner scripts.


## Summary
#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public` [Branch](scriptrunner/models/Branch-gij-self-managed) | [createBranch](#createbranchinteger-string-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  newBranchName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  baseBranchOrTag) |
| `public` [Repository](../rest/publicmodels/Repository-gij-self-managed) | [createIntegration](#createintegrationintegrationrequest)([IntegrationRequest](../rest/integration/IntegrationRequest-gij-self-managed) params) |
| `public` [PullRequest](scriptrunner/models/PullRequest-gij-self-managed) | [createPullRequest](#createpullrequestinteger-string-string-string-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  sourceBranchName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  targetBranchName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  title,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` [Repository](../rest/publicmodels/Repository-gij-self-managed) | [createRepository](#createrepositoryrepository)([Repository](../rest/publicmodels/Repository-gij-self-managed) params) |
| `public` `void` | [deleteBranch](#deletebranchinteger-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  branchName) |
| `public` `boolean` | [deleteIntegration](#deleteintegrationinteger-boolean)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId, `boolean` deleteFiles) |
| `public` `boolean` | [deleteRepository](#deleterepositoryinteger-boolean)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId, `boolean` deleteFiles) |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [doReindex](#doreindexinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId) |
| `public` `boolean` | [doReindexSynchronized](#doreindexsynchronizedinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Branch](scriptrunner/models/Branch-gij-self-managed)> | [getBranchesForIssue](#getbranchesforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Branch](scriptrunner/models/Branch-gij-self-managed)> | [getBranchesForIssue](#getbranchesforissuestring-boolean)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey, `boolean` forceAheadBehindCalculation) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > | [getCommitIssues](#getcommitissuesinteger-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Commit](../rest/publicmodels/Commit-gij-self-managed)> | [getCommitsForIssue](#getcommitsforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Commit](../rest/publicmodels/Commit-gij-self-managed)> | [getCommitsForIssue](#getcommitsforissuestring-boolean)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey,  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  showFiles) |
| `public` [Repository](../rest/publicmodels/Repository-gij-self-managed) | [getIntegration](#getintegrationinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  integrationId) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Repository](../rest/publicmodels/Repository-gij-self-managed)> | [getIntegrations](#getintegrations)() |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[PullRequest](scriptrunner/models/PullRequest-gij-self-managed)> | [getPullRequestsForIssue](#getpullrequestsforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` [IndexStatusResponse](../rest/publicmodels/IndexStatusResponse-gij-self-managed) | [getReindexStatus](#getreindexstatusstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  threadId) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Repository](../rest/publicmodels/Repository-gij-self-managed)> | [getRepositories](#getrepositories)() |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Repository](../rest/publicmodels/Repository-gij-self-managed)> | [getRepositories](#getrepositoriesstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  projectKey) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Tag](../rest/publicmodels/Tag-gij-self-managed)> | [getTagsForIssue](#gettagsforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` `void` | [updateCommitIssueChanges](#updatecommitissuechangesinteger-string-issuesassociationrequest)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash, [IssuesAssociationRequest](../rest/publicmodels/IssuesAssociationRequest-gij-self-managed) request) |
| `public` [Repository](../rest/publicmodels/Repository-gij-self-managed) | [updateIntegration](#updateintegrationinteger-integrationrequest)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  id, [IntegrationRequest](../rest/integration/IntegrationRequest-gij-self-managed) repositoryWithNewParams) |
| `public` [Repository](../rest/publicmodels/Repository-gij-self-managed) | [updateRepository](#updaterepositoryrepository)([Repository](../rest/publicmodels/Repository-gij-self-managed) newParams) |



# Methods
## createBranch(Integer, String, String)
Creates a branch in the repository.
 <br>
 Branch can be created in a repository which belongs to an integration, otherwise GIJException is thrown.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-branch.groovy).

### **Parameters**
* `repoId`: the repository id
* `newBranchName`: a name of the new branch
* `baseBranchOrTag`: a name of a branch or a tag the new branch will be forked from

### **Returns**
branch created

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## createIntegration(IntegrationRequest)
Connect to an integration.
 <br><br>
 This is an async operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-integration.groovy).

### **Parameters**
* `params`: params for the new integration

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## createPullRequest(Integer, String, String, String, String)
Creates a new pull request.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-pull-request.groovy).

### **Parameters**
* `repoId`: a repository id where the new pull request will be created
* `sourceBranchName`: source branch
* `targetBranchName`: target branch
* `title`: the new pull request title
* `issueKey`: issue key, e.g. "TST-234"

### **Returns**

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## createRepository(Repository)
Connects a new repository.
 <br><br>
 This is an async operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-repository.groovy).
 See another [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-delete-reindex-repository.groovy).

### **Parameters**
* `params`: parameters of the new repository including origin, displayName, etc..

### **Throws**
* *org.eclipse.jgit.api.errors.GitAPIException* 
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## deleteBranch(Integer, String)
Deletes the branch.
 <br>
 Branch can be deleted from a repository which belongs to an integration, otherwise GIJException is thrown.
 <br><br>
 This is an async operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-delete-branch.groovy).

### **Parameters**
* `repoId`: the repository id
* `branchName`: a name of the branch to be deleted

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## deleteIntegration(Integer, boolean)
Delete an integration
 <br><br>
 This is a sync operation.

### **Parameters**
* `repoId`: an integration id to be deleted
* `deleteFiles`: indicates whether the repositories folders are also deleted from the Jira server. If set to true, the repositories folders is deleted from the Jira server.

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## deleteRepository(Integer, boolean)
Deletes the existing repository from the Git Integration for Jira app repository configuration.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-delete-reindex-repository.groovy).

### **Parameters**
* `repoId`: this is the ID of the existing repository. For example, 3.
* `deleteFiles`: indicates whether the repository folder is also deleted from the Jira server. If set to true, the repository folder is deleted from the Jira server.

### **Returns**
- true always

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## doReindex(Integer)
Starts the reindex process in a separate thread and returns the result immediately.
 <br>
 Reindex operation can be executed only by admin or a user having access to all repositories.
 <br><br>
 This is an async operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-start-reindex.groovy).

### **Parameters**
* `repoId`: repository id to be reindexed or null to reindex all

### **Returns**
- indexer thread ID (UUID), ex. "eafe58fc-d8de-42ff-8815-6fe5860b38d2"

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## doReindexSynchronized(Integer)
Reindex a repository and waits for the end of the reindex.
 <br>
 When 10 minutes was not enough to wait for reindexing to finish, then GIJException is thrown.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-start-sync-reindex.groovy).

### **Parameters**
* `repoId`: repository id to be reindexed or null to reindex all

### **Returns**

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## getBranchesForIssue(String)
Returns list of branches associated with the issue.
 <br>
 This is an alias for ```getBranchesForIssue(issueKey, false)```,
 i.e. a branch ahead and behind won't be calculated by intent, i.e. they might be undefined.
 <br><br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-get-branches-for-issue.groovy).

### **Parameters**
* `issueKey`: Jira issue key. The issueKey must be valid and existent. Ex.: "TST-234"

### **Throws**
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 
* *com.atlassian.jira.issue.index.IndexException* 



## getBranchesForIssue(String, boolean)
Returns list of branches associated with the issue.
 <br>
 When forceAheadBehindCalculation = true, then a branch ahead and behind will be gotten from a cache or calculated.
 <br><br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-get-branches-for-issue.groovy).

### **Parameters**
* `issueKey`: Jira issue key. The issueKey must be valid and existent. Ex.: "TST-234"
* `forceAheadBehindCalculation`: whether ahead and behind be calculated by force

### **Throws**
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 
* *com.atlassian.jira.issue.index.IndexException* 



## getCommitIssues(Integer, String)
Returns issues which the git commit associated with.

### **Parameters**
* `repoId`: a repository id of a commit
* `commitHash`: git commit id

### **Throws**
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 
* *com.atlassian.jira.issue.index.IndexException* 



## getCommitsForIssue(String)
Returns commits information associated with the issue.
 <br>
 Use getCommitsForIssue(String issueKey, Boolean showFiles) to get commits with files changed.
 <br><br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-get-commits-for-issue.groovy).

### **Parameters**
* `issueKey`: Jira issue key. The issueKey must be valid and existent. Ex.: "TST-234"

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  



## getCommitsForIssue(String, Boolean)
Returns commits information (including files) associated with the issue.

### **Parameters**
* `issueKey`: Jira issue key. The issueKey must be valid and existent. Ex.: "TST-234"
* `showFiles`: whether an information about files changed in the commit is collected and returned

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  



## getIntegration(Integer)
Returns an integration by id.

### **Parameters**
* `integrationId`: the integration id.

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## getIntegrations()
Returns integrations connected.

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## getPullRequestsForIssue(String)
Returns pull requests associated with the issue.

### **Parameters**
* `issueKey`: issue key, e.g. "TST-234"

### **Throws**
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 
* *com.atlassian.jira.issue.index.IndexException* 



## getReindexStatus(String)
Use this method to track messages for a particular reindex thread.
 <br><br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-ping-reindex-status.groovy).

### **Parameters**
* `threadId`: indexer thread ID (UUID), ex. "eafe58fc-d8de-42ff-8815-6fe5860b38d2"

### **Returns**
- reindex status, messages, errors

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## getRepositories()
Returns all repositories connected including disabled repositories and repositories in error status.
 <br><br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-getRepositories.groovy).

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## getRepositories(String)
Returns repositories visible to users of the project.
 <br>
 So repositories visible globally are returned also. Disabled repositories and repositories in ERROR status are excluded.
 <br><br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-getRepositories-projectKey.groovy).

### **Parameters**
* `projectKey`: project key, e.g. "TST"

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## getTagsForIssue(String)
Returns tags associated with the issue.

### **Parameters**
* `issueKey`: Jira issue key. The issueKey must be valid and existent. Ex.: "TST-234"

### **Throws**
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 
* *com.atlassian.jira.issue.index.IndexException* 



## updateCommitIssueChanges(Integer, String, IssuesAssociationRequest)
Changes the commit issues associations.
 <br>
 A change of the commit issues associations in a disabled repository will be ignored.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-update-commit-issue-changes.groovy).

### **Parameters**
* `repoId`: a repository id which the git commit belongs to
* `commitHash`: a git commit id
* `request`: a list of associations changes to be applied

### **Throws**
*  *[IOException](https://docs.oracle.com/javase/8/docs/api/java/io/IOException.html)*  
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## updateIntegration(Integer, IntegrationRequest)
Updated an integration.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-update-integration.groovy).

### **Parameters**
* `id`: integration id to be updated
* `repositoryWithNewParams`: new values for parameters to be changed

### **Returns**
- the integration updated

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 



## updateRepository(Repository)
Updates the existing repository from the given settings.
 <br>
 newParams.id is required. This is the ID of the existing repository. For example, `newParams.setId(3)`.
 <br>
 The updateRepository() API will look for the repository with `id = 3` and replaces repository properties with ones setup in newParams.
 <br><br>
 This is a sync operation.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-create-delete-reindex-repository.groovy).

### **Parameters**
* `newParams`: new values for parameters to be changed

### **Returns**
- repository updated

### **Throws**
* [GIJException](../exceptions/GIJException-gij-self-managed) 




