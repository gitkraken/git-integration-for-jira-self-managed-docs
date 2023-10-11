---

title: Get Commits API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- Commits REST API -->

Call the Get Commits REST API to obtain commit information associated with an issue.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        To perform the Get Commits API call, the Jira user must have the permission to **read** the requested issue.
    </div>
    </div>
</div>

&nbsp;

### url
`/rest/gitplugin/1.0/issues/{issueKey}/commits`

### method
GET

### Parameters

| Field | Description |
| :--- | :--- |
| _**issueKey**_ | _String_. Required.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-234`. |
| **showFiles** | _Boolean_. Optional.<br><br>When set to _**true**_, this extends the commits API to display which files where changed related to a specific Jira issue.<br><br>See usage example below. |

### Response

Returns the result in the example below.

### Example - commits

`http://jira.yourorg.com/rest/gitplugin/1.0/issues/TST-234/commits`

Returns the following example result:

```json
{
  "commits":[
    {
    "author": "msmith <mark@bigbrassband.com>",
    "commitId": "34efa20372f0e2f0c9b705aacc57d7ad82e01426",
    "date": "2015-05-18T10:52:54.000+0000",
    "message": "TST-234 Update link in documentation",
    "repository": {  // INTRODUCED V2.11.0
        "id": 5,
        "name": "test repository name"
      },
      "branch": "master",
      "notes": {
        "refs/notes/commits": "TST-1 fixed also"
      },
    },
    {
    "author": "msmith <mark@bigbrassband.com>",
    "commitId": "52696c2d963be8986c7a2444b6473ea785632dce",
    "date": "2015-05-18T17:41:58.000+0000",
    "message": "TST-234 Remove libtiff dependency",
    }
  ]
}
```

### Example - showFiles

`http://jira.yourorg.com/jira/rest/gitplugin/1.0/issues/TEST-123/commits?showFiles=true`

Returns the following example result, if `showFiles=true`:

```json 
{
  "success": true,
  "commits": [
    {
      "author": "John Smith <john.smith@example.com>",
      "commitId": "2e7f45a5fc9cf30d1ef56051f1fda2d2270d8036",
      "isMergeCommit": true,
      "date": "2023-05-30T21:55:44+0700",
      "message": "Merge branch 'master' into TEST-2",
      "repository": {
        "id": 34,
        "name": "GIT-4188"
      },
      "notes": {},
      "branches": [
        "TEST-2"
      ]
    },
    {
      "author": "John Smith <john.smith@example.com>",
      "commitId": "c0a5c6a6c942e95d554326fa5265c4e0ba7e2f9a",
      "isMergeCommit": false,
      "date": "2023-05-30T21:31:25+0700",
      "message": "TEST-2 commit B",
      "repository": {
        "id": 34,
        "name": "GIT-4188"
      },
      "notes": {},
      "branches": [
        "TEST-2"
      ]
    }
  ]
}
```

&nbsp;

###  Commits REST APIs

**Get Commits** (this page)

[Get Commit Issue Changes](/git-integration-for-jira-data-center/get-commit-issue-changes-gij-self-managed)

[Update Commit Issue Changes](/git-integration-for-jira-data-center/update-commit-issue-changes-gij-self-managed)

