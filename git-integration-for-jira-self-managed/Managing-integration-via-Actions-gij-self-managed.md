---

title: Managing integration via Actions
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
After integrating your repository or git host, a set of actions can be performed by clicking the ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) icon under the **Actions** column on the repository/integration configuration list.

The set of functions depends on what type of integration or repository connection is selected:

## HOSTED and EXTERNAL (Single repository)

### Reindex repository

Immediately starts the synchronization with the selected repository.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the repository is disabled, this option is not available.
    </div>
    </div>
</div>

### Edit repository settings

Opens the **Git Repository - Advanced** page where you can change the settings of the selected connected repository.

For more details, see [Edit repository settings](/git-integration-for-jira-self-managed/edit-repository-settings/).

### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

### Remove repository

Disconnects the repository and removes its settings from the Git Integration for Jira app repository configuration.

### View log

Opens a dialog showing the indexing log of the connected repository. |

* * *

## FOLDER (Tracked folder)

### Show tracked repositories

Opens the **Tracked Repositories** dialog to view the connected tracked folder repositories. This option is only available if the added repository is a tracked folder.

For more information about this function, see [View tracked repositories](/git-integration-for-jira-self-managed/show-tracked-or-integration-repositories/).

### Edit repository settings

Opens the **Git Repository - Advanced** page where you can change the settings of the selected tracked folder integration.

For more details, see [Edit repository settings](/git-integration-for-jira-self-managed/edit-repository-settings/).

### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

### Remove tracked folder

Disconnects the tracked folder integration and removes its settings from the Git Integration for Jira app repository configuration.

### View log
Opens a dialog showing the indexing log of the connected tracked repository.

* * *

## AUTO-CONNECT** (Integration)

### Reindex integration

Immediately starts the synchronization with the selected repository.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the integration is disabled, this option is not available.
    </div>
    </div>
</div>

### Show integration repositories

Opens the **Tracked folder** dialog to manage multiple repositories for this integration. You can enable/disable connected repositories individually. Clicking a repository name will open the connection settings for the selected repository.

For more information about this function, see [View tracked repositories](/git-integration-for-jira-self-managed/show-tracked-or-integration-repositories/).

### Edit integration connection settings

Opens the [Integration connection settings](/git-integration-for-jira-self-managed/edit-integration-connection-settings/) page where you can change the connection settings of the selected integration.

### Edit integration feature settings

Opens the [Integration feature settings](/git-integration-for-jira-self-managed/edit-integration-feature-settings/) page where you can change the feature settings of the selected integration.

### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

### Remove integration

Disconnects the selected integration and removes its settings from the Git Integration for Jira app repository configuration.

### View log

Opens a dialog showing the indexing log of the selected integration. |

* * *

The tracked folder and auto-connect integrations can be configured using the following methods:

*   **Integration** _level_  –  Click  <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration connection settings**. This will open the settings for the selected integration.

*   **Repository** _level_  –  Click  <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Show integration repositories**. Click a repository from the list to open the settings for the selected repository.

