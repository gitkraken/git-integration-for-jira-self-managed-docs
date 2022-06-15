---

title: Azure DevOps | Visual Studio Team Services (VSTS)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <b>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/azure-devops-visual-studio-team-services-vsts-gij-cloud/'>See the corresponding article</a>.
    </div>
    </div>
</div>


![](https://bigbrassband.atlassian.net/wiki/download/attachments/92176406/vsts-azure-devops-logo.png?version=1&modificationDate=1577430609568&cacheVersion=1&api=v2)

![](https://bigbrassband.com/confluence/images/vsts-new-logo.png)

<br>

# Integrate Azure DevOps/Visual Studio Team Services (VSTS) with Jira Data Center/Server

Quickly learn how to connect Azure DevOps/VSTS git repositories via Git Integration for Jira Data Center/Server.

The Git Integration for Jira app supports Azure Repos.

**What's on this page:**
- [Integrate Azure DevOps/Visual Studio Team Services (VSTS) with Jira Data Center/Server](#integrate-azure-devopsvisual-studio-team-services-vsts-with-jira-data-centerserver)
  - [Permissions](#permissions)
  - [Creating personal access tokens for Azure DevOps/VSTS account](#creating-personal-access-tokens-for-azure-devopsvsts-account)
  - [Using Full feature integration](#using-full-feature-integration)
  - [Single repository (Manual integration)](#single-repository-manual-integration)
  - [Webhooks and web linking](#webhooks-and-web-linking)
  - [Linking Azure DevOps/VSTS git commits to Jira Data Center/Server](#linking-azure-devopsvsts-git-commits-to-jira-data-centerserver)
  - [Viewing git commits in Jira Server](#viewing-git-commits-in-jira-server)
  - [Working with branches and pull requests](#working-with-branches-and-pull-requests)
    - [Default branch](#default-branch)
    - [Creating branches](#creating-branches)
    - [Pushing commits to the branch](#pushing-commits-to-the-branch)
    - [Creating pull requests](#creating-pull-requests)
    - [Merging _branch_ to _master_](#merging-branch-to-master)

* * *

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/dwk9zxeane?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/dwk9zxeane'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

## Permissions

Set Azure DevOps/VSTS repository permissions according to your organization's rules. Viewing commits from Jira requires the user to have at least **Read** or **View** permissions. For branch/pull request creation, set specific service users with **Write** permissions.

## Creating personal access tokens for Azure DevOps/VSTS account

Connecting to Azure DevOps / VSTS account requires personal access token to work. If you have not yet generated a personal access token (PAT), create your token by following the steps outlined [in this article.](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed#azure-devops-visual-studio-team-services-vsts/)

## Using Full feature integration

This process requires an existing Microsoft account with Azure DevOps or VSTS **git** projects.

We recommend using the Add new integration panel to connect multiple repositories from your Azure DevOps/VSTS account. This setup uses full feature integration offering functions and features not found on single repository connections.

1.  On the Jira Server dashboard menu, go to Git ➜ **Manage repositories**. The git configuration page for connecting repositories is displayed.

2.  On the Add new integration panel, click **Microsoft**. The following screen is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-azure-vsts-autoconnect-dlg(c).png?version=1&modificationDate=1638876141630&cacheVersion=1&api=v2&width=646&height=449)

    -  For _**External service**_, select **Visual Studio Team Services (VSTS)** or select **Azure DevOps** from the list, if you have it instead.

    -  Enter your personal access token (PAT) on the provided field.

    -  Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed by utilizing the following settings:

        *   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less. Read about JMESPath expressions on their [website](http://jmespath.org/).

            For help with writing expressions, please contact [support](mailto:support@bigbrassband.com).
            To learn more VSTS/Azure DevOps examples, see article [Jira Server: Working with JMESPath Filters](/wiki/spaces/GITSERVER/pages/129171463/Working+with+JMESPath+Filters).

            *   If the field is empty, the Git Integration for Jira app will get all available accounts and then scans all available git repositories.

            *   If the field is not blank, the app will assume it as a single account path and will try to use it. To connect to all available accounts, manually create integrations for each one of them.

        *   **Fetch refspec**  –  Git refspecs contains patterns mapped as references from the remote to the local repository.
            For more information, see **Git Internals -- The Refspec**.

            *   The first two refspec options are required.

            *   The rest of the options are OPTIONAL:

                *   **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching. This option is enabled by default. This affects git notes which are not shown:

                    *   ...when `refs/notes` are disabled on connecting a repository.

                    *   ...when a new note comes when `refs/notes` is disabled.

                *   **Clone and index changes (refs/changes)** – This is a reference to `refs/changes/*` used for fetching.  This option is turned off by default.

                *   **Clone and index other refs** – This is a user-defined list of references used for fetching.  It is a comma-separated list with the format:

                    *   `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

3.  Click **Connect** to continue.

4.  Login to your Microsoft account, if prompted.

5.  On the following dialog, Git Integration for Jira app will read all available repositories from Azure DevOps/VSTS. Click **Import repositories**.

    Repositories of the logged-in Microsoft user can be automatically connected to Jira Data Center/Server. Repositories that are added or removed from Azure DevOps/VSTS will be likewise connected or disconnected from Jira Server.
    Currently, all available accounts are scanned and corresponding URLs are created internally.

6.  After the import process, the **Settings** dialog is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-github-autoconnect-settings-dlg(c).png?version=1&modificationDate=1638876141633&cacheVersion=1&api=v2&width=646&height=449)
    1.  On the Integration Settings, setting the _**Require User PAT**_ option to `ON`, will require users to provide PAT specific for branch and merge requests _(via the developer panel on the Jira issue page)_.  For more information on this feature, see [Integration Settings: Require User PAT](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed/).

    2.  Set **Smart commits** and **Repository Browser** to enable/disable these features.

    3.  Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed/).

7.  Click **Finish** to complete this setup.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For now, only **git** projects are supported from Azure DevOps/VSTS.
    </div>
    </div>
</div>

Azure DevOps/VSTS git repositories are now connected to Jira Server.

## Single repository (Manual integration)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This section is for users who are using SSH connections or those who wanted to only connect a single specific repository.
    </div>
    </div>
</div>

This process requires an existing VSTS/Azure git repository. Look for the the VSTS/Azure repository URL on the repository project page.

Choose between SSH or HTTPS. Use this information to connect the VSTS/Azure git repository to your Jira server via Git Integration for Jira app:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vsts-azure-clone-repo-page.png?version=1&modificationDate=1638876141636&cacheVersion=1&api=v2&width=544&height=236)

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** to open the Connect Wizard.

3.  Paste the URL from Azure DevOps/VSTS web portal in the provided box.

4.  Continue to the next step by following the screen instructions.

5.  Click **Finish** to complete this process. 


The repository is now connected to Jira Server.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Webhooks fail with DefaultCollection in URL path</b><br>
        To fix webhooks for old VSTS/Azure repository connections with <code>DefaultCollection</code> in the URL path, update the <b><i>Repository origin</i></b> field in the Manage git repositories page ➜ &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit repository settings</b> with the repository URL currently being returned by Azure.
    </div>
    </div>
</div>
<br>

## Webhooks and web linking

The Git Integration for Jira app automatically configures web linking for Azure DevOps/VSTS git repositories.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Webhooks are supported on Azure DevOps / Visual Studio Team Services.</b><br>
        First - configure webhooks in the Git Integration app in Jira via the Git menu ➜ <b>Manage repositories</b> then click <b>Webhooks</b> (sidebar). Enable the feature and save the settings. Then <a href='https://docs.microsoft.com/en-us/azure/devops/service-hooks/services/webhooks?view=vsts'>follow these instructions</a> to setup the webhook triggers. Azure DevOps/VSTS webhooks will trigger an immediate index of all repositories within the integration.
    </div>
    </div>
</div>

For detailed step-by-step guide showcasing the webhooks setup, [see this article](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed/).

For single repository connections, web link setup is optional. However, git links will become available in Git Commits tab when configured. For more information on this feature, see [Documentation: Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed).

## Linking Azure DevOps/VSTS git commits to Jira Data Center/Server

This process requires a Azure DevOps/VSTS git repository.

1.  On your web browser, login to your Azure DevOps/VSTS account then go to your working repository.

2.  Clone this repository into your Visual Studio IDE.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vsts-webui-get-clone-url(c).png?version=1&modificationDate=1638876141639&cacheVersion=1&api=v2&width=374&height=433)

    ... or update your local repository files by performing a **Pull** action via VS IDE ➜ **Team Explorer**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vside-teamexp-sync-changes-pull(c).png?version=1&modificationDate=1638876141642&cacheVersion=1&api=v2&width=306&height=201)
3.  Create or modify a file from your local repository.

4.  Perform a commit of the changes via **Team Explorer** ➜ **Changes**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vs-ide-team-explorer-changes-commit-push(c).png?version=1&modificationDate=1638876141645&cacheVersion=1&api=v2&width=306&height=299)
    *   Enter the commit message by mentioning the Jira issue key to associate this commit to. _(Underlined in red)_.

    *   Click the dropdown on the **Commit All** button then select **Commit All and Push**.

5.  The commit is now displayed in the specified Jira issue.


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-azure-vsts-commits-view.png?version=1&modificationDate=1638876141648&cacheVersion=1&api=v2&width=544&height=183)

## Viewing git commits in Jira Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View full commit** to view the code diff.


For more information on this feature, see [Documentation: Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed/).

## Working with branches and pull requests

This process requires a Azure DevOps/VSTS git repository and a PAT with at least `Code (read and write)` scope.

### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Repositories added via Add new integration support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

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
<br>

### Creating branches

1.  On your Jira Server, open a Jira issue. 

2.  On the [Jira Git integration development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed/), go to **Git integration** section then click **Create branch**. The following dialog is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-create-branch-dlg-azure-off(c).png?version=1&modificationDate=1638876141651&cacheVersion=1&api=v2&width=578&height=318)

    -  Select a **Repository** from the list.

    -  Choose a **Base branch**.

    -  Enter a **Branch name** or leave it as is (recommended).

    -  If the [Require User PAT option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed/) is enabled in the **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead.

        ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-create-branch-dlg-azure-github-reqPAT(c).png?version=1&modificationDate=1638876141654&cacheVersion=1&api=v2&width=510&height=281)

    -  Click the link label below the repository selector to setup the PAT. The following dialog appears.

        ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-setup-pat-dlg(c).png?version=1&modificationDate=1638876141656&cacheVersion=1&api=v2&width=544&height=300)

        *   Enter your personal access token from your Azure profile settings.

        *   When you click **Update** to save the settings:

            *   If this field is blank and no PAT is provided, nothing is changed and saved.

            *   If PAT has been previously configured and this field is blank, the PAT will be discarded.

            *   If a PAT has changed since last configuration and is provided, the new PAT is used.

        *   PAT settings can be accessed via Repository browser ➜ **Pers. access** column.

            ![](https://bigbrassband.atlassian.net/wiki/download/attachments/80805899/gitserver-repo-browser-pat-sel(c).png?version=1&modificationDate=1638876141660&cacheVersion=1&api=v2)

        *   Click the Edit ![](/wp-content/uploads/gij-edit-icon-dark.png) icon to setup/reconfigure PAT. The checkmark adjacent to the edit icon indicates PAT has been configured.

3.  Click **Create branch**. The newly-created branch is now listed in the developer panel under **Branches**.


### Pushing commits to the branch

Perform a commit to the newly-created branch to be ready for merge.

1.  On your VS IDE, go to **Team Explorer** and perform a **Pull** action. This will update your local repository with a new branch list.

2.  Go to **Team Explorer** ➜ **Branches**.

3.  Under **Active Repositories**, expand the **remote/origin** folder view.

4.  Right click the new branch then select **Checkout**. The new branch will be listed in the active repositories list.

5.  Make changes to a file to prepare it for commit and branch merge.

6.  On the Team Explorer, click **Changes**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vs-ide-teamexp-branch-commit-push(c).png?version=1&modificationDate=1638876141663&cacheVersion=1&api=v2&width=348&height=340)

    *   Make sure that **Branch:** displays the name of the newly-created branch.  If not, select it again from the list.

    *   Add the Jira issue key to the commit message. _(Underlined in red)_.
        This will associate the commit to the mentioned Jira issue key.

    *   Click the dropdown on the **Commit All** button then select **Commit All and Push**.


The commit is pushed to the new branch and is now ready for merge..

### Creating pull requests

The pull request feature works the same as merge request.

To create a pull request and merge it to the main source (master):

1.  On your Jira Server, open the Jira issue where your previously created a branch.

2.  On the developer panel under **Git integration**, click **Create pull request**. The following dialog is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-create-pullreq-dlg-off(c).png?version=1&modificationDate=1638876141667&cacheVersion=1&api=v2&width=544&height=300)
    *   Select a **Repository** from the list.

    *   Choose the newly-created branch as the **Source branch**.

    *   Set _**master**_ as the **Target branch**.

    *   Enter a descriptive title or leave it as is _(recommended)_.

    *   If the **Require User PAT option** is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead.

        ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-create-pull-req-dlg-azure-reqPAT(c).png?version=1&modificationDate=1638876141671&cacheVersion=1&api=v2&width=578&height=318)

        *   Click the link label below the repository selector to setup the PAT.

        *   If an invalid PAT was configured for the selected repository, the pull request creation process will fail.

3.  Click **Create** to create the pull request.


The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your Azure DevOps/VSTS web portal.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/80805899/vsts-webui-branch-ready-for-merge.png?version=1&modificationDate=1638876141674&cacheVersion=1&api=v2)

### Merging _branch_ to _master_

Continuing from the above steps, the current branch is ready for merge.

1.  On the Team Explorer, update your local repository by performing a **Pull** action.

2.  Go to **Pull Requests**.
    The pending pull request items are displayed here. Pull requests requires the approval of the reviewers before it can be merged from the VS IDE.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vs-ide-teamexp-pull-request-approved(c).png?version=1&modificationDate=1638876141678&cacheVersion=1&api=v2&width=306&height=328)

3.  Go to **Branches** then click **Merge**. The following screen is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/vs-ide-team-explorer-branch-merge-2017(c).png?version=1&modificationDate=1638876141682&cacheVersion=1&api=v2&width=306&height=262)

    *   Set the source to the branch to which you pushed the commits.

    *   Set the target branch to _**master**_.

4.  Click **Merge** to continue.


The reviewer's approval is required to completely merge the pull request. This usually takes place in the Azure DevOps/VSTS portal where your updated code is being reviewed.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/80805899/vsts-webui-pull-request-review-approve.png?version=1&modificationDate=1638876141685&cacheVersion=1&api=v2)

Once approved, the team leader or reviewer can then complete the merge. The commit can be viewed in the associated Jira issue page.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/80805899/gitserver-git-commits-azure-tests.png?version=1&modificationDate=1638876141689&cacheVersion=1&api=v2&width=663&height=208)

