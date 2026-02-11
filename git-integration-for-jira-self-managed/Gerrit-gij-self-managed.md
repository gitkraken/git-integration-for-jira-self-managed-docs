---

title: Gerrit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](/wp-content/uploads/gerrit-banner-logo.png)

&nbsp;

## Integrate Gerrit with Jira Data Center

Quickly learn how to connect Gerrit git repositories via Git Integration for Jira Data Center.
For the Jira Cloud version of this document click [Here](/git-integration-for-jira-cloud/gerrit-gij-self-managed)

**What's on this page:**
- [Integrate Gerrit with Jira Data Center](#integrate-gerrit-with-jira-data-center)
  - [Using Full feature Integration](#using-full-feature-integration)
  - [Single Repository (Manually Connect via SSH, HTTP, HTTPS)](#single-repository-manually-connect-via-ssh-http-https)
  - [Setting Up Gerrit Web Links](#setting-up-gerrit-web-links)
  - [Viewing Git Commits in Jira Data Center](#viewing-git-commits-in-jira-data-center)
  - [Default Branch](#default-branch)
  - [How to enable GetRepositories log response from Gerrit to the Jira log?](#how-to-enable-GetRepositories-log-response-from-Gerrit-to-the-Jira-log)
  - [More Integration Guides](#more-integration-guides)

<br>
<hr>
&nbsp;

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/rknbc3ty4e?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:12px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/rknbc3ty4e'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

### Using Full feature Integration

1.  On your Jira dashboard, go to menu Git ➜ **Manage repositories**.

2.  Click **Gerrit** on the Auto-connect integration panel. The Auto-connect wizard appears.

    ![](/wp-content/uploads/gij-jira-server-gerrit-auto-connect-wiz-login-c.png)

    *   Enter your git server’s **Host URL**.

    *   Enter login credentials for username and password.

    *   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>OPTIONAL</b> Click <b>Advanced</b> to setup how git fetches refs.

        ![](/wp-content/uploads/gij-jira-server-gerrit-auto-connect-advanced-c.png)

        *   Setup fetch refspec by selecting options needed for this integration. A refspec maps a branch in the local repository to a branch in a remote repository. For more information, see <a href='https://git-scm.com/book/en/v2/Git-Internals-The-Refspec' target='_blank'><b>Git Refspec</b></a>.

        *   For **Clone and index other refs**, enable it to define a custom refspec tailored for this integration. A refspec is specified as `[+]<source>:<destination>` --- where, `<source>` is the source branch in the local repository and `<destination>` is the destination branch in the remote repository. The optional `+` sign instructs git to force the remote repository to perform a non-fast-forward update.

        *   For more detailed information on formatting, see <a href='https://git-scm.com/docs/git-fetch' taget='_blank'><b>Git Fetch</b></a>.

            <div class="bbb-callout bbb--note">
            <div class="irow">
                <div class="ilogobox">
                <span class="logoimg"></span>
                </div>
                <div class="imsgbox">
                    <b>Note:</b><br>
                    <i>The new values will be applied to the subsequent fetches only instead of applying it to the objects that have been already fetched</i>.
                </div>
            </div>
            </div>

3.  Click **Connect**. The Auto-connect wizard automatically reads git repositories for import into the git configuration.

4.  Click **Import repositories**. The Settings screen is displayed.

    ![](/wp-content/uploads/gij-gerrit-git-server-autoconnect-settings-dlg-c.png)

    *   Set **Smart Commits**, **Repository Browser** options or leave it as is.

    *   Set **Project Permissions** by restricting it to specific projects or leave it as is (_associate with all projects_).

5.  Click **Finish** to complete this setup.

&nbsp;

### Single Repository (Manually Connect via SSH, HTTP, HTTPS)

Login to your Gerrit account. Obtain the repository URL from the Gerrit repository project page.  Use SSH or HTTP/HTTPS.

1.  On your Jira dashboard menu, go to **Git** ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** to open the Connect Wizard.

3.  Paste the URL from Gerrit web portal in the provided box. (_Example:_ `http(s)://<your.org.com>/<repo_name>`)

4.  Click **Next**. The Settings page is displayed.

    ![](/wp-content/uploads/gij-gerrit-git-server-autoconnect-settings-dlg-c.png)

    *   Set **Smart Commits**, **Repository Browser** options or leave it as is.

    *   Set **Project Permissions** by restricting it to specific projects or leave it as is (_associate with all projects_).

5.  Click **Finish** to complete this process.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The refspec options are not available for single repository connections of Gerrit integration.
    </div>
    </div>
</div>

The repository is now connected to Jira Data Center.

&nbsp;

### Setting Up Gerrit Web Links

Web links are automatically configured for Gerrit repositories with Auto-connect integration.

For manual integration. setting up web links for Gerrit integration is optional.

Configure web links from either of the following locations:

*   **Advanced setup** in Connect Wizard

*   Git ➜ Manage repositories ➜ **Edit repository/integration** settings.

<img src='/wp-content/uploads/gij-gerrit-web-linking-sample.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

Select the Gerrit git host from the **Web Link** dropdown list.

Set the variables to the actual URL settings of the git host.

Save the changes.

&nbsp;

### Viewing Git Commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.

&nbsp;

### Default Branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the **Repository Settings** of the Git Integration for Jira app on the next reindex. Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

For the case with Gerrit, the default main branch is always “master”.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Main branch for repositories within an integration can only be changed on the git server.
    </div>
    </div>
</div>

### How to enable GetRepositories log response from Gerrit to the Jira log?

1.  Open ![](/wp-content/uploads/actions-icon.png) Jira System Administration then click **Logging and profiling** on the left sidebar.

2.  Under the Default loggers section, click **Configure….**

3.  Set the Package name to `com.bigbrassband.jira.git.services.integration`.

4.  Set Logging Level to **DEBUG**.

5.  Click **Add** to proceed.

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b> Remember to turn this setting off after you have obtained the log file for analysis.

&nbsp;
* * *

### More Integration Guides

[GitHub.com](/git-integration-for-jira-data-center/gitHub-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub Enterprise Server](/git-integration-for-jira-data-center/gitHub-Enterprise-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab.com](/git-integration-for-jira-data-center/gitLab-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab CE/EE](/git-integration-for-jira-data-center/gitLab-com-CE-EE-gijsm-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Azure DevOps \| Visual Studio Team Services (VSTS)](/git-integration-for-jira-data-center/azure-DevOps-Visual-Studio-Team-Services-(VSTS)-gij-self-managed) (Git Integration for Data Center/Jira Server)

[Azure DevOps Server \| Team Foundation Services (TFS)](/git-integration-for-jira-data-center/azure-DevOps-Server-Team-Foundation-Services-(TFS)-gij-self-managed) (Git Integration for Jira Data Center/Server)

[AWS CodeCommit](/git-integration-for-jira-data-center/aws-codecommit-gij-self-managed) (Git Integration for Jira Data Center/Server)

**Gerrit** (this page)

[Bitbucket Server](/git-integration-for-jira-data-center/Bitbucket-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bonobo](/git-integration-for-jira-data-center/bonobo-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Windows Network \| Server Share](/git-integration-for-jira-data-center/Windows-Network-Server-Share-gij-self-managed)

[Tracked Folders](/git-integration-for-jira-data-center/tracked-Folders-gij-self-managed) (Git Integration for Jira Data Center/Server)

[**Back to:** Integration basics](/git-integration-for-jira-data-center/Integration-Basics-gij-self-managed) (Git Integration for Jira Data Center/Server)


