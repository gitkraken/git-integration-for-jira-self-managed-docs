---

title: Class CommitIssueChange
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.services.indexer.revisions](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [CommitIssueChange](CommitIssueChange-gij-self-managed)



## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [CommitIssueChange](#commitissuechange)() |
| `public` | [CommitIssueChange](#commitissuechangedate-string-string-string-int)( *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  time,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  changeStr, `int` commitTime) |
| `public` | [CommitIssueChange](#commitissuechangedate-string-string-string-boolean-int)( *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  time,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash, `boolean` isAdded, `int` commitTime) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public` [CommitIssueChange](CommitIssueChange-gij-self-managed) | [add](#addcommitissuechange)([CommitIssueChange](CommitIssueChange-gij-self-managed) change2) |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getAuthor](#getauthor)() |
| `public` [ChangeStr](ChangeStr-gij-self-managed) | [getChangeStr](#getchangestr)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitHash](#getcommithash)() |
| `public` `int` | [getCommitTime](#getcommittime)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getIssueKey](#getissuekey)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getRepoId](#getrepoid)() |
| `public`  *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  | [getTime](#gettime)() |
| `public` `boolean` | [isAdded](#isadded)() |
| `public` `boolean` | [isValid](#isvalid)() |
| `public` `void` | [setAuthor](#setauthorstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author) |
| `public` `void` | [setChangeStr](#setchangestrchangestr)([ChangeStr](ChangeStr-gij-self-managed) changeStr) |
| `public` `void` | [setCommitHash](#setcommithashstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitHash) |
| `public` `void` | [setCommitTime](#setcommittimeint)(`int` commitTime) |
| `public` `void` | [setIsAdded](#setisaddedboolean)(`boolean` addedOrDeleted) |
| `public` `void` | [setIssueKey](#setissuekeystring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  issueKey) |
| `public` `void` | [setRepoId](#setrepoidinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId) |
| `public` `void` | [setTime](#settimedate)( *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  time) |



# Constructors
## CommitIssueChange()




## CommitIssueChange(Date, String, String, String, int)




## CommitIssueChange(Date, String, String, String, boolean, int)





# Methods
## add(CommitIssueChange)




## getAuthor()




## getChangeStr()




## getCommitHash()




## getCommitTime()




## getIssueKey()




## getRepoId()




## getTime()




## isAdded()




## isValid()




## setAuthor(String)




## setChangeStr(CommitIssueChange.ChangeStr)




## setCommitHash(String)




## setCommitTime(int)




## setIsAdded(boolean)




## setIssueKey(String)




## setRepoId(Integer)




## setTime(Date)





