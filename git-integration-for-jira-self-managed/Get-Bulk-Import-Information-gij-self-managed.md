---

title: Get Bulk Import Information
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Obtains information about the importing thread. Use the following path format to access bulk import information.

Any Jira user can perform the Getting Bulk Import Information API call.

## Getting Bulk Import Information**

_**url**_<br>
`/rest/gitplugin/1.0/configuration/progress.json`

_**method**_<br>
GET

### Parameters

`thread_id`<br>
_Integer._ Required.<br>
Input a thread ID to access information about the specific thread process.

### Response

JSON

Returns the status information of the import process.

### Download sample file

[**configuration\_progress.py**](https://bigbrassband.com/files/configuration_progress.zip)

* * *

### Example:

`http://jira.example.org/rest/gitplugin/1.0/`**configuration**`/progress.json?`**thread\_id**`=`**123**

```json
Response example:
{
  "success":false,
  "finished":true,
  "progressEntries":[{
    "prcntDouble":0.0,
    "prcntInteger":0,
    "error":false,
    "message":"Creating repository git@github.com:user/test-repo.git"
   },{
    "error":true,
    "message": "java.lang.NullPointerException"
   },{
    "prcntDouble":100.0,
    "prcntInteger":1042,
    "error":false,
    "message":"Resolving deltas"
   }
  ]
} 

Usage:
user@home:~$ python configuration_progress.py 1058
{"success":false,"finished":true,"progressEntries":[{
...
```

