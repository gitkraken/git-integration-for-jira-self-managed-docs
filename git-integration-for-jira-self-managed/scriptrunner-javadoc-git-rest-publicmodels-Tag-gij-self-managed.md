---

title: ScriptRunner - Javadocs - Class Tag
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

* Package [com.bigbrassband.jira.git.rest.publicmodels](#)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  \> [Tag](#) (this page)

Tag information.


## Summary
#### Constructors
| Visibility | Signature |
| :--- | :--- |
| `public` | [Tag](#tag)() |
| `public` | [Tag](#tagtag)([Tag](#) other) |

#### Methods
| Type and modifiers | Method signature |
| :--- | :--- |
| `public` *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  | [getCommitDate](#getcommitdate)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitId](#getcommitid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitterEmail](#getcommitteremail)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCommitterName](#getcommittername)() |
| `public`  *[Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html)*  | [getCreationDate](#getcreationdate)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getCreationDateFormatted](#getcreationdateformatted)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getMessage](#getmessage)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getName](#getname)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getRepoId](#getrepoid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getRepoName](#getreponame)() |


# Constructors
## Tag()




## Tag(Tag)




# Methods

## getCommitDate()
Returns the commit date.


## getCommitId()
Returns the tag Id.



## getCommitterEmail()
Returns the author email.



## getCommitterName()
Returns the author name.



## getCreationDate()
Returns the creation date of the tag.



## getCreationDateFormatted()
Returns the creation date formatted according to Jira settings and user's timezone.



## getMessage()
Returns the tag message.



## getName()
Returns the tag name.



## getRepoId()
Returns the repository id the tag belongs to.



## getRepoName()
Returns the display name of the tag repository.



