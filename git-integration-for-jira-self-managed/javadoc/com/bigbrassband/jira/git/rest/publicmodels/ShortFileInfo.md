---
  
title: Class ShortFileInfo
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.rest.publicmodels](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [ShortFileInfo](ShortFileInfo-gij-self-managed)

File changes information.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [ShortFileInfo](#shortfileinfofileinfo)(*com.bigbrassband.jira.git.services.issuetabpanels.summary.bean.FileInfo* fileInfo) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  | [getLinesAdded](#getlinesadded)() |
| `public`  *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  | [getLinesChanged](#getlineschanged)() |
| `public`  *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  | [getLinesDeleted](#getlinesdeleted)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getPath](#getpath)() |
| `public` `boolean` | [isAdded](#isadded)() |
| `public` `boolean` | [isDeleted](#isdeleted)() |
| `public` `void` | [setAdded](#setaddedboolean)(`boolean` added) |
| `public` `void` | [setDeleted](#setdeletedboolean)(`boolean` deleted) |
| `public` `void` | [setLinesAdded](#setlinesaddedlong)( *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  linesAdded) |
| `public` `void` | [setLinesChanged](#setlineschangedlong)( *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  linesChanged) |
| `public` `void` | [setLinesDeleted](#setlinesdeletedlong)( *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  linesDeleted) |
| `public` `void` | [setPath](#setpathstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  path) |



# Constructors
## ShortFileInfo(FileInfo)





# Methods
## getLinesAdded()
Returns number of lines added to the file in the git commit.



## getLinesChanged()
Returns number of lines changed in the file in the git commit.



## getLinesDeleted()
Returns number of lines deleted from the file in the git commit.



## getPath()
Returns the file path.



## isAdded()
Returns whether the file was added in the git commit.



## isDeleted()
Returns whether the file was deleted in the git commit.



## setAdded(boolean)




## setDeleted(boolean)




## setLinesAdded(Long)




## setLinesChanged(Long)




## setLinesDeleted(Long)




## setPath(String)





