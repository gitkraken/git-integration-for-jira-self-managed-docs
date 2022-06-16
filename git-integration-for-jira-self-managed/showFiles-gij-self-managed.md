---

title: showFiles
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Extend the Commits REST API to review which files changed related to a specific Jira issue by adding `?showfiles=[true|false]` as an optional parameter.

VERSION 2.11.0+  The repository _**id**_ and repository _**name**_ field in the response result was implemented.

To perform the _showFiles Commits_ API call, the Jira user must have the permission to **read** the requested issue.

| **showFiles (Commits REST API extension)** |     |
| --- | --- |
| _**url**_ | `/rest/gitplugin/1.0/issues/`**{issueKey}**`/commits{?`**showFiles**`=[`**true**`\|`**false**`]}` |
| _**method**_ | GET |

| _**parameters**_ |     |
| --- | --- |
| **Parameter** | **Condition** |
| _**issueKey**_ | _String_. Required.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-123`. |
| _**?showFiles=**_**\[**_**true\|false**_**\]** | _Boolean_. Optional.<br><br>When set to _**true**_, this extends the commits API to display which files where changed related to a specific Jira issue.<br><br>See usage example below. |
| _**response**_ | Returns the result in the example below. |

| **Example** |
| --- |
| **Usage:**  <br>`http://jira.yourorg.com/jira/rest/gitplugin/1.0/issues/`**TST-123**`/commits?`**showFiles=true**<br><br>```java<br>Returns the following example result, if showFiles=true:<br> <br>{<br>  "commits": [<br>    {<br>      "author": "msmith <mark@bigbrassband.com>",<br>      "commitId": "257b4a8490270014922f3b821d61c86e76166dd9",<br>      "date": "2015-12-07 10:54:56 +0600",<br>      "message": "message with TST-123",<br>      "repository": {  INTRODUCED V2.11.0+<br>        "id": 5,<br>        "name": "test repository name"<br>      },<br>      "branch": "master",<br>      "notes": {<br>        "refs/notes/commits": "TST-1 fixed also"<br>      },<br>      "files": [<br>        {<br>          "path": "testFile2.txt",<br>          "linesAdded": 1,<br>          "linesChanged": 0,<br>          "linesDeleted": 0,<br>          "added": true,<br>          "deleted": false,<br>        }<br>      ]<br>    }<br>  ]<br>}<br>``` |
