---

title: Get Commit Issue Changes
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Returns the list of issues associated with the commit from the specified repository.

There are two types of users who can perform the Get Commit Issue Changes API call:

1.  Jira **administrators**

2.  Jira user who has **all** of the following:

    1.  **View/browse permissions** to the project;

    2.  **View Development Tools permissions** to the same project; and

    3.  The repository is **associated** to the project.


| **Get Commit Issue Changes** |     |

| _**url**_ | `http://`**<jira-host>**`/rest/gitplugin/1.0/`**repository**`/`**{repoId}**`/commits/`**{commitHash}**`/issues` |
| _**method**_ | GET |


| _**parameters**_ |     |
| --- | --- |
| **Parameter** | **Condition** |
| _**jira-host**_ | _String_. Required.<br><br>This is the default url location where you host your Jira.<br><br>For example:<br><br>`http://local-host-jira.com:2990`<br><br>`https://jira.your-organization.com` |
| _**repoId**_ | _Integer_. Required.<br><br>Substitute `{repoId}` with the actual repository ID.<br><br>Use the Repository REST API to obtain the connected repositories' IDs. |
| _**commitHash**_ | _String_. Required.<br><br>This is the hash of the commit that you want the results from.<br><br>**Example:**  `e012663bf9bd968388faa510cb5b310e4798c512` |
| _**response**_ | Returns the result for the example below. |

| **Example:** |
| --- |
| `http://`**local-host-jira.com:2990**`/rest/gitplugin/1.0/`**repository**`/`**1**`/commit/`**e012663bf9bd968388faa510cb5b310e4798c512**`/issues` |
| **Result:** |
| ```java<br>{<br> "success": true,<br> "issueKeys":[<br>     "TST-999",<br>     "NEXT-3",<br>     "TST-6",<br>     "TST-2",<br>     "TST-1"<br> ]<br>}<br>``` |

The resulting _**issueKeys**_ are the existing Jira issues that are currently associated with the commit that has the specified commit hash.

| **Example for GET queries:** |
| --- |
| ```powershell<br>GET /jira/rest/gitplugin/1.0/repository/1/commits/e012663bf9bd968388faa510cb5b310e4798c512/issues HTTP/1.1<br>Host: local-host-jira.com:2990<br>Content-Type: application/json<br>``` |

