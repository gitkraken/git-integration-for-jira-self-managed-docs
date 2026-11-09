---

title: ScriptRunner - Javadocs - Class Commit
description: "Commit, the ScriptRunner API model for Git commit information, with its fields and methods."
product: Git Integration for Jira Data Center
feature: ScriptRunner
content_type: api-reference
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2022-08
llms_include: true
tags: [scriptrunner, javadoc, api, commit, commits]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "features-gij-self-managed"
    nav_label: "Class Commit"
    nav_order: 20
    nav_parent: "scriptrunner-javadoc-git-services-gijfacade-gij-self-managed"
    page_type: "content"
---

* Package [com.bigbrassband.jira.git.rest.publicmodels](#)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  \> [Commit](#) (This page)

Git commit information.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [Commit](#commit)() |
| `public` | [Commit](#commitint-string-string-string-string-string-map-list-collection)(`int` repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  repoDisplayName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  date,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message,  *[Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* ,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > notes,  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ShortFileInfo](ShortFileInfo.html.md)\> files,  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> branches) |

#### Methods
| Type and modifiers | Method signature |
| :--- | :--- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getAuthor](#getauthor)() |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> | [getBranches](#getbranches)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitId](#getcommitid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getDate](#getdate)() |
| `public`  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* \<[ShortFileInfo](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-ShortFileInfo-gij-self-managed/)\> | [getFiles](#getfiles)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getMessage](#getmessage)() |
| `public`  *[Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* ,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> | [getNotes](#getnotes)() |
| `public` [RepositoryShortInfo](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-RepositoryShortInfo-gij-self-managed/) | [getRepository](#getrepository)() |
| `public` `void` | [setAuthor](#setauthorstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author) |
| `public` `void` | [setBranches](#setbranchescollection)( *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* >\ branches) |
| `public` `void` | [setCommitId](#setcommitidstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitId) |
| `public` `void` | [setDate](#setdatestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  date) |
| `public` `void` | [setFiles](#setfileslist)( *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ShortFileInfo](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-ShortFileInfo-gij-self-managed/)> files) |
| `public` `void` | [setMessage](#setmessagestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message) |
| `public` `void` | [setNotes](#setnotesmap)( *[Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)* \< *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* ,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* \> notes) |



# Constructors
## Commit()




## Commit(int, String, String, String, String, String, Map\<String, String\>, List\<Commit.ShortFileInfo\>, Collection\<String\>)





# Methods
## getAuthor()
Returns commit author, e.g. "John Smith"



## getBranches()
Returns list of branches the git commit belongs to.



## getCommitId()
Returns git commit id, e.g. "34efa20372f0e2f0c9b705aacc57d7ad82e01426"



## getDate()
Returns git commit date in ISO format using timezone of the current user, e.g. "2022-07-15T00:20:58+0000"



## getFiles()
Returns files changed in the git commit.



## getMessage()
Returns git commit message.



## getNotes()
Returns notes of the git commit, where a map key is a note namespace, a map value is a note message.



## getRepository()
Returns a repository which the git commit belongs to.



## setAuthor(String)




## setBranches(Collection\<String\>)




## setCommitId(String)




## setDate(String)




## setFiles(List<Commit.ShortFileInfo>)




## setMessage(String)




## setNotes(Map\<String, String\>)




