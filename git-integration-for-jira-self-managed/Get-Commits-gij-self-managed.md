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

| Parameter | Condition |
| :--- | :--- |
| _**issueKey**_ | _String_. Required.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-234`. |

### Response

Returns the result in the example below.

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/issues/TST-234/commits`

```json
Returns the following example result:
 
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

&nbsp;

###  Commits REST APIs

**Get Commits** (this page)

[showFiles](/git-integration-for-jira-data-center/)

[Get Commit Issue Changes](/git-integration-for-jira-data-center/get-commit-issue-changes-gij-self-managed)

[Update Commit Issue Changes](/git-integration-for-jira-data-center/update-commit-issue-changes-gij-self-managed)

