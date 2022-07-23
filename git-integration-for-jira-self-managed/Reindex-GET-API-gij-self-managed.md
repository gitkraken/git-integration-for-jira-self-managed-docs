---

title: Reindex GET API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Use this method to track messages for a particular thread.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <ol>
            <li>Jira <b>administrators</b></li>
            <li>Jira user who has <b>all</b> of the following:
                <ol type='a'>
                    <li><b>View/browse permissions</b> to the project;</li>
                    <li><b>View Development Tools permissions</b> to the same project; and</li>
                    <li>The repository is <b>associated</b> to the project.</li>
                </ol>
            </li>
        </ol>
    </div>
    </div>
</div>
<br>

## Reindex GET API

_**url**_<br>
`/rest/gitplugin/1.0/index.json`

_**method**_<br>
GET

### Parameters

| Parameter | Condition |
| :--- | :--- |
| _**threadID**_ | _Required_.<br><br>Indexer thread ID (UUID).  Query parameter.<br><br>**Example:**<br>`eafe58fc-d8de-42ff-8815-6fe5860b38d2` |

### Response

JSON

<br>

### Example:

`http://jira.yourorg.com/rest/gitplugin/1.0/index.json?`**threadId**`=`**eafe58fc-d8de-42ff-8815-6fe5860b38d2**

```json
Response:
{
    "success":true,
    "finished":true,
    "threadId":172,
    "messages": {
        "Indexing test-repo":100.0
    },
    "errors": {},
    "lastOperationPercent":100.0
}
```

