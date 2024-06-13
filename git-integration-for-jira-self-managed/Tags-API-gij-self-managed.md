---

title: Tags API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Tag REST API returns several latest tags for the issue.  Tags are sorted in chronological order from newest to oldest.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        To perform the Tag API call, the Jira user must have the permission to <b>read</b> the requested issue.
    </div>
    </div>
</div>

&nbsp;

### url
`{JiraBaseURL}/rest/gitplugin/1.0/issuegitdetails/issue/{issuekey}/tag`

### method
GET

### Parameters

| Field | Description |
| :--- | :--- |
| _**issueKey**_ | _String_. Required. Path parameter.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-435`. |
| _**tagsPerRepository**_ | _Integer._ Required.<br><br>This parameter limits the total number of tags returned.<br><br>Use values greater than or equal to **1** <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>RECOMMENDED</b>.<br><br>Using the zero (0) value will return all tags linked to the issue but this greatly impacts Jira performance <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>NOT RECOMMENDED</b>.<br><br>**Example:**<br><br>`/rest/gitplugin/1.0/issuegitdetails/issue/TST-435/tag?tagsPerRepository=2` |

### Response

Returns the number of tags according to the parameter value for each repository associated with the issue.

The result contains tag elements with basic information such as name of a tag, associated commit data, associated repository settings, etc.

The additional flag _**hasMore**_ indicates if an issue contains more tags. Increasing the quantity number for `tagsPerRepository` will return a large collection result depending on the size of the parameter value  –  in case _**hasMore**_ has `true` as response.

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/issuegitdetails/issue/TEST-435/tag?tagsPerRepository=2`

**Result:**

```json
{
  "tags": [
    {
      "name": "test tag 1",
      "commitId": "4caf6aa4fd50ef42012863ce561bddba32557152",
      "repoId": 2,
      "repoName": "test-repo-01",
      "isGitViewerEnabled": true,
      "creationDateFormatted": "April 9, 2020 20:27:28 PM OMST",
      "committerName": "John Smith",
      "committerEmail": "johnsmith@example.com",
      "creationDate": 1617978448000
    },
    {
      "name": "test tag 2",
      "commitId": "90e902222248ae205ed6ed42cd037df8fbefc871",
      "repoId": 3,
      "repoName": "test-repo-02",
      "isGitViewerEnabled": true,
      "creationDateFormatted": "November 12, 2020 10:38:56 AM OMST",
      "message": "TEST-1 message",
      "committerName": "John Smith",
      "committerEmail": "johnsmith@example.com",
      "creationDate": 1605155936000
    }
  ],
  "isTagsFeatureEnabled": true,
  "hasMore": true,
  "calculationError": "",
  "firstTag": {
    "name": "testrepo-test-tag-01",
    "commitId": "a7141bf14e3a27c413b568c8d1f5a5f3a6a45135",
    "repoId": 1,
    "repoName": "test-repo-main",
    "isGitViewerEnabled": true,
    "creationDateFormatted": "April 5, 2018 11:52:11 AM OMST",
    "message": "TEST-1 tags per repo example",
    "committerName": "John Smith",
    "committerEmail": "johnsmith@example.com",
    "creationDate": 1459835531000
  }
}
```

&nbsp;

**[« Back to REST API index](/git-integration-for-jira-data-center/rest-api-gij-self-managed)**

