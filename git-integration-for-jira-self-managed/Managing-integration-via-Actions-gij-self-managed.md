---

title: Managing integration via Actions
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

After integrating your repository or git host, a set of actions can be performed by clicking the ![](/wp-content/uploads/actions-icon.png) icon under the **Actions** column on the repository/integration configuration list.

The set of functions depends on what type of integration or repository connection is selected:

### HOSTED and EXTERNAL (Single repository)

#### Reindex repository

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

#### Edit repository settings

Opens the **Git Repository - Advanced** page where you can change the settings of the selected connected repository.

For more details, see [Edit repository settings](/git-integration-for-jira-data-center/edit-repository-settings-gij-self-managed).

#### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Please do note that this process will rebuild index from scratch. Take this into consideration when indexing very large repositories or integration.
    </div>
    </div>
</div>

On following screen, the user is prompted to also reset all main revision information or not. The default setting is enabled. For a proper rebuild of the index information, leave it as is. Click **Reset index** to proceed.

![](/wp-content/uploads/gij-gitserverdc-gitmgr-actions-reset-index-prompt.png)

#### Remove repository

Disconnects the repository and removes its settings from the Git Integration for Jira app repository configuration.

#### View log

Opens a dialog showing the indexing log of the connected repository. |

&nbsp;
* * *
&nbsp;

### FOLDER (Tracked folder)

#### Show tracked repositories

Opens the **Tracked Repositories** dialog to view the connected tracked folder repositories. This option is only available if the added repository is a tracked folder.

For more information about this function, see [View tracked repositories](/git-integration-for-jira-data-center/show-tracked-or-integration-repositories-gij-self-managed).

#### Edit repository settings

Opens the **Git Repository - Advanced** page where you can change the settings of the selected tracked folder integration.

For more details, see [Edit repository settings](/git-integration-for-jira-data-center/edit-repository-settings-gij-self-managed).

#### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Please do note that this process will rebuild index from scratch. Take this into consideration when indexing very large repositories or integration.
    </div>
    </div>
</div>

On following screen, the user is prompted to also reset all main revision information or not. The default setting is enabled. For a proper rebuild of the index information, leave it as is. Click **Reset index** to proceed.

![](/wp-content/uploads/gij-gitserverdc-gitmgr-actions-reset-index-prompt.png)

#### Remove tracked folder

Disconnects the tracked folder integration and removes its settings from the Git Integration for Jira app repository configuration.

#### View log
Opens a dialog showing the indexing log of the connected tracked repository.

&nbsp;
* * *
&nbsp;

### AUTO-CONNECT (Integration)

#### Reindex integration

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

#### Show integration repositories

Opens the **Integration** dialog to manage multiple repositories for this integration. You can enable/disable connected repositories individually. Clicking a repository name will open the connection settings for the selected repository.

For more information about this function, see [View tracked repositories](/git-integration-for-jira-data-center/show-tracked-or-integration-repositories-gij-self-managed).

#### Edit integration connection settings

Opens the [Integration connection settings](/git-integration-for-jira-data-center/edit-integration-connection-settings-gij-self-managed) page where you can change the connection settings of the selected integration.

#### Edit integration feature settings

Opens the [Integration feature settings](/git-integration-for-jira-data-center/edit-integration-feature-settings-gij-self-managed) page where you can change the feature settings of the selected integration.

#### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Please do note that this process will rebuild index from scratch. Take this into consideration when indexing very large repositories or integration.
    </div>
    </div>
</div>

On following screen, the user is prompted to also reset all main revision information or not. The default setting is enabled. For a proper rebuild of the index information, leave it as is. Click **Reset index** to proceed.

![](/wp-content/uploads/gij-gitserverdc-gitmgr-actions-reset-index-prompt.png)

#### Remove integration

Disconnects the selected integration and removes its settings from the Git Integration for Jira app repository configuration.

#### View log

Opens a dialog showing the indexing log of the selected integration. |

&nbsp;
* * *

The tracked folder and auto-connect integrations can be configured using the following methods:

*   **Integration** _level_  –  Click  ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit integration connection settings**. This will open the settings for the selected integration.

*   **Repository** _level_  –  Click  ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Show integration repositories**. Click a repository from the list to open the settings for the selected repository.

&nbsp;

### GitHub App integration

#### Reindex integration

Immediately starts the synchronization with the selected GHA integration.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the GHA integration is disabled, this option is not available.
    </div>
    </div>
</div>

#### Show integration repositories

Opens the **Integration** dialog to manage multiple repositories of an organization for this GHA integration. You can enable/disable connected repositories individually. Clicking a repository name will open the connection settings for the selected repository.

For more information about this function, see [View tracked repositories](/git-integration-for-jira-data-center/show-tracked-or-integration-repositories-gij-self-managed).

#### Edit integration connection settings

Opens the [Integration connection settings](/git-integration-for-jira-data-center/edit-integration-connection-settings-gij-self-managed) page where you can change the connection settings of the selected GHA integration.

#### Edit integration feature settings

Opens the [Integration feature settings](/git-integration-for-jira-data-center/edit-integration-feature-settings-gij-self-managed) page where you can change the feature settings of the selected GHA integration.

#### Reset index

Clears the last indexed revision and rebuild Lucene index on next synchronization.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Please do note that this process will rebuild index from scratch. Take this into consideration when indexing very large repositories or integration.
    </div>
    </div>
</div>

On following screen, the user is prompted to also reset all main revision information or not. The default setting is enabled. For a proper rebuild of the index information, leave it as is. Click **Reset index** to proceed.

![](/wp-content/uploads/gij-gitserverdc-gitmgr-actions-reset-index-prompt.png)

#### Remove integration

Disconnects the selected GHA integration and removes its settings from the Git Integration for Jira app repository configuration.

#### View log

Opens a dialog showing the indexing log of the selected GHA integration.

&nbsp;
* * *

[**Prev:** Managing repository or integration configuration](/git-integration-for-jira-data-center/managing-repository-or-integration-configuration-gij-self-managed)

[**Next:** Show tracked or integration repositories](/git-integration-for-jira-data-center/show-tracked-or-integration-repositories-gij-self-managed)

