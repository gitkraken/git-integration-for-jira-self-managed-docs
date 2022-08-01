# Class Branch

* Package [com.bigbrassband.jira.git.services.scriptrunner.models](#)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [Branch](#)

Branch information.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [Branch](#branchstring-string-repository)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  name,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  externalUrl, [Repository](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-Repository-gij-self-managed) repository) |
| `public` | [Branch](#branchstring-string-int-int-repository)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  name,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  externalUrl, `int` ahead, `int` behind, [Repository](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-Repository-gij-self-managed) repository) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public` `int` | [getAhead](#getahead)() |
| `public` `int` | [getBehind](#getbehind)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getExternalUrl](#getexternalurl)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getName](#getname)() |
| `public` [Repository](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-Repository-gij-self-managed) | [getRepository](#getrepository)() |
| `public` `boolean` | [isAheadBehindPresented](#isaheadbehindpresented)() |



# Constructors
## Branch(String, String, Repository)




## Branch(String, String, int, int, Repository)





# Methods
## getAhead()
How far ahead is the branch from the main branch.



## getBehind()
How far behind is the branch from the main branch.



## getExternalUrl()
Link to the branch on github/gitlab/etc..



## getName()
Returns the branch name.



## getRepository()
Returns a repository the branch belongs to.



## isAheadBehindPresented()
Returns whether branch ahead and behind are defined/calculated/meaningful.




