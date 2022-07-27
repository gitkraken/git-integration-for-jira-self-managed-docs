---

title: Class ReindexLogEntry
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.services.async](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [ReindexLogEntry](ReindexLogEntry-gij-self-managed)

Contains a reindex message.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [ReindexLogEntry](#reindexlogentry)() |
| `public` | [ReindexLogEntry](#reindexlogentrystring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message) |
| `public` | [ReindexLogEntry](#reindexlogentrystring-boolean)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  errorMessage, `boolean` isError) |
| `public` | [ReindexLogEntry](#reindexlogentrystring-throwable)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  errorMsg,  *[Throwable](https://docs.oracle.com/javase/8/docs/api/java/lang/Throwable.html)*  ex) |
| `public` | [ReindexLogEntry](#reindexlogentrylong-boolean-string-string)(`long` time, `boolean` error,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  details) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getDetails](#getdetails)() |
| `public` `long` | [getInsertionTime](#getinsertiontime)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getMessage](#getmessage)() |
| `public` `boolean` | [isError](#iserror)() |
| `public` `void` | [setDetails](#setdetailsstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  details) |
| `public` `void` | [setError](#seterrorboolean)(`boolean` error) |
| `public` `void` | [setInsertionTime](#setinsertiontimelong)(`long` insertionTime) |
| `public` `void` | [setMessage](#setmessagestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  message) |



# Constructors
## ReindexLogEntry()




## ReindexLogEntry(String)




## ReindexLogEntry(String, boolean)




## ReindexLogEntry(String, Throwable)




## ReindexLogEntry(long, boolean, String, String)





# Methods
## getDetails()
If an exception was thrown then the details contain the exception stacktrace.



## getInsertionTime()
Unix time of the message measured in milliseconds.



## getMessage()
Returns the message.



## isError()
Returns whether the messages is an error message.



## setDetails(String)




## setError(boolean)




## setInsertionTime(long)




## setMessage(String)





