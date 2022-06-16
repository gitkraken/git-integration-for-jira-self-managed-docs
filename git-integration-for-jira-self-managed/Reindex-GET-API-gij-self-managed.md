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


## Reindex GET API

_**url**_  -- `/rest/gitplugin/1.0/index.json`

_**method**_ -- GET

_**Parameters**_

| **Parameter** | **Condition** |
| :--- | :--- |
| _**threadID**_ | _Required_.<br><br>Indexer thread ID (UUID).  Query parameter.<br><br>**Example:**<br>`eafe58fc-d8de-42ff-8815-6fe5860b38d2` |
| _**response**_ | JSON |

<br>

**Example:**

`http://jira.yourorg.com/rest/gitplugin/1.0/index.json?`**threadId**`=`**eafe58fc-d8de-42ff-8815-6fe5860b38d2**

```java
Response:
{
    "success":true,
    "finished":true,
    "threadId":172,
    "messages": {
        "Indexing test-repo":100.0
    },
    "errors": {},
    "lastOperationPercent":100.0
}
```

