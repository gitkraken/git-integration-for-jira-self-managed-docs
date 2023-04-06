---

title: Retrieve an Integration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Retrieves the parameter details of an integration from the git repository configuration.

Only Jira admins can perform the Retrieve an Integration API call.


### Retrieve an Integration

### url
`/rest/gitplugin/1.0/integration/{integrationId}`

### method
GET

### parameters

| Paramater | Condition |
| :--- | :--- |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/2`. |

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/integration/2`

**Response example:**

```json
{
    "success": "true",
    "integrations": [                  
        {
            "id": 2,
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

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

**Retrieve an Integration** (this page)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

