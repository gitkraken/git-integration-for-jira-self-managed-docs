---

title: Enable/Disable Existing Repository API
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
        Only Jira admins can perform the Enable/Disable Existing Repository API call.
    </div>
    </div>
</div>

### URL format
`\{JIRA\_BASE\_URL\}/rest/gitplugin/1.0/repository/\{repoId\}/disable?disable=true|false`

### method
**PUT**

Utilize the following parameters to control the field values in the URL format:

### parameters

| Field | Description |
| :---- | :---- |
| _**JIRA\_BASE\_URL**_ | _String_. Required.<br><br>This is your organization’s Jira base URL. For example, `https://acmecorp.jira.com`. |
| _**repoId**_ | _Integer_. Required.<br><br> This is the repository ID that your are targeting to enable/disable. |
| _**disable**_ | _Boolean_. Required.<br><br>When set to **disable=true**, the status of the target repository in the Manage git repository/integration configuration list becomes <b style='background-color:#6E5DC6; padding:1px 5px; color:#FFFFFF; border-radius:3px; margin: 0 5px; font-size: small;'>DISABLED</b>. Set to **disable=false**, to enable it again. |

&nbsp;

### example

`https://acmecorp.jira.com/rest/gitplugin/1.0/repository/2/disable?disable=true`

**RESULT:**
```json
{
  "success": true
}
```

![](/wp-content/uploads/gij-datacenter-repo-api-disable-true.png)

&nbsp;

### Repository REST APIs

[Retrieve Repository List](/git-integration-for-jira-data-center/retrieve-repository-list-gij-self-managed)

[Add New Repository](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed)

**Enable/disable Existing Repository** (this page)

[Update Existing Repository](/git-integration-for-jira-data-center/update-existing-repository-gij-self-managed)

[Delete Existing Repository](/git-integration-for-jira-data-center/delete-existing-repository-gij-self-managed)

