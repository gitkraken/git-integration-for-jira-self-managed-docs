---

title: Class GIJFacade
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.services](README.html)
* [GIJFacade](GIJFacade.html)

This is the main facade to be used in ScriptRunner scripts.


## Summary
#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public` [Branch](scriptrunner/models/Branch.html) | [createBranch](#createbranchinteger-string-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  newBranchName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  baseBranchOrTag) |
| `public` [Repository](../rest/publicmodels/Repository.html) | [createIntegration](#createintegrationintegrationrequest)([IntegrationRequest](../rest/integration/IntegrationRequest.html) params) |
| `public` [PullRequest](scriptrunner/models/PullRequest.html) | [createPullRequest](#createpullrequestinteger-string-string-string-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  sourceBranchName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  targetBranchName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  title,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` [Repository](../rest/publicmodels/Repository.html) | [createRepository](#createrepositoryrepository)([Repository](../rest/publicmodels/Repository.html) params) |
| `public` `void` | [deleteBranch](#deletebranchinteger-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  branchName) |
| `public` `boolean` | [deleteIntegration](#deleteintegrationinteger-boolean)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId, `boolean` deleteFiles) |
| `public` `boolean` | [deleteRepository](#deleterepositoryinteger-boolean)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId, `boolean` deleteFiles) |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [doReindex](#doreindexinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId) |
| `public` `boolean` | [doReindexSynchronized](#doreindexsynchronizedinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Branch](scriptrunner/models/Branch.html)> | [getBranchesForIssue](#getbranchesforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Branch](scriptrunner/models/Branch.html)> | [getBranchesForIssue](#getbranchesforissuestring-boolean)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey, `boolean` forceAheadBehindCalculation) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > | [getCommitIssues](#getcommitissuesinteger-string)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Commit](../rest/publicmodels/Commit.html)> | [getCommitsForIssue](#getcommitsforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Commit](../rest/publicmodels/Commit.html)> | [getCommitsForIssue](#getcommitsforissuestring-boolean)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey,  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  showFiles) |
| `public` [Repository](../rest/publicmodels/Repository.html) | [getIntegration](#getintegrationinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  integrationId) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Repository](../rest/publicmodels/Repository.html)> | [getIntegrations](#getintegrations)() |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[PullRequest](scriptrunner/models/PullRequest.html)> | [getPullRequestsForIssue](#getpullrequestsforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` [IndexStatusResponse](../rest/publicmodels/IndexStatusResponse.html) | [getReindexStatus](#getreindexstatusstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  threadId) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Repository](../rest/publicmodels/Repository.html)> | [getRepositories](#getrepositories)() |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Repository](../rest/publicmodels/Repository.html)> | [getRepositories](#getrepositoriesstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  projectKey) |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* <[Tag](../rest/publicmodels/Tag.html)> | [getTagsForIssue](#gettagsforissuestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` `void` | [updateCommitIssueChanges](#updatecommitissuechangesinteger-string-issuesassociationrequest)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash, [IssuesAssociationRequest](../rest/publicmodels/IssuesAssociationRequest.html) request) |
| `public` [Repository](../rest/publicmodels/Repository.html) | [updateIntegration](#updateintegrationinteger-integrationrequest)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  id, [IntegrationRequest](../rest/integration/IntegrationRequest.html) repositoryWithNewParams) |
| `public` [Repository](../rest/publicmodels/Repository.html) | [updateRepository](#updaterepositoryrepository)([Repository](../rest/publicmodels/Repository.html) newParams) |



# Methods
## createBranch(Integer, String, String)




## createIntegration(IntegrationRequest)




## createPullRequest(Integer, String, String, String, String)


### **Parameters**
* `issueKey`: required, otherwise GIJException

### **Returns**


### **Throws**
* [GIJException](../exceptions/GIJException.html) 



## createRepository(Repository)




## deleteBranch(Integer, String)




## deleteIntegration(Integer, boolean)




## deleteRepository(Integer, boolean)




## doReindex(Integer)




## doReindexSynchronized(Integer)
Reindex a repository and waits for the end of the reindex.

### **Parameters**
* `repoId`: repository id to be reindexed

### **Returns**

### **Throws**
* [GIJException](../exceptions/GIJException.html) 
* *com.bigbrassband.jira.git.exceptions.operations.OperationException* - when 10 minutes was not enough to wait for reindexing to finish



## getBranchesForIssue(String)




## getBranchesForIssue(String, boolean)




## getCommitIssues(Integer, String)




## getCommitsForIssue(String)




## getCommitsForIssue(String, Boolean)




## getIntegration(Integer)




## getIntegrations()




## getPullRequestsForIssue(String)




## getReindexStatus(String)




## getRepositories()
Returns all repositories connected including disabled repositories and repositories in error status.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-getRepositories.groovy.md).

### **Throws**
* [GIJException](../exceptions/GIJException.html) 



## getRepositories(String)
Returns repositories visible to users of the project.
 <br>
 So repositories visible globally are returned also. Disabled repositories and repositories in ERROR status are excluded.
 <br>
 See [script example](/git-integration-for-jira-self-managed/javadoc/examples/scriptrunner-example-getRepositories-projectKey.groovy.md).

### **Parameters**
* `projectKey`: project key, e.g. "TST"

### **Throws**
* [GIJException](../exceptions/GIJException.html) 



## getTagsForIssue(String)




## updateCommitIssueChanges(Integer, String, IssuesAssociationRequest)




## updateIntegration(Integer, IntegrationRequest)




## updateRepository(Repository)





