---

title: Remove Integration API
description: "Delete an integration from the app configuration, and optionally its files, with a DELETE call to the Integration REST API."
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
tags: [rest api, integration api, remove integration, delete request]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Remove Integration – API"
    nav_order: 50
    nav_parent: "integration-api-gij-self-managed"
    page_type: "content"
    card_icon: "api"
    card_color: "blue"
    card_description: "Delete an integration from the app configuration, and optionally its files, with a DELETE call to the Integration REST API"
---

Deletes the existing integration from the Git Integration for Jira app repository configuration.

> **Warning:** Only Jira admins can perform the Remove Integration API call.

&nbsp;

### url
`{JiraBaseURL}/rest/gitplugin/1.0/integration/{integrationId}`

### method
DELETE


### Parameters

| Field | Description |
| :--- | :--- |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/3`. |
| _**deleteFiles**_ | _Boolean._ Optional.<br><br>Default value is `false`. Indicates whether the integration folder is also deleted from the Jira server. If set to _**true**_, the repository folder is deleted from the Jira server. If set to `false`, the unused cloned repositories of an integration will remain in `jira/home/data/git-plugin` folder. |
| _**response**_ | Deletes the integration from the Git Integration for Jira app repository configuration. If the `deleteFiles` parameter is set to _**true**_, the folders of all the repositories of the integration are also deleted from the Jira instance. |
| _**format**_ | `http://jira.yourorg.com/rest/gitplugin/1.0/integration/\[integrationId\]?deleteFiles=true` |

&nbsp;

### Examples

**Example 1:**

`http://jira.yourorg.com/rest/gitplugin/1.0/integration/154?deleteFiles=true`

```java
Response:
{
  "success": true
}
```

**Example 2:**

`http://jira.yourorg.com/rest/gitplugin/1.0/integration/5?deleteFiles=true`

```java
Response:
{
  "success": false,
  "error": "Repository with id=5 does not exist",
  "advice": "Please try again with an existing repository id."
}
```

&nbsp;

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

**Remove Integration** (this page)

[Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

