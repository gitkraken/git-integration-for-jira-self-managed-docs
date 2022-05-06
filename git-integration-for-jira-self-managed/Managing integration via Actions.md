---

title: Managing integration via Actions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Managing integration via Actions

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397476/Managing+integration+via+Actions>

* * *

After integrating your repository or git host, a set of actions can be performed by clicking the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) icon under the **Actions** column on the repository/integration configuration list.

The set of functions depends on what type of integration or repository connection is selected:

|     |     |
| --- | --- |
| **HOSTED** and **EXTERNAL** (Single repository) |     |
| **Action** | **Description** |
| _**Reindex repository**_ | Immediately starts the synchronization with the selected repository.<br><br>JIRA SERVER DATA CENTER  <br>If the repository is disabled, this option is not available. |
| _**Edit repository settings**_ | Opens the **Git Repository - Advanced** page where you can change the settings of the selected connected repository. For more details, see [Edit repository settings](/wiki/spaces/GIJDC/pages/1947107348/Edit+repository+settings). |
| _**Reset index**_ | Clears the last indexed revision and rebuild Lucene index on next synchronization. |
| _**Remove repository**_ | Disconnects the repository and removes its settings from the Git Integration for Jira app repository configuration. |
| _**View log**_ | Opens a dialog showing the indexing log of the connected repository. |

|     |     |
| --- | --- |
| **FOLDER** (Tracked folder) |     |
| **Action** | **Description** |
| _**Show tracked repositories**_ | Opens the **Tracked Repositories** dialog to view the connected tracked folder repositories. This option is only available if the added repository is a tracked folder. For more information about this function, see [View tracked repositories](https://bigbrassband.com/git-integration-for-jira/documentation/setting-up-repos-manage-integration.html#view_tracked_repos). |
| _**Edit repository settings**_ | Opens the **Git Repository - Advanced** page where you can change the settings of the selected tracked folder integration. For more details, see [Edit repository settings](/wiki/spaces/GIJDC/pages/1947107348/Edit+repository+settings). |
| _**Reset index**_ | Clears the last indexed revision and rebuild Lucene index on next synchronization. |
| _**Remove tracked folder**_ | Disconnects the tracked folder integration and removes its settings from the Git Integration for Jira app repository configuration. |
| _**View log**_ | Opens a dialog showing the indexing log of the connected tracked repository. |

|     |     |
| --- | --- |
| **AUTO-CONNECT** (Integration) |     |
| **Action** | **Description** |
| _**Reindex integration**_ | Immediately starts the synchronization with the selected repository.<br><br>JIRA SERVER DATA CENTER  <br>If the repository is disabled, this option is not available. |
| _**Show integration repositories**_ | Opens the **Tracked folder** dialog to manage multiple repositories for this integration. You can enable/disable connected repositories individually. Clicking a repository name will open the connection settings for the selected repository. For more information about this function, see [View tracked repositories](/wiki/spaces/GIJDC/pages/1930397507/Show+tracked+or+integration+repositories). |
| _**Edit integration connection settings**_ | Opens the [Integration connection settings](/wiki/spaces/GIJDC/pages/1930397536/Edit+integration+connection+settings) page where you can change the connection settings of the selected integration. |
| _**Edit integration feature settings**_ | Opens the [Integration feature settings](/wiki/spaces/GIJDC/pages/1930397576/Edit+integration+feature+settings) page where you can change the feature settings of the selected integration. |
| _**Reset index**_ | Clears the last indexed revision and rebuild Lucene index on next synchronization. |
| _**Remove integration**_ | Disconnects the selected integration and removes its settings from the Git Integration for Jira app repository configuration. |
| _**View log**_ | Opens a dialog showing the indexing log of the selected integration. |

  
The tracked folder and auto-connect integrations can be configured using the following methods:

*   **Integration** _level_  –  Click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit integration connection settings**. This will open the settings for the selected integration.
    
*   **Repository** _level_  –  Click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Show integration repositories**. Click a repository from the list to open the settings for the selected repository.
    

[« Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration)

[Show tracked or integration repositories »](/wiki/spaces/GIJDC/pages/1930397507/Show+tracked+or+integration+repositories)

### More related topics about managing repositories/integration configuration

*   Page:
    
    [Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Managing integration via Actions](/wiki/spaces/GIJDC/pages/1930397476/Managing+integration+via+Actions) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Show tracked or integration repositories](/wiki/spaces/GIJDC/pages/1930397507/Show+tracked+or+integration+repositories) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Edit integration connection settings](/wiki/spaces/GIJDC/pages/1930397536/Edit+integration+connection+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Edit integration feature settings](/wiki/spaces/GIJDC/pages/1930397576/Edit+integration+feature+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [SSL verify](/wiki/spaces/GIJDC/pages/1930397639/SSL+verify) (Git Integration for Jira Data Center)
    
*   Page:
    
    [View integration or repository properties](/wiki/spaces/GIJDC/pages/1930397673/View+integration+or+repository+properties) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Viewing indexing logs](/wiki/spaces/GIJDC/pages/1930397702/Viewing+indexing+logs) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Removing integration or repository configuration](/wiki/spaces/GIJDC/pages/1930397738/Removing+integration+or+repository+configuration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Edit repository settings](/wiki/spaces/GIJDC/pages/1947107348/Edit+repository+settings) (Git Integration for Jira Data Center)