---

title: Reindex POST API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Starts the reindex process in a separate thread and returns the result immediately.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        There are two types of users who can perform the Reindex POST API call:
        <ol>
            <li>Jira <b>administrators</b></li>
            <li>Jira user who has <b>all</b> of the following:
            <ul>
                <li><b>View/browse permissions</b> to the project;</li>
                <li><b>View Development Tools permissions</b> to the same project; and</li>
                <li>The repository is <b>associated</b> to the project.</li>
            </ul></li>
        </ol>
    </div>
    </div>
</div>
<br>

## Reindex POST API

### url
`/rest/gitplugin/2.0/reindex`

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The old URL format (<code>/rest/gitplugin/1.0/index.json</code>) is deprecated.
    </div>
    </div>
</div>
<br>

### method
POST

### content-type
application/json

### Parameters

| Parameter | Condition |
| :--- | :--- |
| _**repoId**_ | _Integer_. Repository ID. JSON parameter.<br><br>**Example:**<br>`/rest/gitplugin/2.0/reindex?repoId=133`<br><br>If _**repoId**_ is left as blank, the API will perform a reindex of all repositories. |
| _**priority**_ | Set the priority of the operation. The tasks in the queue are processed in descending order of priority. Use the following priorities for indexing operations:<br>24 -- Manual reindex<br>22 -- Webhook reindex<br>20 -- Scheduled reindex<br>10 -- Remove repository<br>&nbsp;&nbsp;2 -- Git GC<br><br><b>Example:</b><br>`/rest/gitplugin/2.0/reindex?repoId=133&prioirity=20` |

### Response
JSON

<br>

### Example with repoId assigned:

```json
http://jira.yourorg.com/rest/gitplugin/2.0/reindex?repoID=133

Body, JSON(application/json):
{
  "repoId": [133]
}
 
-----------------------
 
Response:
{
  "success": true,
  "finished": false,
  "threadId": "c3989477-053b-4cb7-965c-1ab54690490f"
}
```

### Example with priority assigned:

```json
http://jira.yourorg.com/rest/gitplugin/2.0/reindex?repoID=133&priority=20

Body, JSON(application/json):
{
  "repoId": [133],
  "priority": 20
}
 
-----------------------
 
Response:
{
  "success": true,
  "finished": false,
  "threadId": "c3989477-053b-4cb7-965c-1ab54690490f"
}
```

### Example with blank repoId:

```json
http://jira.yourorg.com/rest/gitplugin/2.0/reindex

-----------------------

Response:
{}
```

&nbsp;
<hr>
&nbsp;

## Reindex REST APIs

**Reindex POST API** (this page)

[Reindex GET API](/git-integration-for-jira-data-center/reindex-get-api-gij-self-managed)

