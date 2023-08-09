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

| Field | Description |
| :--- | :--- |
| _**projectKey**_ | _**Jira Project key (string)**_. Optional. <br>Query parameter. If omitted, all imported repositories will be returned.<br><br>**Example:**<br>Form param (`projectKey`: **TST**) |
| _**prHideFilter**_ | _String_. Optional. <br>Displays all pull requests for the specific issue, if left blank. Otherwise, set pull requests matching pattern to hide pull requests on issue pages that match the specified regular expression pattern. |

### response
JSON

### Example:
`http://jira.yourorg.com/rest/gitplugin/1.0/repository?projectKey=TST`

```json
{
    "success": true,
    "integrations": [
    {
        "id": 1,
        "displayName": "https://github.com/",
        "origin": "https://api.github.com",
        "disabled": false,
        "sendCommitEmails": true,
        "maxMinsToCommitEmail": 1440,
        "global": true,
        "initDate": 1685725083439,
        "lastIndexedDate": 1685728181726,
        "revisionIndexing": true,
        "gitViewerEnabled": true,
        "disableSslVerification": false,
        "smartCommitsEnabled": true,
        "prHideFilter": "",
        "requireUserPat": false,
        "projectMappingIds": [],
        "integrationType": "GITHUB",
        "showAllTags": true,
        "sourcesDiffViewEnabled": true,
        "apiFilter": "[?contains(name, 'long')]",
        "refSpecNotes": true,
        "refSpecChanges": false,
        "trustFolderStat": true
    },
    {
        "id": 3,
        "displayName": "https://gitlab.com/",
        "origin": "https://gitlab.com",
        "disabled": false,
        "sendCommitEmails": true,
        "maxMinsToCommitEmail": 1440,
        "global": true,
        "initDate": 1685731335247,
        "lastIndexedDate": 1685731345075,
        "revisionIndexing": true,
        "gitViewerEnabled": true,
        "disableSslVerification": false,
        "smartCommitsEnabled": true,
        "requireUserPat": false,
        "projectMappingIds": [],
        "integrationType": "GITLAB",
        "showAllTags": true,
        "sourcesDiffViewEnabled": true,
        "apiFilter": "[?contains(name, 'Release-test-GIJ-GitLab-PAT')]",
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

