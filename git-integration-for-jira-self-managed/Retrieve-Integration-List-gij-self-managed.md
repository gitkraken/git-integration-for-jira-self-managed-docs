---

title: Retrieve Integration List API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Retrieves the list of integrations and their respective parameter details from the git repository configuration.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Retrieve Integration List API call.
    </div>
    </div>
</div>

&nbsp;

### url
`{JiraBaseURL}/rest/gitplugin/1.0/integration`

### method
GET

### parameter
none
### Example

`http://jira.yourorg.com/rest/gitplugin/1.0/integration`

**Response example:**

```json
{
    "success": true,
    "integrations": [
        {
            "id": 1,
            "displayName": "https://github.com/*",
            "origin": "https://api.github.com",
            "disabled": false,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "initDate": 1675942373613,
            "lastIndexedDate": 1695470025397,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "prHideFilter": "^.*master.*$",
            "requireUserPat": false,
            "projectMappingIds": [
            ],
            "integrationType": "GITHUB",
            "showAllTags": true,
            "sourcesDiffViewEnabled": true,
            "refSpecNotes": true,
            "refSpecChanges": false,
            "trustFolderStat": true
        },
        {
            "id": 2,
            "displayName": "https://gitlab.com/*",
            "origin": "https://gitlab.com",
            "disabled": true,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "initDate": 1675942410674,
            "lastIndexedDate": 1686136525099,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "requireUserPat": false,
            "projectMappingIds": [
            ],
            "integrationType": "GITLAB",
            "showAllTags": true,
            "sourcesDiffViewEnabled": true,
            "refSpecNotes": true,
            "refSpecChanges": false,
            "trustFolderStat": true
        }        
    ]
}

```

&nbsp;

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

[Retrieve an Integration](/git-integration-for-jira-data-center/Retrieve-an-Integration-gij-self-managed)

**Retrieve Integration List** (this page)

