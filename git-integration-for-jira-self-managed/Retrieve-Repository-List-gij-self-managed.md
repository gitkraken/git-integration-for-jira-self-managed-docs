---

title: Retrieve Repository List
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Retrieves list of repositories mapped to a given project.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Any Jira user can perform the Retrieve Repository List API call.
    </div>
    </div>
</div>

&nbsp;

### url
`/rest/gitplugin/1.0/`**repository**

### method
GET

### parameters

_**projectKey**_

Jira Project key (string). _**Optional**_.  Query parameter.  If omitted, all imported repositories will be returned.

**Example:** Form param (`projectKey`: **TST**)

### response
JSON

### Example:
`http://jira.yourorg.com/rest/gitplugin/1.0/repository?projectKey=TST`

```json
{
  "success": true,
  "repositories": [
    {
      "id": 2,
      "displayName": "testrepo",
      "origin": "https://github.com/xxx",
      "mainBranch": "master",
      "root": "xxx/xxx",
      "realRoot": "2_testrepo",
      "absoluteRoot": false,
      "disabled": false,
      "enableFetches": true,
      "sendCommitEmails": true,
      "maxMinsToCommitEmail": 1440,
      "global": true,
      "hosted": false,
      "initDate": 1606383040986,
      "lastIndexedDate": 1613815871685,
      "revisionIndexing": true,
      "gitViewerEnabled": true,
      "disableSslVerification": false,
      "smartCommitsEnabled": true,
      "viewFormat": "",
      "commitsValidationRequired": true,
      "requireUserPat": false,
      "projectMappingIds": [],
      "trackedFolderId": 11,
      "integrationType": "GITHUB",
      "showAllTags": true,
      "supportsBranchCreationApi": true,
      "supportsPullRequestApi": "PULL_REQUESTS_GROUP",
      "sourcesDiffViewEnabled": true,
      "refSpecNotes": true,
      "refSpecChanges": false,
      "trustFolderStat": true
    },
    {
      "id": 1,
      "displayName": "gitrepo",
      "origin": "https://xxx@xxx.gitlab.org/xxx",
      "mainBranch": "master",
      "root": "/xxx/xxx/xxx",
      "realRoot": "1_gitrepo",
      "absoluteRoot": false,
      "disabled": false,
      "enableFetches": true,
      "sendCommitEmails": true,
      "maxMinsToCommitEmail": 1440,
      "global": true,
      "hosted": false,
      "initDate": 1606383040986,
      "lastIndexedDate": 1613815870861,
      "revisionIndexing": true,
      "gitViewerEnabled": true,
      "disableSslVerification": false,
      "smartCommitsEnabled": true,
      "commitsValidationRequired": true,
      "requireUserPat": false,
      "projectMappingIds": [],
      "trackedFolderId": 11,
      "integrationType": "GITLAB",
      "showAllTags": true,
      "supportsBranchCreationApi": true,
      "supportsPullRequestApi": "MERGE_REQUESTS_GROUP",
      "sourcesDiffViewEnabled": true,
      "refSpecNotes": true,
      "refSpecChanges": false,
      "trustFolderStat": true
    }
  ]
}
```

&nbsp;

### Repository REST APIs

**Retrieve Repository List** (this page)

[Add New Repository](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed)

[Update Existing Repository](/git-integration-for-jira-data-center/update-existing-repository-gij-self-managed)

[Delete Existing Repository](/git-integration-for-jira-data-center/delete-existing-repository-gij-self-managed)

