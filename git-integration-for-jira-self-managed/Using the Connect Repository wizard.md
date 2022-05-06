---

title: Using the Connect Repository wizard
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Using the Connect Repository wizard

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard>

* * *

**What’s on this page:**

* * *

## Getting started

Navigate to the Manage repositories page.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930397090/gitserver-gitmgr-connect2git-sel.png?version=1&modificationDate=1630642822421&cacheVersion=1&api=v2)

To start integrating a git repository, follow the steps below:

1.  Click **Connect to Git Repository**. The connect repository wizard is displayed:
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-start-screen(new).png?version=1&modificationDate=1630642823179&cacheVersion=1&api=v2&width=646&height=501)
2.  Enter required repository location. The **Repository location** can be any type of supported gitl URL protocols as stated in the _**Location type**_ examples.
    
3.  Click **Next**. The Connect wizard will automatically detect the provided repository location type.
    

**Detection of Remote Origin Setting**

The detection works for most repositories. If a repository root points to a valid git repository, the repository origin is detected automatically. When a repository has no origin, the user has to specify it manually.

Do note that the Connect wizard **clones the remote repository by default**. It does not clone local repositories. For local repositories, the `root` is set to local path and fetches are disabled.

Starting **v2.6.7+** of the Git Integration app, the default identities are not used and the repository is created without the additional key upload.

If the Git repository file system is somehow available to the Jira server, you can save the clone step and save the disk space on a Jira server by pointing the Jira server straight at it.

### Settings

In the **Settings** screen, you can configure features such as [Smart Commits](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398395/%28GDC%29+Smart+commits), [Repository Browser](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398598/%28GDC%29+Repository+Browser) and [Project Permission](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397766/%28GDC%29+Associating+project+permissions) settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-cfg-screen.png?version=1&modificationDate=1630642823475&cacheVersion=1&api=v2&width=680&height=376)

*   **Smart Commits**  – Enable or disable this setting to allow processing of smart commits for this repository connection.
    
*   **Repository Browser** – Enable or disable this setting to allows users to view git repositories of configured projects via the **Git** menu on the Jira dashboard. This feature is only available on Jira Server/DC instances.
    
*   For _**Project Permissions**_, set one or more projects in the **Restrict to projects** field to map this repository and make the **Git Commits** tab available in the **Issue** pages of the associated projects. Otherwise, leave the _**Associate with all projects**_ state to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) to associate this repository to all projects.
    

  
The level of permissions can be one of the following:

|     |     |
| --- | --- |
| **Level** | **Process** |
| _**Repository**_ | Select a repository from the repository list. For repositories inside integrations, view the integration then select a repository within _(_![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Actions ➜ Show integration repositories)_. After the selection, you will be taken to the repository properties.<br><br>Set the **Project Permissions** as follows:<br><br>1.  Uncheck the **Associate with all projects** option.<br>    <br>2.  Click the _**Restrict to project**_ field and select one or more project(s).<br>    <br>3.  Save/Update the repository settings. |
| _**Integration**_ | Select an integration from the repository list then open the integration feature properties _(_![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Actions ➜ Edit integration feature settings)_.<br><br>Set the **Project Permissions** as follows:<br><br>1.  Uncheck the **Associate with all projects** option.<br>    <br>2.  Click the _**Restrict to project**_ field and select a project.<br>    <br>3.  Save/Update the repository settings. |
| _**All**_ | This is the default setting where the **Associate to all projects** option is in ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) state. |

For Project Permissions, the **View Development Tools** _project permission_ must be granted to Users ➜ Group ➜ _**Project Roles**_.

Click **Next**.

### HTTP(S) authentication

If the entered git clone URL requires HTTP credentials, the following screen appears:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-auth-scr-http(n).png?version=1&modificationDate=1630642824202&cacheVersion=1&api=v2&width=680&height=355)

Provide _**Username**_ and _**Password**_ in the respective fields then click **Next** to continue.

The HTTP authorization errors indicate that the credentials provided are not valid.

### SSH authentication

For SSH git repository connections, the following screen is displayed for authentication:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930397090/gitserver-ssh-connect-auth-screen.png?version=1&modificationDate=1630642825404&cacheVersion=1&api=v2)

Upload the private key file by clicking **Choose File** and navigate to the private key file. Otherwise, paste the private key text into the provided box.

For establishing safety connection with SSH, upload a public Key to the SSH server and set the private Key to the SSH client.

Take note that the SSH server is the Git server and the SSH client is the Jira server.

When adding a new repository that requires an SSH key, you can now pick an existing associated key in the _**Existing key**_ list (see Figure 4).

Click **Next** to proceed.

### Passphrase Input

If the generated SSH key pair has a passphrase, you will see the following screen:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397090/connect-git-wizard-auth-scr-pass.png?version=1&modificationDate=1630642824934&cacheVersion=1&api=v2&width=442&height=254)

Enter the _**Passphrase**_ for your private key. Click **Next** to continue.

The passphrase screen only appears if the user has added an SSH key that requires a passphrase.

The Git Integration for Jira app will initially try to use the keys provided by the user before using the keys from the home directory.

After the above requirements are fulfilled, the wizard will:

*   create a local copy of the git repository; and
    
*   index the git repository to build change history.
    

Click **Finish** to close the wizard.

This completes the setup and the newly added repository appears on the integration list on the Git Integration app repository configuration page.

[« Using the Add new integration wizard](/wiki/spaces/GIJDC/pages/1930397044/Using+the+Add+new+integration+wizard)

[Connecting a repository via Advanced setup »](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397180/%28GDC%29+Connecting+a+repository+via+Advanced+setup)

## More related topics about setting up repositories

*   Page:
    
    [Git integration configuration page](/wiki/spaces/GIJDC/pages/1930396951/Git+integration+configuration+page) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Using the Add new integration wizard](/wiki/spaces/GIJDC/pages/1930397044/Using+the+Add+new+integration+wizard) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Using the Connect Repository wizard](/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Connecting a repository via Advanced setup](/wiki/spaces/GIJDC/pages/1930397180/Connecting+a+repository+via+Advanced+setup) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding a repository hosted on Windows Server or Windows Network share](/wiki/spaces/GIJDC/pages/1930397287/Adding+a+repository+hosted+on+Windows+Server+or+Windows+Network+share) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setup repository root not located in Jira Home directory](/wiki/spaces/GIJDC/pages/1930397313/Setup+repository+root+not+located+in+Jira+Home+directory) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Tracked folders overview](/wiki/spaces/GIJDC/pages/1930397330/Tracked+folders+overview) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Self-signed HTTPS integration](/wiki/spaces/GIJDC/pages/1930397349/Self-signed+HTTPS+integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Associating project permissions](/wiki/spaces/GIJDC/pages/1930397766/Associating+project+permissions) (Git Integration for Jira Data Center)