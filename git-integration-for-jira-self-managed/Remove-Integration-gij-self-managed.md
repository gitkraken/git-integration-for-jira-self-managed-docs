---

title: Remove Integration API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Deletes the existing integration from the Git Integration for Jira app repository configuration.

Only Jira admins can perform the Remove Integration API call.

## Remove Existing Integration

### url
`/rest/gitplugin/1.0/`**integration**`/`**{integrationId}**

### method
DELETE


### Parameters

| Paramater | Condition |
| :--- | :--- |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/3`. |
| _**deleteFiles**_ | _Boolean._ Optional.<br><br>Indicates whether the integration folder is also deleted from the Jira server. If set to _**true**_, the repository folder is deleted from the Jira server. |
| _**response**_ | Deletes the integration from the Git Integration for Jira app repository configuration. If the `deleteFiles` parameter is set to _**true**_, the folders of all the repositories of the integration are also deleted from the Jira instance. |
| _**format**_ | `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**/\[**integrationId**\]`?`**deleteFiles=true** |

<br>

### Examples:

**Example 1:**

`http://jira.yourorg.com/rest/gitplugin/1.0/integration/`**`154`**?deleteFiles=**`true`**

```java
Response:
{
  "success": true
}
```

**Example 2:**

`http://jira.yourorg.com/rest/gitplugin/1.0/integration/`**`5`**?deleteFiles=**`true`**

```java
Response:
{
  "success": false,
  "error": "Repository with id=5 does not exist",
  "advice": "Please try again with an existing repository id."
}
```

<br>

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

**Remove Integration** (this page)

[Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

