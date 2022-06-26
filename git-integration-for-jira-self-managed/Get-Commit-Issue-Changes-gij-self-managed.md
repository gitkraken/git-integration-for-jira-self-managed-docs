---

title: Get Commit Issue Changes
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- commits REST API -->

Returns the list of issues associated with the commit from the specified repository.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        There are two types of users who can perform the Get Commit Issue Changes API call:
        <ol>
        <li>Jira <b>administrators</b></li>
        <li>Jira user who has <b>all</b> of the following:
            <ul>
            <li><b>View/browse permissions</b> to the project;</li>
            <li><b>View Development Tools permissions</b> to the same project; and</li>
            <li>The repository is <b>associated</b> to the project.</li>
            </ul>
        </li>
        </ol>
    </div>
    </div>
</div>
<br>

## Get Commit Issue Changes

### URL

`http://`**<jira-host>**`/rest/gitplugin/1.0/`**repository**`/`**{repoId}**`/commits/`**{commitHash}**`/issues`

### Method

GET

### Parameters

| **Parameter** | **Condition** |
| :--- | :--- |
| _**jira-host**_ | _String_. Required.<br><br>This is the default url location where you host your Jira.<br><br>For example:<br>`http://local-host-jira.com:2990`<br>`https://jira.your-organization.com` |
| _**repoId**_ | _Integer_. Required.<br><br>Substitute `{repoId}` with the actual repository ID.<br><br>Use the Repository REST API to obtain the connected repositories' IDs. |
| _**commitHash**_ | _String_. Required.<br><br>This is the hash of the commit that you want the results from.<br><br>**Example:**  `e012663bf9bd968388faa510cb5b310e4798c512` |

### Response

Returns the result for the example below.

### Example

`http://`**local-host-jira.com:2990**`/rest/gitplugin/1.0/`**repository**`/`**1**`/commit/`**e012663bf9bd968388faa510cb5b310e4798c512**`/issues`

**Result:**
```json
{
 "success": true,
 "issueKeys":[
     "TST-999",
     "NEXT-3",
     "TST-6",
     "TST-2",
     "TST-1"
 ]
}
```

The resulting _**issueKeys**_ are the existing Jira issues that are currently associated with the commit that has the specified commit hash.

**Example for GET queries:**

```powershell
GET /jira/rest/gitplugin/1.0/repository/1/commits/e012663bf9bd968388faa510cb5b310e4798c512/issues HTTP/1.1

Host: local-host-jira.com:2990
Content-Type: application/json
```

