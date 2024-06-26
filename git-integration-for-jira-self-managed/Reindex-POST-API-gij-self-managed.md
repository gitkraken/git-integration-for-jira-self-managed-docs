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
        <ol style='margin-bottom:-20px'>
            <li>Jira <b>administrators</b></li>
            <li>Jira user who has <b>all</b> of the following:
            <ul>
                <li><b>View/browse permissions</b> to the project;</li>
                <li><b>View Development Tools permissions</b> to the same project; and</li>
                <li>The repository is <b>associated</b> to the project.</li>
            </ul></li>
        </ol>
    </div>
    </div>
</div>

&nbsp;
### url
`{JiraBaseURL}/rest/gitplugin/2.0/reindex` <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW IN v4.17</b>

### method
POST

### content-type
application/json

### Parameters

Request body is a JSON structure.

| Field | Description |
| :--- | :--- |
| _**repoId**_ | _Integer_. Optional.<br><br>If _**repoId**_ is left as blank, the API will perform a reindex of all repositories. |
| _**priority**_ |  _Integer_. Optional.<br><br>Set the priority of the operation. Default value is **24**. Any value greater or equal to **1** is allowed.<br><br>The tasks in the queue are executed in descending order of priority. The Git Integration for Jira app internally uses the following priorities for operations:<br>24 -- Manual reindex<br>22 -- Webhook reindex<br>20 -- Scheduled reindex<br>10 -- Remove repository<br>&nbsp;&nbsp;2 -- Git GC<br><br> |

### Response
JSON

### Example with repoId assigned:
Reindex the repository with repoId.

```json
http://jira.yourorg.com/rest/gitplugin/2.0/reindex

Body, JSON(application/json):
{
  "repoId": 133
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
http://jira.yourorg.com/rest/gitplugin/2.0/reindex

Body, JSON(application/json):
{
  "repoId": 133,
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
With blank repoId, the example below will perform a full reindex.

```json
http://jira.yourorg.com/rest/gitplugin/2.0/reindex

-----------------------

Response:
{
  "success": true,
  "finished": false,
  "threadId": "18cc6873-2b75-45b3-ab86-a6b1d09f6c9f"
}
```

### Example with Webhook URL from the GIJ webhooks page:
Reindex a repository which contains the webhook setting.

```json
http://jira.yourorg.com/rest/gitplugin/webhook/1.0/reindex/<secret_key>

-----------------------

Response:
{
  "success": true,
  "finished": false,
  "threadId": "18cc6873-2b75-45b3-ab86-a6b1d09f6c9f"
}
```

&nbsp;
* * *

## Reindex REST APIs

**Reindex POST API** (this page)

[Reindex GET API](/git-integration-for-jira-data-center/reindex-get-api-gij-self-managed)

