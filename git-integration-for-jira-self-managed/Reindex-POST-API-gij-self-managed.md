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
`/rest/gitplugin/1.0/index.json`

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The old URL format (<code>/rest/gitplugin/1.0/index.json</code>) will be deprecated in GIJ v4.17+.
    </div>
    </div>
</div>
<br>

### method
POST

### content-type
application/json

### Parameters

Request body is a JSON structure.

| Parameter | Description |
| :--- | :--- |
| _**repoId**_ | Array of Long. Form parameter.<br><br>This is the repository ID, separated by commas.<br><br>**Examples:**<br>Form param (`"repoId": [133]`)<br>Form param (`"repoId": [133,142,...,154]`) |

&nbsp;

### Response
JSON

<br>

### Example with repoId assigned:

```json
http://jira.yourorg.com/rest/gitplugin/1.0/index.json
 
Body, JSON(application/json):
{
  "repoId": [133]
}
 
-----------------------
 
Response:
{
  "success":true,
  "finished":true,
  "threadId": xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
}
```
&nbsp;
<hr>
&nbsp;

## Reindex REST APIs

**Reindex POST API** (this page)

[Reindex GET API](/git-integration-for-jira-data-center/reindex-get-api-gij-self-managed)

