---

title: Branches API
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Branches REST API will obtain list of branches associated to a Jira issue.

There are two types of users who can perform the Branches API call:

1.  Jira **administrators**

2.  Jira user who has **all** of the following:

    1.  **View/browse permissions** to the project;

    2.  **View Development Tools permissions** to the same project; and

    3.  The repository is **associated** to the project.


|     |     |
| --- | --- |
| **Branches** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/issues/branches?`**key**`=`**{issuekey}** |     |
| _**method**_ |     |
| GET |     |
| _**parameters**_ |     |
| Parameter | Description |
| _**issueKey**_ | _String_. Optional.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-435`. |
| response |     |
| If the _optional query_ is not defined, it will return all indexed git branches. |     |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/issues/branches?`**key="TST-435"**<br><br>```java<br>Result:<br>{<br>    "success":true,<br>    "branches":["master","release","TST-435"]<br>}<br>``` |

### REST APIs

*   [Bulk Change API](/wiki/spaces/GIJDC/pages/380764495/Bulk+Change+API) (Git Integration for Jira Data Center)

*   [Repository API](/git-integration-for-jira-self-managed/Repository-API) (Git Integration for Jira Data Center)

*   [Reindex API](/git-integration-for-jira-self-managed/Reindex-API) (Git Integration for Jira Data Center)

*   [Commits API](/git-integration-for-jira-self-managed/Commits-API) (Git Integration for Jira Data Center)

*   [Branches API](/git-integration-for-jira-self-managed/Branches-API) (Git Integration for Jira Data Center)

*   [Integration API](/git-integration-for-jira-self-managed/Integration-API) (Git Integration for Jira Data Center)