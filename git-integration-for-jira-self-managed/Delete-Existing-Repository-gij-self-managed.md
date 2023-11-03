---

title: Delete Existing Repository API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- REST API -->

Deletes the existing repository from the Git Integration for Jira app repository configuration.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Delete Repository API call.
    </div>
    </div>
</div>

&nbsp;

### url
`/rest/gitplugin/1.0/repository`

### method
DELETE

### Parameters

| Field | Description |
| :--- | :--- |
| _**id**_ | _Integer_. Required.<br><br>This is the ID of the existing repository. For example, `id : 3,`. |
| _**deleteFiles**_ | _Boolean._ Optional.<br><br>Default value is `false`. Indicates whether the repository folder is also deleted from the Jira server. If set to _**true**_, the repository folder is deleted from the Jira server. If set to `false`, the unused clone of a repository will remain in `jira/home/data/git-plugin` folder.<br><br><div class="bbb-callout bbb--alert" style='margin-bottom:0px;'><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox"><b>Important!</b><br>DO NOT use <code>deleteFiles=true</code> to repository files where origin points to an original repository path. For example:<br><ul><li>...when a plain repository is pointing to an absolute path</li><li>...when a tracked folder is connected to a GitLab hashed storage</li></ul><p style='margin-bottom:-5px;'>If set to <code>true</code>, it will erase (a) repositories from the absolute path and (b) repositories from your Gitlab.</p></div></div></div> |

### Response

Deletes the repository from the Git Integration for Jira app repository configuration. If the `deleteFiles` parameter is set to _**true**_, the repository folder is also deleted from the Jira instance.

### Examples

**Example 1:**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/repository?id=3&deleteFiles=true`

```json
Response:
{
  "success": true
}
```

**Example 2:**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/repository?id=5`

```json
Response:
{
  "success": false,
  "error": "Repository with id=5 does not exist",
  "advice": "Please try again with an existing repository id."
}
```

<p>&nbsp;</p>

### Repository REST APIs

[Retrieve Repository List](/git-integration-for-jira-data-center/retrieve-repository-List-gij-self-managed/)

[Add New Repository](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed/)

[Update Existing Repository](/git-integration-for-jira-data-center/Update-Existing-Repository-gij-self-managed/)

**Delete Existing Repository** (this page)

