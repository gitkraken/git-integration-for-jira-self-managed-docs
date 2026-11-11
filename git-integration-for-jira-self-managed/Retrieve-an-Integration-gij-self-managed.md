---

title: Retrieve an Integration API
description: Get the parameter details of a single integration by its ID with the Retrieve an Integration REST API.
product: Git Integration for Jira Data Center
feature: REST API
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2024-06
llms_include: true
tags: [rest api, integration api, get integration, integration id]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Retrieve an Integration API"
    nav_order: 60
    nav_parent: "integration-api-gij-self-managed"
    page_type: "content"
    card_icon: "api"
    card_color: "blue"
    card_description: "Get the parameter details of a single integration by its ID with the Retrieve an Integration REST API"
---

Retrieves the parameter details of an integration from the git repository configuration.

> **Warning:** Only Jira admins can perform the Retrieve an Integration API call.

&nbsp;

### url
`{JiraBaseURL}/rest/gitplugin/1.0/integration/{integrationId}`

### method
GET

### parameters

| Field | Description |
| :--- | :--- |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/2`. |

### Example

`http://jira.yourorg.com/rest/gitplugin/1.0/integration/2`

**Response example:**

```json
{
    "success": "true",
    "integration": [                  
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

&nbsp;

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

**Retrieve an Integration** (this page)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

