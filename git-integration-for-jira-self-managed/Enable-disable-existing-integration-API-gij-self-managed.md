---

title: Enable/Disable Existing Integration API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Enable/Disable Existing Integration API call.
    </div>
</div>

### URL format
`\{JIRA_BASE_URL\}/rest/gitplugin/1.0/repository/\{integrationId\}/disable?disable=true|false`

### method
**PUT**

&nbsp;

Utilize the following parameters to control the field values in the URL format:

### parameters

| Field | Description |
| :---- | :---- |
| _**JIRA_BASE_URL**_ | _String_. Required.<br><br>This is your organization’s Jira base URL. For example, `https://acmecorp.jira.com`. |
| _**integrationId**_ | _Integer_. Required.<br><br> This is the integration ID that your are targeting to enable/disable. |
| _**disable**_ | _Boolean_. Required.<br><br>When set to **disable=true**, the status of the target integration in the Manage git integration configuration list becomes <b style='background-color:#6E5DC6; padding:1px 5px; color:#FFFFFF; border-radius:3px; margin: 0 5px; font-size: small;'>DISABLED</b>. Set to **disable=false**, to enable it again. |

&nbsp;

### example

`https://acmecorp.jira.com/rest/gitplugin/1.0/repository/1/disable?disable=true`

**RESULT:**
```json
{
  "success": true
}
```

![](/wp-content/uploads/gij-datacenter-integration-api-disable-true.png)

&nbsp;

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

[Add New Integration Type API (examples)](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)

**Enable/disable Existing Integration** (this page)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

[Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

