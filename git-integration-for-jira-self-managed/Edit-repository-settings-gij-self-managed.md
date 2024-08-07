---

title: Edit repository connection settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Starting **v4.24+**, the Edit repository settings page have been revamped and improved.

![](/wp-content/uploads/gij-gitserverdc-edit-repository-actions-menu-sel.png)

&nbsp;

On the Manage integration list, click <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit repository settings**. This is where you can manage repository connection settings for the chosen repository. The available settings depend on which type of repository you are currently working on: `HOSTED`, `EXTERNAL` or `FOLDER`.

![](/wp-content/uploads/gij-gitserverdc-edit-repo-connection-settings-01.png)

&nbsp;

On the top part of the page is a toggle to enable or disable the currently chosen repository connection. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b>

On the integration panel, the repository origin and its status is displayed. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b>

Utilize the options below for configuring repository settings:

### Display name

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-repo-connection-settings-02.png' style='margin:25px auto;max-width:100%;display:block;' />

This is the alias that will appear in the Repository/Integration column.

### Cloned repository root

This settings group contains configuration related to the cloned repository root.

<img src='/wp-content/uploads/gij-gitserverdc-edit-repo-connection-settings-03.png' style='margin:25px auto;max-width:100%;display:block;' />

| Option | Description | Type |
| :--- | :--- | :--- |
| _**Absolute Repository Root**_ | This is the calculated absolute path of the clone repository root on the same machine as Jira. This field is read-only. | HOSTED EXTERNAL FOLDER |
| _**Cloned root location**_ | Set this cloned repository to be automatically managed by Git Integration for Jira app or manually configured by the Jira admin. | HOSTED EXTERNAL FOLDER |
| _**Repository Root**_ | This is the path to a clone of the repository. The full path is also displayed below the field box if available. | HOSTED EXTERNAL |
| _**Enable Fetches**_ | Set if the git is either hosted at remote server or hosted on the same server as Jira. | EXTERNAL |
| _**Repository origin**_ | This is the path to the git origin where the cloned repository came from. This field is read-only. | HOSTED EXTERNAL |

&nbsp;

### Manage credentials

<img src='/wp-content/uploads/gij-gitserverdc-edit-repo-connection-settings-04.png' style='margin:25px auto;max-width:100%;display:block;' />

| Option | Description | Type |
| _**Use HTTP(S) Authentication**_ | If this repository connection supports HTTP(S) authentication, turn on this feature and enter the required username and password credentials here. | EXTERNAL |
| _**Username**_ | Only accessible if the Use HTTP(S) authentication setting is enabled.<br><br>Enter the username to login for this git repository. | EXTERNAL |
| _**Password / Personal access token**_ | Only accessible if the Use HTTP(S) authentication setting is enabled.<br><br>Enter password for the username to login for this git repository. If personal access token is configured for the username, enter that instead. | EXTERNAL |
| _**SSL Verify**_ | Enable/Disable. If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a remote Git server. | EXTERNAL |
| _**TrustFolderStat**_ | When this setting is set to `False`, the objects/pack folder will always be scanned to check for new pack files. If set to `True`, the `last-modified` attribute of the folder will be used instead to check the folder for modifications.<br><div class="bbb-callout bbb--info"><div class="irow"><div class="ilogobox"> <span class="logoimg"></span></div><div class="imsgbox">The default value for Jira Server is <code>True</code>. For Jira Data Center, it's <code>False</code>.</div></div></div> <div class="bbb-callout bbb--note"><div class="irow"><div class="ilogobox"><span class="logoimg"></span></div><div class="imsgbox">If your repository is stored on a network share, it is highly recommended to set this option to <code>False</code>.</div></div></div> | HOSTED EXTERNAL FOLDER |

&nbsp;

### Integration connection advanced settings

Set Revision Indexing and Fetch refspec settings as desired.

<img src='/wp-content/uploads/gij-gitserverdc-plain-repo-connection-settings-adv-425.png' style='margin:25px auto;max-width:100%;display:block;' />

| _**Revision Indexing**_ | This setting turns on the memory cache which is used when list of commits are displayed. Select if revision indexing will index and link to any mentioned issue keys in the revision history or not. | EXTERNAL FOLDER |
| _**Fetch refspec**_ | Git refspecs contain patterns mapped as references from the remote to the local repository. The first two refspec options are required. The rest of the options are optional.<br><br>For more information, see <a href='https://git-scm.com/book/en/v2/Git-Internals-The-Refspec' target='_blank'><b>Git Internals – The Refspec</b></a>. | EXTERNAL FOLDER |

* * *

Click **Save** to save the settings.

Next, click **Feature settings** on the sidebar to open the configuration page related to repository features.

&nbsp;
* * *

[**Prev:** Edit integration feature settings](/git-integration-for-jira-data-center/edit-integration-feature-settings-gij-self-managed)

[**Next:** Edit repository feature settings](/git-integration-for-jira-data-center/edit-repository-feature-settings-gij-self-managed)

