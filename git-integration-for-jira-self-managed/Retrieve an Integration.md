---

title: Retrieve an Integration
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Retrieve an Integration

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380699382/Retrieve+an+Integration>

* * *

Retrieves the parameter details of an integration from the git repository configuration.

Only Jira admins can perform the Retrieve an Integration API call.

|     |     |
| --- | --- |
| **Retrieve an Integration** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**integration**`/`**{integrationId}** |     |
| _**method**_ |     |
| GET |     |
| _**parameters**_ |     |
| **Paramater** | **Condition** |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/2`. |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**`/`**2**<br><br>Response example:<br><br>```java<br>{<br>    "success": "true",<br>    "integrations": [                  <br>        {<br>            "id": 2,<br>            "displayName": "Test GitHub",<br>            "origin": "https://api.github.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1549911276768,<br>            "lastIndexedDate": 1584930774250,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "tagsFilter": "",<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "GITHUB",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "apiPath": "",<br>            "apiFilter": "",<br>            "trustFolderStat": false<br>        }<br>    ]<br>}<br>``` |

### Related articles

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