---

title: Delete Existing Repository
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Delete Existing Repository

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380797296/Delete+Existing+Repository>

* * *

Deletes the existing repository from the Git Integration for Jira app repository configuration.

Only Jira admins can perform the Delete Repository API call.

|     |     |
| --- | --- |
| **Delete Existing Repository** |     |
| _**url**_ |     |
| `/rest/gitplugin/1.0/`**repository** |     |
| _**method**_ |     |
| DELETE |     |
| _**parameters**_ |     |
| **Paramater** | **Condition** |
| _**id**_ | _Integer_. Required.<br><br>This is the ID of the existing repository. For example, `id : 3,`. |
| _**deleteFiles**_ | _Boolean._ Optional.<br><br>Indicates whether the repository folder is also deleted from the Jira server. If set to _**true**_, the repository folder is deleted from the Jira server. |
| _**response**_ |     |
| Deletes the repository from the Git Integration for Jira app repository configuration. If the `deleteFiles` parameter is set to _**true**_, the repository folder is also deleted from the Jira instance. |     |

|     |
| --- |
| **Examples:** |
| **Example 1:**  <br>`http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`?`**id=3**`&`**deleteFiles=true**<br><br>```java<br>Response:<br>{<br>  "success": true<br>}<br>```<br><br>**Example 2:**  <br>`http://jira.yourorg.com/rest/gitplugin/1.0/`**repository**`?`**id=5**<br><br>```java<br>Response:<br>{<br>  "success": false,<br>  "error": "Repository with id=5 does not exist",<br>  "advice": "Please try again with an existing repository id."<br>}<br>``` |

### Related articles

*   Page:
    
    [Retrieve Repository List](/wiki/spaces/GIJDC/pages/380666386/Retrieve+Repository+List) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Add New Repository](/wiki/spaces/GIJDC/pages/380666393/Add+New+Repository) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Update Existing Repository](/wiki/spaces/GIJDC/pages/380699263/Update+Existing+Repository) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Delete Existing Repository](/wiki/spaces/GIJDC/pages/380797296/Delete+Existing+Repository) (Git Integration for Jira Data Center)