---

title: Update Commit Issue Changes API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Updates the list of issues associated with the commit to the specified repository.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        There are two types of users who can perform the Get Commit Issue Changes API call:
        <ol style='margin-bottom:-20px'>
            <li>Jira <b>administrators</b></li>
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

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This REST API has a <a href='#changestrs-extension'>changeStrs</a> extension.
    </div>
    </div>
</div>

&nbsp;

### url
`{JiraBaseURL}/rest/gitplugin/1.0/repository/\{repoId\}/commits/\{commitHash\}/issues`

### method
POST

### parameters

| Field | Description |
| :--- | :--- |
| _**jira-host**_ | _String_. Required.<br><br>This is the default url location where you host your Jira.<br><br>**For example:**<br>`http://local-host-jira.com:2990`<br>`https://jira.your-organization.com` |
| _**repoId**_ | _Integer_. Required.<br><br>Substitute `{repoId}` with the actual repository ID.<br><br>Use the [Repository REST API](/git-integration-for-jira-data-center/repository-api-gij-self-managed) to obtain the connected repositories' IDs.<br><br>**Example:**<br>`http://local-host-jira.com:2990/rest/gitplugin/1.0/repository/1/commit/e012663bf9bd968388faa510cb5b310e4798c512/issues`<br><br>In the case of the above example, the commit association(s) of the specified commit hash and repository will be updated using the parameters specified in the JSON request body. See [changeStrs](#changeStrs) parameter. |
| _**commitHash**_ | _String_. Required.<br><br>This is the hash of the commit that you want the results from.<br><br>**Example:**  `e012663bf9bd968388faa510cb5b310e4798c512` |

&nbsp;

### changeStrs extension

The request body is a JSON structure supporting the following parameters:

| Parameter | Description |
| :--- | :--- |
| _**a**_ | Adds a new issue key to associate to the commit. |
| _**d**_ | Disassociate the specified issue key from the commit. |

**Example request:**<br>
```json
{
    "changeStrs": ["d:TEST-5", "a:TEST-6", "a:TEST-7"]
}
```

### response
Returns the result for the example below.

**Example for POST queries:**<br>
```json
POST /jira/rest/gitplugin/1.0/repository/1/commits/e012663bf9bd968388faa510cb5b310e4798c512/issues HTTP/1.1
Host: localhost:2990
Content-Type: application/json
 
{
  "changeStrs": ["d:TEST-5", "a:TEST-6", "a:TEST-7"]
}
```

The _**changeStrs**_ modifier with the specified parameters will give the following result:

```ruby
Removes association of TEST-5; and
associates TEST-6 and TEST-7 to the same commit in repo1 and repo2.
```

&nbsp;

### Commits REST APIs

[Get Commits](/git-integration-for-jira-data-center/get-Commits-gij-self-managed)

[Get Commit Issue Changes](/git-integration-for-jira-data-center/get-commit-issue-changes-gij-self-managed)

**Update Commit Issue Changes** (this page)

