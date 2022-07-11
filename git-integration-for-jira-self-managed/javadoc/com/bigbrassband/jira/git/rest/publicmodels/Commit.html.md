---

title: Class Commit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.rest.publicmodels](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [Commit](Commit.html)




## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [Commit](#commit)() |
| `public` | [Commit](#commitint-string-string-string-string-string-map-list-collection)(`int` repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  repoDisplayName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  date,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message,  *[Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* ,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > notes,  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ShortFileInfo](ShortFileInfo.html)> files,  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > branches) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getAuthor](#getauthor)() |
| `public`  *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > | [getBranches](#getbranches)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitId](#getcommitid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getDate](#getdate)() |
| `public`  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ShortFileInfo](ShortFileInfo.html)> | [getFiles](#getfiles)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getMessage](#getmessage)() |
| `public`  *[Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* ,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > | [getNotes](#getnotes)() |
| `public` *com.bigbrassband.jira.git.rest.publicmodels.Commit.Repository* | [getRepository](#getrepository)() |
| `public` `void` | [setAuthor](#setauthorstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  author) |
| `public` `void` | [setBranches](#setbranchescollection)( *[Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > branches) |
| `public` `void` | [setCommitId](#setcommitidstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitId) |
| `public` `void` | [setDate](#setdatestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  date) |
| `public` `void` | [setFiles](#setfileslist)( *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ShortFileInfo](ShortFileInfo.html)> files) |
| `public` `void` | [setMessage](#setmessagestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message) |
| `public` `void` | [setNotes](#setnotesmap)( *[Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html)* < *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* ,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* > notes) |



# Constructors
## Commit()




## Commit(int, String, String, String, String, String, Map<String, String>, List<Commit.ShortFileInfo>, Collection<String>)





# Methods
## getAuthor()




## getBranches()




## getCommitId()




## getDate()




## getFiles()




## getMessage()




## getNotes()




## getRepository()




## setAuthor(String)




## setBranches(Collection<String>)




## setCommitId(String)




## setDate(String)




## setFiles(List<Commit.ShortFileInfo>)




## setMessage(String)




## setNotes(Map<String, String>)





