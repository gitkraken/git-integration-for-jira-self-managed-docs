# Class IssuesAssociationRequest

* Package [com.bigbrassband.jira.git.rest.publicmodels](#)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  \> [IssuesAssociationRequest](#) (this page)



## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [IssuesAssociationRequest](#issuesassociationrequest)() |
| `public` | [IssuesAssociationRequest](#issuesassociationrequestlist)( *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> changeStrs) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public` [IssuesAssociationRequest](IssuesAssociationRequest.html.md) | [addLink](#addlinkstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public`  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> | [getChangeStrs](#getchangestrs)() |
| `public` [IssuesAssociationRequest](IssuesAssociationRequest.html.md) | [removeLink](#removelinkstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` `void` | [setChangeStrs](#setchangestrslist)( *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> changeStrs) |
| `public`  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* \<[CommitIssueChange](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-services-indexer-revisions-CommitIssueChange-gij-self-managed)\> | [transform](#transformstring-string-int)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash, `int` commitTime) |



# Constructors
## IssuesAssociationRequest()




## IssuesAssociationRequest(List\<String\>)





# Methods
## addLink(String)




## getChangeStrs()




## removeLink(String)




## setChangeStrs(List\<String\>)




## transform(String, String, int)





