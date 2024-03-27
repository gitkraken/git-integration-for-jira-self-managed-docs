---

title: Edit integration connection settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Starting version **4.24+**, the Edit integration settings page have been revamped and improved. The integration connection and feature settings are now merged into the integration settings page.

![](/wp-content/uploads/gij-gitserverdc-edit-integration-actions-menu-sel.png)

&nbsp;

On the Manage integrations list, click  <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit integration settings**. This will open the connection settings page for the selected integration by default.

![](/wp-content/uploads/gij-gitserverdc-edit-integration-connection-settings-01.png)

&nbsp;

On the top part of the page is a toggle to enable or disable the currently chosen integration. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b>

On the integration panel, the git host service and its status is displayed. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-connection-settings-02.png' style='margin:25px auto;max-width:100%;display:block;'>

Utilize the following options to configure the selected integration:

| Option | Description |
| :--- | :--- |
| _**Display Name**_ | This is the alias that will appear on the Repository/Integration column on the Manage repository/integrations configuration list. |
| _**Host URL**_ | Displays the URL path of the git host service. This field is read-only. |

&nbsp;

### Manage credentials

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-connection-settings-03.png' style='margin:25px auto 35 auto;max-width:100%;display:block;'>

On v4.24+, the following options are moved into the Manage credentials settings:

| Option | Description |
| :--- | :--- |
| _**Personal Access Token**_ | This is where you can update the personal access token if it is changed or has expired. |
| _**SSL Verify**_ | The Git Integration for Jira app will enforce/ignore verification of SSL certificate when connecting to a git server. For more information, see [SSL verify](/git-integration-for-jira-data-center/SSL-verify-gij-self-managed). |
| _**TrustFolderStat**_ | When this setting is set to `False`, the objects/pack folder will always be scanned to check for new pack files. If set to `True`, the `last-modified` attribute of the folder will be used instead to check the folder for modifications.<div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">The default value for Jira Server is <code>True</code>. For Jira Data Center, it's <code>False</code>.</div></div></div><div class="bbb-callout bbb--note"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your repository is stored on a network share, it is highly recommended to set this option to <code>False</code>.</div></div></div> |

&nbsp;

### Connection advanced settings

<img src='/wp-content/uploads/gij-gitserverdc-edit-connection-settings-new-adv-425.png' style='margin:25px auto 35 auto;max-width:100%;display:block;'>

Click the Advanced twisty to show more options to customize the integration connection.

| Option | Description |
| :--- | :--- |
| _**Revision indexing**_ | This option turns on the memory cache which is used when the list of commits are displayed. Choose if revision indexing will index and link to any mentioned Jira issue keys in the revision history or not. |
| _**Custom API Path**_ | This will trigger the integration to use the specified relative REST API path to retrieve the list of tracked repositories. This filter controls which repositories are integrated. For more details, see [Working with Custom API Path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed). |
| _**JMESPath Filters**_ | This feature uses regexp filter to limit API results and control which repositories are integrated. For more information, see [Working with JMESPath Filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed). |
| **Fetch refspec** | Git refspecs contain patterns mapped as references from the remote to the local repository. The first two refspec options are required. The rest of the options are optional.<br><br>For more information, see [Git Internals – The Refspec](https://git-scm.com/book/en/v2/Git-Internals-The-Refspec). |

Click **Save** to save the changes.

Next, go to the integration Feature settings page by clicking **Feature settings** on the sidebar.

&nbsp;
* * *

[**Prev:** Show tracked or integration repositories](/git-integration-for-jira-data-center/show-tracked-or-integration-repositories-gij-self-managed)

[**Next:** Edit integration feature settings](/git-integration-for-jira-data-center/edit-integration-feature-settings-gij-self-managed)

