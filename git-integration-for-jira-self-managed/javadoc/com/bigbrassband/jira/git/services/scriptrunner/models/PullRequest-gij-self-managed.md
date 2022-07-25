---

title: Class PullRequest
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.services.scriptrunner.models](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [PullRequest](PullRequest-gij-self-managed)

Pull Request information.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [PullRequest](#pullrequest)() |
| `public` | [PullRequest](#pullrequeststring-string-string-string-string-string-string-repository)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  id,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  title,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  description,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  baseBranch,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  compareBranch,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  state,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  url, [Repository](../../../rest/publicmodels/Repository-gij-self-managed) repository) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getBaseBranch](#getbasebranch)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCompareBranch](#getcomparebranch)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getDescription](#getdescription)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getId](#getid)() |
| `public` [Repository](../../../rest/publicmodels/Repository-gij-self-managed) | [getRepository](#getrepository)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getState](#getstate)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getTitle](#gettitle)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getUrl](#geturl)() |



# Constructors
## PullRequest()




## PullRequest(String, String, String, String, String, String, String, Repository)





# Methods
## getBaseBranch()
Returns the pull request base branch.



## getCompareBranch()
Returns the pull request compare branch.



## getDescription()
Returns the pull request description.



## getId()
Returns the pull request id.



## getRepository()
Returns a repositry the pull request belongs to.



## getState()
Returns the pull request state, e.g. OPEN, MERGED, CLOSED.



## getTitle()
Returns the pull request title.



## getUrl()
Returns url to the pull request on a git server.




