---

title: showFiles
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Extend the Commits REST API to review which files changed related to a specific Jira issue by adding `?showfiles=[true|false]` as an optional parameter.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        To perform the <i>showFiles Commits</i> API call, the Jira user must have the permission to <b>read</b> the requested issue.
    </div>
    </div>
</div>
<br>

## showFiles (Commits REST API extension)

### url
`/rest/gitplugin/1.0/issues/{issueKey}/commits{?showFiles=[true|false]}`

### method
GET

### parameters

| **Parameter** | **Condition** |
| :--- | :--- |
| _**issueKey**_ | _String_. Required.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-123`. |
| _**?showFiles=**_**\[**_**true\|false**_**\]** | _Boolean_. Optional.<br><br>When set to _**true**_, this extends the commits API to display which files where changed related to a specific Jira issue.<br><br>See usage example below. |
| _**response**_ | Returns the result in the example below. |

<br>

### Example usage:

`http://jira.yourorg.com/jira/rest/gitplugin/1.0/issues/TST-123/commits?showFiles=true`

```json
Returns the following example result, if showFiles=true:
 
{
  "commits": [
    {
      "author": "msmith <mark@bigbrassband.com>",
      "commitId": "257b4a8490270014922f3b821d61c86e76166dd9",
      "date": "2015-12-07 10:54:56 +0600",
      "message": "message with TST-123",
      "repository": {  INTRODUCED V2.11.0+
        "id": 5,
        "name": "test repository name"
      },
      "branch": "master",
      "notes": {
        "refs/notes/commits": "TST-1 fixed also"
      },
      "files": [
        {
          "path": "testFile2.txt",
          "linesAdded": 1,
          "linesChanged": 0,
          "linesDeleted": 0,
          "added": true,
          "deleted": false,
        }
      ]
    }
  ]
}
```

<br>

## Related articles on Commits API

[Get Commits](/git-integration-for-jira-data-center/get-Commits-gij-self-managed)

**showFiles** (this page)

[Get Commit Issue Changes](/git-integration-for-jira-data-center/get-commit-issue-changes-gij-self-managed)

[Update Commit Issue Changes](/git-integration-for-jira-data-center/update-commit-issue-changes-gij-self-managed)

