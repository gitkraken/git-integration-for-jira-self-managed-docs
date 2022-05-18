---

title: Tags API
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Tag REST API returns several latest tags for the issue.  Tags are sorted in chronological order from newest to oldest.

To perform the Tag API call, the Jira user must have the permission to **read** the requested issue.

|     |     |
| --- | --- |
| **Tag** |     |
| url |     |
| `/rest/gitplugin/1.0/issuegitdetails/issue/`**{issuekey}**`/tag` |     |
| method |     |
| GET |     |
| _**parameters**_ |     |
| **Parameter** | **Description** |
| _**issueKey**_ | _String_. Required. Path parameter.<br><br>This is the Jira Issue Key – a concatenation of Project key and Issue number. It must contain a dash ('-'). The _**issueKey**_ must be valid and existent.<br><br>For example: `TST-435`. |
| _**tagsPerRepository**_ | _Integer._ Required.<br><br>This parameter limits the total number of tags returned.<br><br>Use values greater than or equal to **1** (RECOMMENDED).<br><br>Using the zero (0) value will return all tags linked to the issue but this greatly impacts Jira performance (NOT RECOMMENDED).<br><br>**Example:**<br><br>`/rest/gitplugin/1.0/issuegitdetails/issue/`**TST-435**`/tag?`**tagsPerRepository=2** |
| _**response**_ |     |
| Returns the number of tags according to the parameter value for each repository associated with the issue. |     |


The result contains tag elements with basic information such as name of a tag, associated commit data, associated repository settings, etc.

The additional flag _**hasMore**_ indicates if an issue contains more tags. Increasing the quantity number for `tagsPerRepository` will return a large collection result depending on the size of the parameter value  –  in case _**hasMore**_ has **true** as response.

|     |
| --- |
| **Example:** |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**issuegitdetails**`/issue/`**TST-435**`/`**tag**`?`**tagsPerRepository**\=**2**<br><br>**Result:**<br><br>```java<br>{<br>  "tags": [<br>    {<br>      "name": "test tag 1",<br>      "commitId": "4caf6aa4fd50ef42012863ce561bddba32557152",<br>      "repoId": 2,<br>      "repoName": "test-repo-01",<br>      "isGitViewerEnabled": true,<br>      "creationDateFormatted": "April 9, 2020 20:27:28 PM OMST",<br>      "committerName": "John Smith",<br>      "committerEmail": "johnsmith@example.com",<br>      "creationDate": 1617978448000<br>    },<br>    {<br>      "name": "test tag 2",<br>      "commitId": "90e902222248ae205ed6ed42cd037df8fbefc871",<br>      "repoId": 3,<br>      "repoName": "test-repo-02",<br>      "isGitViewerEnabled": true,<br>      "creationDateFormatted": "November 12, 2020 10:38:56 AM OMST",<br>      "message": "TEST-1 message",<br>      "committerName": "John Smith",<br>      "committerEmail": "johnsmith@example.com",<br>      "creationDate": 1605155936000<br>    }<br>  ],<br>  "isTagsFeatureEnabled": true,<br>  "hasMore": true,<br>  "calculationError": "",<br>  "firstTag": {<br>    "name": "testrepo-test-tag-01",<br>    "commitId": "a7141bf14e3a27c413b568c8d1f5a5f3a6a45135",<br>    "repoId": 1,<br>    "repoName": "test-repo-main",<br>    "isGitViewerEnabled": true,<br>    "creationDateFormatted": "April 5, 2018 11:52:11 AM OMST",<br>    "message": "TEST-1 tags per repo example",<br>    "committerName": "John Smith",<br>    "committerEmail": "johnsmith@example.com",<br>    "creationDate": 1459835531000<br>  }<br>}<br>``` |

### REST APIs

*   Page:

    [Bulk Change API](/wiki/spaces/GIJDC/pages/380764495/Bulk+Change+API) (Git Integration for Jira Data Center)

*   Page:

    [Repository API](/git-integration-for-jira-self-managed/Repository-API) (Git Integration for Jira Data Center)

*   Page:

    [Reindex API](/git-integration-for-jira-self-managed/Reindex-API) (Git Integration for Jira Data Center)

*   Page:

    [Commits API](/git-integration-for-jira-self-managed/Commits-API) (Git Integration for Jira Data Center)

*   Page:

    [Branches API](/git-integration-for-jira-self-managed/Branches-API) (Git Integration for Jira Data Center)

*   Page:

    [Integration API](/git-integration-for-jira-self-managed/Integration-API) (Git Integration for Jira Data Center)