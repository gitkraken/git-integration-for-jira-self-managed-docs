---

title: Reindex GET API
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Use this method to track messages for a particular thread.

There are two types of users who can perform the Reindex GET API call:

1.  Jira **administrators**

2.  Jira user who has **all** of the following:

    1.  **View/browse permissions** to the project;

    2.  **View Development Tools permissions** to the same project; and

    3.  The repository is **associated** to the project.


|     |     |
| --- | --- |
| **Reindex GET API** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/index.json` |     |
| _**method**_ |     |
| GET |     |
| _**parameters**_ |     |
| **Parameter** | **Condition** |
| _**threadID**_ | _Required_.<br><br>Indexer thread ID (UUID).  Query parameter.<br><br>**Example:**<br><br>`eafe58fc-d8de-42ff-8815-6fe5860b38d2` |
| _**response**_ |     |
| JSON |     |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/index.json?`**threadId**`=`**eafe58fc-d8de-42ff-8815-6fe5860b38d2**<br><br>```java<br>Response:<br>{<br>  "success":true,<br>  "finished":true,<br>  "threadId":172,<br>  "messages": {<br>    "Indexing test-repo":100.0<br>    },<br>  "errors": {},<br>  "lastOperationPercent":100.0<br>}<br>``` |

### Related articles

*   Page:

    [Reindex POST API](/wiki/spaces/GIJDC/pages/380666409/Reindex+POST+API) (Git Integration for Jira Data Center)