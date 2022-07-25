---

title: Class IndexStatusResponse
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.rest.publicmodels](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > *com.bigbrassband.jira.git.rest.DefaultRestResponse* > [IndexStatusResponse](IndexStatusResponse-gij-self-managed)

Contains status of a reindex.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [IndexStatusResponse](#indexstatusresponse)() |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[Double](https://docs.oracle.com/javase/8/docs/api/java/lang/Double.html)*  | [getCompletionPercentage](#getcompletionpercentage)() |
| `public` `long` | [getErrorsCount](#geterrorscount)() |
| `public`  *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ReindexLogEntry](../../services/async/ReindexLogEntry-gij-self-managed)> | [getMessages](#getmessages)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getThreadId](#getthreadid)() |
| `public` `boolean` | [isFinished](#isfinished)() |
| `public` `void` | [setCompletionPercentage](#setcompletionpercentagedouble)( *[Double](https://docs.oracle.com/javase/8/docs/api/java/lang/Double.html)*  completionPercentage) |
| `public` `void` | [setFinished](#setfinishedboolean)(`boolean` finished) |
| `public` `void` | [setMessages](#setmessageslist)( *[List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)* <[ReindexLogEntry](../../services/async/ReindexLogEntry-gij-self-managed)> messages) |
| `public` `void` | [setThreadId](#setthreadidstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  threadId) |



# Constructors
## IndexStatusResponse()





# Methods
## getCompletionPercentage()
Returns completion percentage.



## getErrorsCount()
Returns number of errors appeared during the reindex.



## getMessages()



## getThreadId()
Reindex thread id.



## isFinished()
Returns whether the reindex is finished.



## setCompletionPercentage(Double)




## setFinished(boolean)




## setMessages(List<ReindexLogEntry>)




## setThreadId(String)





