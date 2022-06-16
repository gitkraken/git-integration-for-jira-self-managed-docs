---

title: Retrieve Integration List
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Retrieves the list of integrations and their respective parameter details from the git repository configuration.

Only Jira admins can perform the Retrieve Integration List API call.

### **Retrieve Integration List**

| _**url**_ | `/rest/gitplugin/1.0/`**integration** |
| --- | --- |
| _**method**_ | GET |

| **Example:** |
| --- |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**<br><br>Response example:<br><br>```java<br>{<br>    "success": "true",<br>    "integrations": [        <br>        {<br>            "id": 1,<br>            "displayName": "https://dev.azure.com",<br>            "origin": "https://dev.azure.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1575323678601,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "AZURE",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "trustFolderStat": false<br>        },<br>        {<br>            "id": 2,<br>            "displayName": "/jira/repos/*",<br>            "origin": "/jira/repos/*",<br>            "root": "/jira/repos/",<br>            "realRoot": "/jira/repos/",<br>            "absoluteRoot": true,<br>            "disabled": true,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1477564914000,<br>            "lastIndexedDate": 1508771838475,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "FILESPACE",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "trustFolderStat": false<br>        },<br>        {<br>            "id": 3,<br>            "displayName": "https://gitlab.com/*",<br>            "origin": "https://gitlab.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": false,<br>            "initDate": 1528905066452,<br>            "lastIndexedDate": 1584930702945,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": false,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "tagsFilter": "",<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "GITLAB",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "trustFolderStat": false<br>        },               <br>        {<br>            "id": 4,<br>            "displayName": "Test GitHub",<br>            "origin": "https://api.github.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1549911276768,<br>            "lastIndexedDate": 1584930774250,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "tagsFilter": "",<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "GITHUB",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "apiPath": "",<br>            "apiFilter": "",<br>            "trustFolderStat": false<br>        }<br>    ]<br>}<br>``` |

