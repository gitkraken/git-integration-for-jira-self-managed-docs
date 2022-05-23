---

title: Retrieve Repository List
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Retrieves list of repositories mapped to a given project.

Any Jira user can perform the Retrieve Repository List API call.

|     |     |
| --- | --- |
| **Retrieve Repository List** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**repository** |     |
| _**method**_ |     |
| GET |     |
| _**parameters**_ |     |
| `projectKey` | Jira Project key (string). _**Optional**_.  Query parameter.  If omitted, all imported repositories will be returned.<br><br>Example: Form param (`projectKey`: **TST**) |
| _**response**_ |     |
| JSON |     |

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`?`**projectKey**`=`**TST**<br><br>```java<br>Response Example:<br>{<br>  "success": true,<br>  "repositories": [<br>    {<br>      "id": 2,<br>      "displayName": "testrepo",<br>      "origin": "https://github.com/xxx",<br>      "mainBranch": "master",<br>      "root": "xxx/xxx",<br>      "realRoot": "2_testrepo",<br>      "absoluteRoot": false,<br>      "disabled": false,<br>      "enableFetches": true,<br>      "sendCommitEmails": true,<br>      "maxMinsToCommitEmail": 1440,<br>      "global": true,<br>      "hosted": false,<br>      "initDate": 1606383040986,<br>      "lastIndexedDate": 1613815871685,<br>      "revisionIndexing": true,<br>      "gitViewerEnabled": true,<br>      "disableSslVerification": false,<br>      "smartCommitsEnabled": true,<br>      "viewFormat": "",<br>      "commitsValidationRequired": true,<br>      "requireUserPat": false,<br>      "projectMappingIds": [],<br>      "trackedFolderId": 11,<br>      "integrationType": "GITHUB",<br>      "showAllTags": true,<br>      "supportsBranchCreationApi": true,<br>      "supportsPullRequestApi": "PULL_REQUESTS_GROUP",<br>      "sourcesDiffViewEnabled": true,<br>      "refSpecNotes": true,<br>      "refSpecChanges": false,<br>      "trustFolderStat": true<br>    },<br>    {<br>      "id": 1,<br>      "displayName": "gitrepo",<br>      "origin": "https://xxx@xxx.gitlab.org/xxx",<br>      "mainBranch": "master",<br>      "root": "/xxx/xxx/xxx",<br>      "realRoot": "1_gitrepo",<br>      "absoluteRoot": false,<br>      "disabled": false,<br>      "enableFetches": true,<br>      "sendCommitEmails": true,<br>      "maxMinsToCommitEmail": 1440,<br>      "global": true,<br>      "hosted": false,<br>      "initDate": 1606383040986,<br>      "lastIndexedDate": 1613815870861,<br>      "revisionIndexing": true,<br>      "gitViewerEnabled": true,<br>      "disableSslVerification": false,<br>      "smartCommitsEnabled": true,<br>      "commitsValidationRequired": true,<br>      "requireUserPat": false,<br>      "projectMappingIds": [],<br>      "trackedFolderId": 11,<br>      "integrationType": "GITLAB",<br>      "showAllTags": true,<br>      "supportsBranchCreationApi": true,<br>      "supportsPullRequestApi": "MERGE_REQUESTS_GROUP",<br>      "sourcesDiffViewEnabled": true,<br>      "refSpecNotes": true,<br>      "refSpecChanges": false,<br>      "trustFolderStat": true<br>    }<br>  ]<br>}<br>``` |

