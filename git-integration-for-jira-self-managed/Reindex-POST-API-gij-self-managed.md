---

title: Reindex POST API
description:
taxonomy:
    category: git-integration-for-jira-self-managed

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

_**url**_ -- `/rest/gitplugin/1.0/index.json`

_**method**_ -- POST

<br>

### Parameters

| **Parameter** | **Condition** |
| :--- | :--- |
| _**repoId**_ | _Array of Long_. Repository ID.  Form parameter.<br><br>**Example:**<br>Form param (`repoId: [133]`) |
| _**response**_ | JSON |

<br>

**Example:**

```java
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

