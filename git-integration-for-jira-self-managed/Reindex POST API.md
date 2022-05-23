---

title: Reindex POST API
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Starts the reindex process in a separate thread and returns the result immediately.

There are two types of users who can perform the Reindex POST API call:

1.  Jira **administrators**

2.  Jira user who has **all** of the following:

    1.  **View/browse permissions** to the project;

    2.  **View Development Tools permissions** to the same project; and

    3.  The repository is **associated** to the project.


|     |     |
| --- | --- |
| **Reindex POST API** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/index.json` |     |
| _**method**_ |     |
| POST |     |
| _**parameters**_ |     |
| **Parameter** | **Condition** |
| _**repoId**_ | _Array of Long_. Repository ID.  Form parameter.<br><br>**Example:**<br><br>Form param (`repoId: [133]`) |
| _**response**_ |     |
| JSON |     |

|     |
| --- |
| **Example:** |
| ```java<br>http://jira.yourorg.com/rest/gitplugin/1.0/index.json<br> <br>Body, JSON(application/json):<br>{<br>  "repoId": [133]<br>}<br> <br>-----------------------<br> <br>Response:<br>{<br>  "success":true,<br>  "finished":true,<br>  "threadId": xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx<br>}<br>``` |

