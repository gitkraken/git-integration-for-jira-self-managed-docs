---

title: Retrieve an Integration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Retrieves the parameter details of an integration from the git repository configuration.

Only Jira admins can perform the Retrieve an Integration API call.


### **Retrieve an Integration** 

| _**url**_ | `/rest/gitplugin/1.0/`**integration**`/`**{integrationId}** |
| --- | --- |
| _**method**_ | GET |
| _**parameters**_ |     |

| **Paramater** | **Condition** |
| --- | --- |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/2`. |

| **Example:** |
| --- |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**`/`**2**<br><br>Response example:<br><br>```java<br>{<br>    "success": "true",<br>    "integrations": [                  <br>        {<br>            "id": 2,<br>            "displayName": "Test GitHub",<br>            "origin": "https://api.github.com",<br>            "disabled": false,<br>            "sendCommitEmails": true,<br>            "maxMinsToCommitEmail": 1440,<br>            "global": true,<br>            "initDate": 1549911276768,<br>            "lastIndexedDate": 1584930774250,<br>            "revisionIndexing": true,<br>            "gitViewerEnabled": true,<br>            "disableSslVerification": false,<br>            "smartCommitsEnabled": true,<br>            "tagsFilter": "",<br>            "requireUserPat": false,<br>            "projectMappingIds": [],<br>            "integrationType": "GITHUB",<br>            "sourcesDiffViewEnabled": true,<br>            "refSpecNotes": true,<br>            "refSpecChanges": false,<br>            "apiPath": "",<br>            "apiFilter": "",<br>            "trustFolderStat": false<br>        }<br>    ]<br>}<br>``` |

