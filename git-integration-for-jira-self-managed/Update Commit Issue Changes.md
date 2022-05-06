---

title: Update Commit Issue Changes
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Update Commit Issue Changes

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/380699298/Update+Commit+Issue+Changes>

* * *

Updates the list of issues associated with the commit to the specified repository.

There are two types of users who can perform the Get Commit Issue Changes API call:

1.  Jira **administrators**
    
2.  Jira user who has **all** of the following:
    
    1.  **View/browse permissions** to the project;
        
    2.  **View Development Tools permissions** to the same project; and
        
    3.  The repository is **associated** to the project.
        

|     |     |
| --- | --- |
| **Update Commit Issue Changes** |     |     |
| _**url**_ |     |     |
| `http://`**<jira-host>**`/rest/gitplugin/1.0/`**repository**`/`**{repoId}**`/commits/`**{commitHash}**`/issues` |     |     |
| _**method**_ |     |     |
| POST |     |     |
| _**parameters**_ |     |     |
| **Parameter** | **Condition** |     |
| _**jira-host**_ | _String_. Required.<br><br>This is the default url location where you host your Jira.<br><br>**For example:**<br><br>`http://local-host-jira.com:2990`<br><br>`https://jira.your-organization.com` |     |
| _**repoId**_ | _Integer_. Required.<br><br>Substitute `{repoId}` with the actual repository ID.<br><br>Use the [Repository REST API](/wiki/spaces/GIJDC/pages/380699237/Repository+API) to obtain the connected repositories' IDs.<br><br>**Example:**<br><br>`http://`**local-host-jira.com:2990**`/rest/gitplugin/1.0/`**repository**`/`**1**`/commit/`**e012663bf9bd968388faa510cb5b310e4798c512**`/issues`<br><br>In the case of the above example, the commit association(s) of the specified commit hash and repository will be updated using the parameters specified in the JSON request body. See [changeStrs](#changeStrs) parameter. |     |
| _**commitHash**_ | _String_. Required.<br><br>This is the hash of the commit that you want the results from.<br><br>**Example:**  `e012663bf9bd968388faa510cb5b310e4798c512` |     |
| #### _changeStrs_ | The request body is a JSON structure supporting the following parameters: |     |
| **Parameter** | **Description** |
| _**a**_ | Adds a new issue key to associate to the commit. |
| _**d**_ | Disassociate the specified issue key from the commit. |
|     |     |
| **Example request:** |     |
| ```java<br>{<br>  "changeStrs": ["d:TST-5", "a:TST-6", "a:TST-7"]<br>}<br>``` |     |
| **response** |     |     |
| Returns the result for the example below. |     |     |

|     |
| --- |
| **Example for POST queries:** |
| ```java<br>POST /jira/rest/gitplugin/1.0/repository/1/commits/e012663bf9bd968388faa510cb5b310e4798c512/issues HTTP/1.1<br>Host: localhost:2990<br>Content-Type: application/json<br> <br>{<br>  "changeStrs": ["d:TST-5", "a:TST-6", "a:TST-7"]<br>}<br>``` |

|     |
| --- |
| **The** _**changeStrs**_ **modifier with the specified parameters will give the following result:** |
| ```java<br>Removes association of TST-5; and<br>associates TST-6 and TST-7 to the same commit in repo1 and repo2.<br>``` |

### Related articles

*   Page:
    
    [Get Commits](/wiki/spaces/GIJDC/pages/380764568/Get+Commits) (Git Integration for Jira Data Center)
    
*   Page:
    
    [showFiles](/wiki/spaces/GIJDC/pages/380699289/showFiles) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Get Commit Issue Changes](/wiki/spaces/GIJDC/pages/380797314/Get+Commit+Issue+Changes) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Update Commit Issue Changes](/wiki/spaces/GIJDC/pages/380699298/Update+Commit+Issue+Changes) (Git Integration for Jira Data Center)