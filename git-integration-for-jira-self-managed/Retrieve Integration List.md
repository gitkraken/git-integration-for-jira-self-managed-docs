---

title: Retrieve Integration List
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Retrieve Integration List

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380666487/Retrieve+Integration+List>

* * *

Retrieves the list of integrations and their respective parameter details from the git repository configuration.

Only Jira admins can perform the Retrieve Integration List API call.

|     |
| --- |
| **Retrieve Integration List** |
| _**url**_ |
| `/rest/gitplugin/1.0/`**integration** |
| _**method**_ |
| GET |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**<br><br>Response example:<br><br>```java<br>{<br>    "success": "true",<br>    "integrations": [        <br>        {<br>            "id": 1,<br>            "displayName": "https://dev.azure.com",<br>            "origin": "https://dev.azure.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1575323678601,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "AZURE",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "trustFolderStat": false<br>        },<br>        {<br>            "id": 2,<br>            "displayName": "/jira/repos/*",<br>            "origin": "/jira/repos/*",<br>            "root": "/jira/repos/",<br>            "realRoot": "/jira/repos/",<br>            "absoluteRoot": true,<br>            "disabled": true,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1477564914000,<br>            "lastIndexedDate": 1508771838475,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "FILESPACE",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "trustFolderStat": false<br>        },<br>        {<br>            "id": 3,<br>            "displayName": "https://gitlab.com/*",<br>            "origin": "https://gitlab.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": false,<br>            "initDate": 1528905066452,<br>            "lastIndexedDate": 1584930702945,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": false,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "tagsFilter": "",<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "GITLAB",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "trustFolderStat": false<br>        },               <br>        {<br>            "id": 4,<br>            "displayName": "Test GitHub",<br>            "origin": "https://api.github.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1549911276768,<br>            "lastIndexedDate": 1584930774250,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "tagsFilter": "",<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "GITHUB",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "apiPath": "",<br>            "apiFilter": "",<br>            "trustFolderStat": false<br>        }<br>    ]<br>}<br>``` |

## Related articles

*   Page:
    
    [Add New Integration](/wiki/spaces/GIJDC/pages/380666461/Add+New+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Add New Integration Type API (examples)](/wiki/spaces/GIJDC/pages/380666468) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Update Existing Integration](/wiki/spaces/GIJDC/pages/380699347/Update+Existing+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Remove Integration](/wiki/spaces/GIJDC/pages/380797346/Remove+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Retrieve an Integration](/wiki/spaces/GIJDC/pages/380699382/Retrieve+an+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Retrieve Integration List](/wiki/spaces/GIJDC/pages/380666487/Retrieve+Integration+List) (Git Integration for Jira Data Center)