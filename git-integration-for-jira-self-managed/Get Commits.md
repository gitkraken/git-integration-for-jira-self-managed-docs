---

title: Get Commits
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Call the Get Commits REST API to obtain commit information associated with an issue.

VERSION 2.11.0+ The repository _**id**_ and repository _**name**_ field in the response result was implemented.

To perform the Get Commits API call, the Jira user must have the permission to **read** the requested issue.

|     |     |
| --- | --- |
| **Get Commits** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**issues**`/`**{issueKey}**`/commits` |     |
| _**method**_ |     |
| GET |     |
| _**parameters**_ |     |
| **Parameter** | **Condition** |
| _**issueKey**_ | _String_. Required.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-234`. |
| _**response**_ |     |
| Returns the result in the example below. |     |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**issues**`/`**TST-234**`/commits`<br><br>```java<br>Returns the following example result:<br> <br>{<br>  "commits":[<br>    {<br>    "author": "msmith <mark@bigbrassband.com>",<br>    "commitId": "34efa20372f0e2f0c9b705aacc57d7ad82e01426",<br>    "date": "2015-05-18T10:52:54.000+0000",<br>    "message": "TST-234 Update link in documentation",<br>    "repository": {  // INTRODUCED V2.11.0<br>        "id": 5,<br>        "name": "test repository name"<br>      },<br>      "branch": "master",<br>      "notes": {<br>        "refs/notes/commits": "TST-1 fixed also"<br>      },<br>    },<br>    {<br>    "author": "msmith <mark@bigbrassband.com>",<br>    "commitId": "52696c2d963be8986c7a2444b6473ea785632dce",<br>    "date": "2015-05-18T17:41:58.000+0000",<br>    "message": "TST-234 Remove libtiff dependency",<br>    }<br>  ]<br>}<br>``` |

### Related articles

*   Page:

    [Get Commits](/wiki/spaces/GIJDC/pages/380764568/Get+Commits) (Git Integration for Jira Data Center)

*   Page:

    [showFiles](/wiki/spaces/GIJDC/pages/380699289/showFiles) (Git Integration for Jira Data Center)

*   Page:

    [Get Commit Issue Changes](/wiki/spaces/GIJDC/pages/380797314/Get+Commit+Issue+Changes) (Git Integration for Jira Data Center)

*   Page:

    [Update Commit Issue Changes](/wiki/spaces/GIJDC/pages/380699298/Update+Commit+Issue+Changes) (Git Integration for Jira Data Center)