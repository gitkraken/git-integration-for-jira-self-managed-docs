---

title: ScriptRunner - Javadocs - Class PullRequest
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
<!-- The methods - public - Repository link is flagged as 404 by web crawlers. This is intended as is. -->

* Package [com.bigbrassband.jira.git.services.scriptrunner.models](#)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  \> [PullRequest](#) (this page)

Pull Request information.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [PullRequest](#pullrequest)() |
| `public` | [PullRequest](#pullrequeststring-string-string-string-string-string-string-repository)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  id,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  title,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  description,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  baseBranch,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  compareBranch,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  state,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  url, [Repository](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-Repository-gij-self-managed/) repository) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getBaseBranch](#getbasebranch)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCompareBranch](#getcomparebranch)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getDescription](#getdescription)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getId](#getid)() |
| `public` [Repository](../../../rest/publicmodels/Repository.html.md) | [getRepository](#getrepository)() |
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
Returns a repository the pull request belongs to.



## getState()
Returns the pull request state, e.g. `OPEN`, `MERGED`, `CLOSED`.



## getTitle()
Returns the pull request title.



## getUrl()
Returns url to the pull request on a git server.




