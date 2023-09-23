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
`/rest/gitplugin/1.0/repository`

### method
GET

### parameters

| Field | Description |
| :--- | :--- |
| **all** | _Optional._ Also returns all the imported repositories. The **_all_** parameter can be safely ommitted, since adding it to the url just only make the request look formal. Cannot be used with other parameters. |
| _**projectKey**_ | _**Jira Project key (string)**_. Optional. <br>Query parameter. If omitted, all imported repositories will be returned.<br><br>**Example:**<br>Form param (`projectKey`: **TST**) |
| _**prHideFilter**_ | _String_. Optional. <br>Displays all pull requests for the specific issue, if left blank. Otherwise, set pull requests matching pattern to hide pull requests on issue pages that match the specified regular expression pattern. |

### response
JSON

### Example:
`http://jira.yourorg.com/rest/gitplugin/1.0/repository?projectKey=TEST`

```json
{
    "success": true,
    "repositories": [   
        {
            "id": 1,
            "group": "TestOrg",
            "displayName": "test-repo",
            "origin": "https://github.com/TestOrg/test-repo.git",
            "mainBranch": "master",
            "root": "..\\data\\git-plugin\\1_test-repo",
            "realRoot": "1_test-repo",
            "absoluteRoot": false,
            "disabled": false,
            "enableFetches": true,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "hosted": false,
            "initDate": 1675942388415,
            "lastIndexedDate": 1695468517355,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "webLinkType": "github",
            "viewFormat": "",
            "changesetFormat": "https://github.com/TestOrg/test-repo/commit/${rev}",
            "fileAddedFormat": "https://github.com/TestOrg/test-repo/commit/${rev}#diff-${sha256path}",
            "fileModifiedFormat": "https://github.com/TestOrg/test-repo/commit/${rev}#diff-${sha256path}",
            "fileDeletedFormat": "https://github.com/TestOrg/test-repo/commit/${rev}#diff-${sha256path}",
            "mergeRequestFormat": "https://github.com/TestOrg/test-repo/pull/${mergereqId}",
            "branchLinkFormat": "https://github.com/TestOrg/test-repo/tree/${branch}",
            "commitsValidationRequired": true,
            "requireUserPat": false,
            "projectMappingIds": [
            ],
            "trackedFolderId": 1,
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
            "id": 2,
            "group": "TestOrg",
            "displayName": "acme",
            "origin": "https://github.com/TestOrg/acme.git",
            "mainBranch": "main",
            "root": "..\\data\\git-plugin\\2_acme",
            "realRoot": "2_acme",
            "absoluteRoot": false,
            "disabled": false,
            "enableFetches": true,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "hosted": false,
            "initDate": 1675942385985,
            "lastIndexedDate": 1695468510019,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "webLinkType": "github",
            "viewFormat": "",
            "changesetFormat": "https://github.com/TestOrg/acme/commit/${rev}",
            "fileAddedFormat": "https://github.com/TestOrg/acme/commit/${rev}#diff-${sha256path}",
            "fileModifiedFormat": "https://github.com/TestOrg/acme/commit/${rev}#diff-${sha256path}",
            "fileDeletedFormat": "https://github.com/TestOrg/acme/commit/${rev}#diff-${sha256path}",
            "mergeRequestFormat": "https://github.com/TestOrg/acme/pull/${mergereqId}",
            "branchLinkFormat": "https://github.com/TestOrg/acme/tree/${branch}",
            "commitsValidationRequired": true,
            "requireUserPat": false,
            "projectMappingIds": [
            ],
            "trackedFolderId": 1,
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
            "id": 3,
            "group": "TestOrg",
            "displayName": "applanix-site-viewer",
            "origin": "https://github.com/TestOrg/applanix-site-viewer.git",
            "mainBranch": "master",
            "root": "..\\data\\git-plugin\\3_applanix-site-viewer",
            "realRoot": "3_applanix-site-viewer",
            "absoluteRoot": false,
            "disabled": false,
            "enableFetches": true,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "hosted": false,
            "initDate": 1675942392599,
            "lastIndexedDate": 1695468520018,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "webLinkType": "github",
            "viewFormat": "",
            "changesetFormat": "https://github.com/TestOrg/applanix-site-viewer/commit/${rev}",
            "fileAddedFormat": "https://github.com/TestOrg/applanix-site-viewer/commit/${rev}#diff-${sha256path}",
            "fileModifiedFormat": "https://github.com/TestOrg/applanix-site-viewer/commit/${rev}#diff-${sha256path}",
            "fileDeletedFormat": "https://github.com/TestOrg/applanix-site-viewer/commit/${rev}#diff-${sha256path}",
            "mergeRequestFormat": "https://github.com/TestOrg/applanix-site-viewer/pull/${mergereqId}",
            "branchLinkFormat": "https://github.com/TestOrg/applanix-site-viewer/tree/${branch}",
            "commitsValidationRequired": true,
            "requireUserPat": false,
            "projectMappingIds": [
            ],
            "trackedFolderId": 1,
            "integrationType": "GITHUB",
            "showAllTags": true,
            "supportsBranchCreationApi": true,
            "supportsPullRequestApi": "PULL_REQUESTS_GROUP",
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

