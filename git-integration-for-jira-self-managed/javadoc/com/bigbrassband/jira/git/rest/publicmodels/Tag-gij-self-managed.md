---
  
title: Class Tag
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.rest.publicmodels](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [Tag](Tag-gij-self-managed)

Tag information.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [Tag](#tag)() |
| `public` | [Tag](#tagtag)([Tag](Tag-gij-self-managed) other) |
| `public` | [Tag](#tagstring-string-integer-string-date-string-string-string-string)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  name,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitId,  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  repoName,  *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  creationDate,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  creationDateFormatted,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  committerName,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  committerEmail) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitId](#getcommitid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitterEmail](#getcommitteremail)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitterName](#getcommittername)() |
| `public`  *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  | [getCreationDate](#getcreationdate)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCreationDateFormatted](#getcreationdateformatted)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getMessage](#getmessage)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getName](#getname)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getRepoId](#getrepoid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getRepoName](#getreponame)() |
| `public` `void` | [setCommitId](#setcommitidstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  commitId) |
| `public` `void` | [setCommitterEmail](#setcommitteremailstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  committerEmail) |
| `public` `void` | [setCommitterName](#setcommitternamestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  committerName) |
| `public` `void` | [setCreationDate](#setcreationdatedate)( *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  creationDate) |
| `public` `void` | [setCreationDateFormatted](#setcreationdateformattedstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  creationDateFormatted) |
| `public` `void` | [setMessage](#setmessagestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message) |
| `public` `void` | [setName](#setnamestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  name) |
| `public` `void` | [setRepoId](#setrepoidinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  repoId) |
| `public` `void` | [setRepoName](#setreponamestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  repoName) |



# Constructors
## Tag()




## Tag(Tag)




## Tag(String, String, Integer, String, Date, String, String, String, String)





# Methods
## getCommitId()
Returns the tag Id.



## getCommitterEmail()
Returns author email.



## getCommitterName()
Returns author name.



## getCreationDate()
Returns a creation date of the tag.



## getCreationDateFormatted()
Returns a creation date formatted according to Jira settings and user's timezone.



## getMessage()
Returns the tag message.



## getName()
Returns the tag name.



## getRepoId()
Returns a repository id the tag belongs to.



## getRepoName()
Returns a display name of the tag repository.



## setCommitId(String)




## setCommitterEmail(String)




## setCommitterName(String)




## setCreationDate(Date)




## setCreationDateFormatted(String)




## setMessage(String)




## setName(String)




## setRepoId(Integer)




## setRepoName(String)





