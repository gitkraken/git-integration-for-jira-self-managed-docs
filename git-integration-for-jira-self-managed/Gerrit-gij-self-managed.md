---

title: Gerrit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979855/gerrit-banner-logo.png?version=1&modificationDate=1591009190980&cacheVersion=1&api=v2&width=272&height=112)

# Integrate Gerrit with Jira Data Center

Quickly learn how to connect Gerrit git repositories via Git Integration for Jira Data Center.
For the Jira Cloud version of this document click [Here](/git-integration-for-jira-cloud/gerrit-gij-self-managed/)

* * *

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/rknbc3ty4e?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rknbc3ty4e'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

## Using Full feature Integration

1.  On your Jira dashboard, go to menu **Git** ➜ **Manage repositories**.

2.  Click **Gerrit** on the Auto-connect integration panel. The Auto-connect wizard appears.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979855/jira-server-gerrit-auto-connect-wiz-login(c).png?version=1&modificationDate=1591009191460&cacheVersion=1&api=v2&width=646&height=449)

    *   Enter your git server’s **Host URL**.

    *   Enter login credentials for username and password.

    *   OPTIONAL Click **Advanced** to setup how git fetches refs.

        ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979855/jira-server-gerrit-auto-connect-advanced(c).png?version=1&modificationDate=1591009191907&cacheVersion=1&api=v2&width=510&height=225)

        *   Setup fetch refspec by selecting options needed for this integration. A refspec maps a branch in the local repository to a branch in a remote repository. For more information, see [**Git Refspec**](https://git-scm.com/book/en/v2/Git-Internals-The-Refspec).

        *   For **Clone and index other refs**, enable it to define a custom refspec tailored for this integration. A refspec is specified as `[+]<source>:<destination>` --- where, `<source>` is the source branch in the local repository and `<destination>` is the destination branch in the remote repository. The optional `+` sign instructs git to force the remote repository to perform a non-fast-forward update.

        *   For more detailed information on formatting, see [**Git Fetch**](https://git-scm.com/docs/git-fetch).

            **Note:** _The new values will be applied to the subsequent fetches only instead of applying it to the objects that have been already fetched_.

3.  Click **Connect**. The Auto-connect wizard automatically reads git repositories for import into the git configuration.

4.  Click **Import repositories**. The Settings screen is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/91979855/gerrit-git-server-autoconnect-settings-dlg(c).png?version=2&modificationDate=1591009193074&cacheVersion=1&api=v2)

    *   Set **Smart Commits**, **Repository Browser** options or leave it as is.

    *   Set **Project Permissions** by restricting it to specific projects or leave it as is (_associate with all projects_).

5.  Click **Finish** to complete this setup.


## Single Repository (Manually Connect via SSH/HTTP/HTTPS)

Login to your Gerrit account. Obtain the repository URL from the Gerrit repository project page.  Use SSH or HTTP/HTTPS.

1.  On your Jira dashboard menu, go to **Git** ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** to open the Connect Wizard.

3.  Paste the URL from Gerrit web portal in the provided box. (_Example:_ `http(s)://<your.org.com>/<repo_name>`)

4.  Click **Next**. The Settings page is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/91979855/gerrit-git-server-autoconnect-settings-dlg(c).png?version=2&modificationDate=1591009193074&cacheVersion=1&api=v2)

    *   Set **Smart Commits**, **Repository Browser** options or leave it as is.

    *   Set **Project Permissions** by restricting it to specific projects or leave it as is (_associate with all projects_).

5.  Click **Finish** to complete this process.


The refspec options are not available for single repository connections of Gerrit integration.

The repository is now connected to Jira Data Center.

## Setting Up Gerrit Web Links

Web links are automatically configured for Gerrit repositories with Auto-connect integration.

For manual integration. setting up web links for Gerrit integration is optional.

Configure web links from either of the following locations:

*   **Advanced setup** in Connect Wizard

*   Git ➜ Manage repositories ➜ **Edit repository/integration** settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979855/gerrit-web-linking-sample.png?version=1&modificationDate=1591009193560&cacheVersion=1&api=v2&width=680&height=356)

<br>

Select the Gerrit git host from the **Web Link** dropdown list.

Set the variables to the actual URL settings of the git host.

Save the changes.

## Viewing Git Commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.


## Default Branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the **Repository Settings** of the Git Integration for Jira app on the next reindex. Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

For the case with Gerrit, the default main branch is always “master”.

Main branch for repositories within an integration can only be changed on the git server.

