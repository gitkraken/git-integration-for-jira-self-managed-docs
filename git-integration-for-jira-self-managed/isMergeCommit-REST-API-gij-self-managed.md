---

title: Merge Commit REST API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Returns the list of git commits which are found and identified to be merge commits.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>How to determine if a commit is a merge commit?</b><br>
        A git commit that has two or more parents is a merge commit.
    </div>
    </div>
</div>

&nbsp;

## isMergeCommit (Commits REST API extension)

### url
`/jira/rest/gitplugin/1.0/issues/JIRA_ISSUE_KEY/commits`

### method
GET

### content-type
application/json

### parameters
none

### response
Returns the result in the example below.

### Example usage:
`GET http://jira.yourorg.com/jira/rest/gitplugin/1.0/issues/TEST-1/commits`

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

### Commits REST APIs

[Get Commits](/git-integration-for-jira-data-center/get-Commits-gij-self-managed)

[showFiles](/git-integration-for-jira-data-center/showfiles-gij-self-managed)

[Get Commit Issue Changes](/git-integration-for-jira-data-center/get-commit-issue-changes-gij-self-managed)

[Update Commit Issue Changes](/git-integration-for-jira-data-center/update-commit-issue-changes-gij-self-managed)

**Merge Commit** (this page)

