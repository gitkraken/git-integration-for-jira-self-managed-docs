---

title: Get Bulk Import Information
description: Check the progress and status messages of a bulk import thread with the Get Bulk Import Information REST API.
product: Git Integration for Jira Data Center
feature: REST API
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2024-06
llms_include: true
tags: [rest api, bulk import, import progress, thread id, bulk change]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Get Bulk Import Information"
    nav_order: 30
    nav_parent: "bulk-change-api-gij-self-managed"
    page_type: "content"
    card_icon: "api"
    card_color: "blue"
    card_description: "Check the progress and status messages of a bulk import thread with the Get Bulk Import Information REST API"
---

Obtains information about the importing thread. Use the following path format to access bulk import information.

Any Jira user can perform the Getting Bulk Import Information API call.

_**url**_<br>
`{JiraBaseURL}/rest/gitplugin/1.0/configuration/progress.json`

_**method**_<br>
GET

### Parameters

`thread_id`<br>
_Integer._ Required.<br>
Input a thread ID to access information about the specific thread process.

### Response

JSON

Returns the status information of the import process.

### Download sample file

Right click the link and download the file below:
[**configuration\_progress.py**](/wp-content/uploads/configuration_progress.zip)

* * *

### Example:

`http://jira.example.org/rest/gitplugin/1.0/configuration/progress.json?thread\_id=123`

```json
Response example:
{
  "success":false,
  "finished":true,
  "progressEntries":[{
    "prcntDouble":0.0,
    "prcntInteger":0,
    "error":false,
    "message":"Creating repository git@github.com:user/test-repo.git"
   },{
    "error":true,
    "message": "java.lang.NullPointerException"
   },{
    "prcntDouble":100.0,
    "prcntInteger":1042,
    "error":false,
    "message":"Resolving deltas"
   }
  ]
} 

Usage:
user@home:~$ python configuration_progress.py 1058
{"success":false,"finished":true,"progressEntries":[{
...
```

<p>&nbsp;</p>


### Bulk Change REST APIs

*   [Bulk Export](/git-integration-for-jira-data-center/bulk-export-gij-self-managed) (Git Integration for Jira Data Center)

*   [Bulk Ixport](/git-integration-for-jira-data-center/bulk-import-gij-self-managed) (Git Integration for Jira Data Center)

*   **Get Bulk Import Information** (this page)

