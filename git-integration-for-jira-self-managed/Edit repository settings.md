---

title: Edit repository settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

HOSTED EXTERNAL FOLDER

Click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Action ➜ **Edit repository settings** to open the **Git Repository - Advanced** page where you can change the settings of the selected connected repository: `HOSTED`, `EXTERNAL` or `FOLDER`.

Utilize the options below for configuring repository settings:

|     |     |     |
| --- | --- | --- |
| **Option** | **Description** | **Integration** |
| _**Display Name**_ | This is the alias that will appear in the Repository/Integration column. | HOSTED EXTERNAL FOLDER |
| _**Key**_ | This is the key name for this repository connection. | HOSTED |
| _**Absolute Repository Root**_ | This is the calculated absolute path of the clone repository root on the same machine as Jira. | HOSTED EXTERNAL FOLDER |
| _**Clone root location**_ | Set to automatically managed or manually configured by Jira admin. | HOSTED EXTERNAL FOLDER |
| _**Repository Root**_ | This is the path to a clone of the repository. | HOSTED EXTERNAL |
| _**Enable Fetches**_ | Set to either hosted at remote server or hosted on the same server as Jira. | EXTERNAL |
| _**Main Branch**_ | Set the main branch. Default is `master`. | HOSTED EXTERNAL |
| _**Use HTTP(S) Authentication**_ | If this repository connection supports HTTP(S)) authentication, turn on this feature and enter the required username and password credentials here. | EXTERNAL |
| _**SSL Verify**_ | Enable/Disable. If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a remote Git server. | EXTERNAL |
| _**TrustFolderStat**_ | When this setting is set to `False`, the objects/pack folder will always be scanned to check for new pack files. If set to `True`, the `last-modified` attribute of the folder will be used instead to check the folder for modifications.<br><br>The default value for Jira Server is `True`. For Jira Data Center, it's `False`.<br><br>If your repository is stored on a network share, it is highly recommended to set this option to `False`. | HOSTED EXTERNAL FOLDER |
| _**Advanced: Revision Indexing and Fetch refspec**_ | Set Revision Indexing and Fetch refspec settings as desired.<br><br>**Revision indexing**  <br>This option turns on the memory cache which is used when list of commits are displayed. Select if revision indexing will index and link to any mentioned issue keys in the revision history or not.<br><br>**Fetch refspec**  <br>Git refspecs contain patterns mapped as references from the remote to the local repository. The first two refspec options are required. The rest of the options are optional.<br><br>For more information, see [**Git Internals – The Refspec**](https://git-scm.com/book/en/v2/Git-Internals-The-Refspec). | EXTERNAL FOLDER |
| _**Repository Browser**_ | Enabled/Disabled. When `Enabled`, it allows users to view Git repositories of configured projects. For more information, see [Repository Browser](/git-integration-for-jira-self-managed/Repository-Browser). | HOSTED EXTERNAL FOLDER |
| _**Tags**_ | Set whether to show all tags or show on tags with matching regex pattern. For more information on git tags, see [Git tags](/git-integration-for-jira-self-managed/Git-tags). | HOSTED EXTERNAL FOLDER |
| _**Project Permissions: Restrict to projects**_ | The default setting is **Associate with all projects**. You can restrict access to the Repository Browser and Git Commit tabs (Advanced) for the selected repository by setting the project associations. | HOSTED EXTERNAL FOLDER |
| _**Source Code Diff Viewing**_ | Allows users to view the diff by commit and file. | HOSTED EXTERNAL FOLDER |
| _**Smart Commits**_ | Allows the users to use the smart commits feature. | HOSTED EXTERNAL FOLDER |
| _**Commit Message Validation**_ | Turn this setting `On` to reject/ignore any commit that does not reference a valid Jira issue key. | HOSTED |
| _**Commit Notification Emails**_ | Enable/disable this setting to allow sending of commit notification emails.<br><br>Set the **Max commit age (in minutes)** as desired. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. | HOSTED EXTERNAL FOLDER |
| _**Web Linking**_ | _Optional._<br><br>The web linking feature adds links to your git hosting provider directly into the Git Commits tab. For special integrations (Auto-Connect), this feature is configured automatically. For more information on about this topic, see [Web linking](/git-integration-for-jira-self-managed/Web-linking). | EXTERNAL |

**AU**

[« Edit integration feature settings](/wiki/spaces/GIJDC/pages/1930397576/Edit+integration+feature+settings)

[SSL verify »](/git-integration-for-jira-self-managed/SSL-verify)

