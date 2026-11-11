---

title: Reindex GET API
description: "Track the messages and status of a reindex thread, for one repository or all, with the Reindex GET REST API."
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
tags: [rest api, reindex api, reindex status, thread id, indexing]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Reindex GET API"
    nav_order: 20
    nav_parent: "reindex-api-gij-self-managed"
    page_type: "content"
---

Use this method to track messages for a particular thread.

> **Warning:**
> <ol style='margin-bottom:-20px;'>
> <li>Jira <b>administrators</b></li>
> <li>Jira user who has <b>all</b> of the following:
> <ol type='a'>
> <li><b>View/browse permissions</b> to the project;</li>
> <li><b>View Development Tools permissions</b> to the same project; and</li>
> <li>The repository is <b>associated</b> to the project.</li>
> </ol>
> </li>
> </ol>

&nbsp;

### url
`{JiraBaseURL}/rest/gitplugin/1.0/index.json`

### method
GET

### parameters

| Field | Description |
| :--- | :--- |
| _**threadID**_ | _Required_.<br><br>Indexer thread ID (UUID). Query parameter.<br><br>**Example:**<br>`eafe58fc-d8de-42ff-8815-6fe5860b38d2` |
| _**repoId**_ | _Integer_. Optional.<br><br>When the `repoId` field is empty, the API will fetch the reindex status for all repositories. Providing an integer value will retrieve the reindex status for a particular repository. |

### response
JSON

<br>

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/index.json?threadId=eafe58fc-d8de-42ff-8815-6fe5860b38d2&repoId=113`

```json
Response:
{
    "success":true,
    "finished":true,
    "threadId":172,
    "messages": {
        "Indexing test-repo":100.0
    },
    "errors": {},
    "lastOperationPercent":100.0
}
```

&nbsp;

### Reindex REST APIs

[Reindex POST API](/git-integration-for-jira-data-center/reindex-post-api-gij-self-managed) (Git Integration for Jira Data Center)

**Reindex GET API** (this page)

