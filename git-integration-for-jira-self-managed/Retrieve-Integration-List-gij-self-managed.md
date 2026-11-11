---

title: Retrieve Integration List API
description: Get the list of connected integrations and their parameters with the Retrieve Integration List REST API.
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
tags: [rest api, integration api, list integrations, get request]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Retrieve Integration List API"
    nav_order: 70
    nav_parent: "integration-api-gij-self-managed"
    page_type: "content"
---

Retrieves the list of integrations and their respective parameter details from the git repository configuration.

> **Warning:** Only Jira admins can perform the Retrieve Integration List API call.

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

