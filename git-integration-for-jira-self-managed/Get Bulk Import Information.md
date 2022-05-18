---

title: Get Bulk Import Information
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Obtains information about the importing thread.  Use the following path format to access bulk import information.

Any Jira user can perform the Getting Bulk Import Information API call.

|     |     |
| --- | --- |
| **Getting Bulk Import Information** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/configuration/progress.json` |     |
| _**method**_ |     |
| GET |     |
| _**parameters**_ |     |
| `thread_id` | _Integer._ Required.<br><br>Input a thread ID to access information about the specific thread process. |
| _**response**_ |     |
| JSON<br><br>Returns the status information of the import process. |     |
| **Download sample file** |     |
| ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) [**configuration\_progress.py**](https://bigbrassband.com/files/configuration_progress.zip) |     |

|     |
| --- |
| **Example:** |
| `http://jira.example.org/rest/gitplugin/1.0/`**configuration**`/progress.json?`**thread\_id**`=`**123**<br><br>```java<br>Response example:<br>{<br>  "success":false,<br>  "finished":true,<br>  "progressEntries":[{<br>    "prcntDouble":0.0,<br>    "prcntInteger":0,<br>    "error":false,<br>    "message":"Creating repository git@github.com:user/test-repo.git"<br>   },{<br>    "error":true,<br>    "message": "java.lang.NullPointerException"<br>   },{<br>    "prcntDouble":100.0,<br>    "prcntInteger":1042,<br>    "error":false,<br>    "message":"Resolving deltas"<br>   }<br>  ]<br>}<br> <br> <br>Usage:<br>user@home:~$ python configuration_progress.py 1058<br>{"success":false,"finished":true,"progressEntries":[{<br>...<br>``` |

### Related articles

*   Page:

    [Bulk Export](/git-integration-for-jira-self-managed/Bulk-Export) (Git Integration for Jira Data Center)

*   Page:

    [Bulk Import](/git-integration-for-jira-self-managed/Bulk-Import) (Git Integration for Jira Data Center)

*   Page:

    [Get Bulk Import Information](/wiki/spaces/GIJDC/pages/421298278/Get+Bulk+Import+Information) (Git Integration for Jira Data Center)