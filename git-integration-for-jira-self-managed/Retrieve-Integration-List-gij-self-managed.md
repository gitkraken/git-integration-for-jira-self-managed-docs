---

title: Retrieve Integration List
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Retrieves the list of integrations and their respective parameter details from the git repository configuration.

Only Jira admins can perform the Retrieve Integration List API call.

## Retrieve Integration List

### url
`/rest/gitplugin/1.0/`**integration**

### method
GET

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**

**Response example:**

```json
{
    "success": "true",
    "integrations": [        
        {
            "id": 1,
            "displayName": "https://dev.azure.com",
            "origin": "https://dev.azure.com",
            "disabled": false,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "initDate": 1575323678601,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "requireUserPat": false,
            "projectMappingIds": [],
            "integrationType": "AZURE",
            "sourcesDiffViewEnabled": true,
            "refSpecNotes": true,
            "refSpecChanges": false,
            "trustFolderStat": false
        },
        {
            "id": 2,
            "displayName": "/jira/repos/*",
            "origin": "/jira/repos/*",
            "root": "/jira/repos/",
            "realRoot": "/jira/repos/",
            "absoluteRoot": true,
            "disabled": true,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "initDate": 1477564914000,
            "lastIndexedDate": 1508771838475,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "requireUserPat": false,
            "projectMappingIds": [],
            "integrationType": "FILESPACE",
            "sourcesDiffViewEnabled": true,
            "refSpecNotes": true,
            "refSpecChanges": false,
            "trustFolderStat": false
        },
        {
            "id": 3,
            "displayName": "https://gitlab.com/*",
            "origin": "https://gitlab.com",
            "disabled": false,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": false,
            "initDate": 1528905066452,
            "lastIndexedDate": 1584930702945,
            "revisionIndexing": true,
            "gitViewerEnabled": false,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "tagsFilter": "",
            "requireUserPat": false,
            "projectMappingIds": [],
            "integrationType": "GITLAB",
            "sourcesDiffViewEnabled": true,
            "refSpecNotes": true,
            "refSpecChanges": false,
            "trustFolderStat": false
        },               
        {
            "id": 4,
            "displayName": "Test GitHub",
            "origin": "https://api.github.com",
            "disabled": false,
            "sendCommitEmails": true,
            "maxMinsToCommitEmail": 1440,
            "global": true,
            "initDate": 1549911276768,
            "lastIndexedDate": 1584930774250,
            "revisionIndexing": true,
            "gitViewerEnabled": true,
            "disableSslVerification": false,
            "smartCommitsEnabled": true,
            "tagsFilter": "",
            "requireUserPat": false,
            "projectMappingIds": [],
            "integrationType": "GITHUB",
            "sourcesDiffViewEnabled": true,
            "refSpecNotes": true,
            "refSpecChanges": false,
            "apiPath": "",
            "apiFilter": "",
            "trustFolderStat": false
        }
    ]
}
```

<br>

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

[Retrieve an Integration](/git-integration-for-jira-data-center/Retrieve-an-Integration-gij-self-managed)

**Retrieve Integration List** (this page)

