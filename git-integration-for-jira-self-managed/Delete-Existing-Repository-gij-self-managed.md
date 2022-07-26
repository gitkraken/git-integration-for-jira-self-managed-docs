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
<br>

## Delete Existing Repository properties**

_**url**_<br>
`/rest/gitplugin/1.0/`**repository**

_**method**_<br>
DELETE

### Parameters

| Parameter | Condition |
| :--- | :--- |
| _**id**_ | _Integer_. Required.<br><br>This is the ID of the existing repository. For example, `id : 3,`. |
| _**deleteFiles**_ | _Boolean._ Optional.<br><br>Indicates whether the repository folder is also deleted from the Jira server. If set to _**true**_, the repository folder is deleted from the Jira server. |

### Response

Deletes the repository from the Git Integration for Jira app repository configuration. If the `deleteFiles` parameter is set to _**true**_, the repository folder is also deleted from the Jira instance.

### Examples

**Example 1:**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`?`**id=3**`&`**deleteFiles=true**

```json
Response:
{
  "success": true
}
```

**Example 2:**<br>
`http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`?`**id=5**

```json
Response:
{
  "success": false,
  "error": "Repository with id=5 does not exist",
  "advice": "Please try again with an existing repository id."
}
```

## Related articles

*   [Retrieve Repository List](/git-integration-for-jira-data-center/retrieve-repository-List-gij-self-managed/)

*   [Add New Repository](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed/)

*   [Update Existing Repository](/git-integration-for-jira-data-center/Update-Existing-Repository-gij-self-managed/)

*   [Delete Existing Repository](/git-integration-for-jira-data-center/Delete-Existing-Repository-gij-self-managed/)

