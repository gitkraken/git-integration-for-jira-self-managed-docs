---

title: Remove Integration
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Remove Integration

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380797346/Remove+Integration>

* * *

Deletes the existing integration from the Git Integration for Jira app repository configuration.

Only Jira admins can perform the Remove Integration API call.

|     |     |
| --- | --- |
| **Remove Existing Integration** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**integration**`/`**{integrationId}** |     |
| _**method**_ |     |
| DELETE |     |
| _**parameters**_ |     |
| **Paramater** | **Condition** |
| _**integrationId**_ | _Integer_. Required.<br><br>This is the ID of the existing integration. For example, `/integration/3`. |
| _**deleteFiles**_ | _Boolean._ Optional.<br><br>Indicates whether the integration folder is also deleted from the Jira server. If set to _**true**_, the repository folder is deleted from the Jira server. |
| _**response**_ |     |
| Deletes the integration from the Git Integration for Jira app repository configuration. If the `deleteFiles` parameter is set to _**true**_, the folders of all the repositories of the integration are also deleted from the Jira instance. |     |
| _**format**_ |     |
| `http://jira.yourorg.com/rest/gitplugin/1.0/`**integration**/\[**integrationId**\]`?`**deleteFiles=true** |     |

|     |
| --- |
| **Examples:** |
| **Example 1:**  <br>`http://jira.yourorg.com/rest/gitplugin/1.0/integration/`**154**`?deleteFiles=`**true**<br><br>```java<br>Response:<br>{<br>  "success": true<br>}<br>```<br><br>**Example 2:**  <br>`http://jira.yourorg.com/rest/gitplugin/1.0/integration/`**5**`?deleteFiles=`**true**<br><br>```java<br>Response:<br>{<br>  "success": false,<br>  "error": "Repository with id=5 does not exist",<br>  "advice": "Please try again with an existing repository id."<br>}<br>``` |

### Related articles

*   Page:
    
    [Add New Integration](/wiki/spaces/GIJDC/pages/380666461/Add+New+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Add New Integration Type API (examples)](/wiki/spaces/GIJDC/pages/380666468) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Update Existing Integration](/wiki/spaces/GIJDC/pages/380699347/Update+Existing+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Remove Integration](/wiki/spaces/GIJDC/pages/380797346/Remove+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Retrieve an Integration](/wiki/spaces/GIJDC/pages/380699382/Retrieve+an+Integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Retrieve Integration List](/wiki/spaces/GIJDC/pages/380666487/Retrieve+Integration+List) (Git Integration for Jira Data Center)