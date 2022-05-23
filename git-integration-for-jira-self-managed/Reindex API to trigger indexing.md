---

title: Reindex API to trigger indexing
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Call the [Reindex REST API](/wiki/spaces/GIJDC/pages/380699270) to have more control on indexing.

|     |
| --- |
| **Reindex POST API** |
| Use this method to start the reindex process in a separate thread. |
| Example:<br><br>```java<br>http://jira.yourorg.com/rest/gitplugin/1.0/index.json<br>``` |

|     |
| --- |
| **Reindex GET API** |
| Use this method to track messages for a particular thread. |
| Example:<br><br>```java<br>http://jira.yourorg.com/rest/gitplugin/1.0/index.json?threadId=eafe58fc-d8de-42ff-8815-6fe5860b38d2<br>``` |



[« Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317)

[Recommended reindex interval setting »](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting)

