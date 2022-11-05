---

title: Azure DevOps Server | Team Foundation Services (TFS)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <b>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/azure-devops-server-team-foundation-services-tfs-gij-cloud'>See the corresponding article</a>.
    </div>
    </div>
</div>
<br>
<br>

<img src='/wp-content/uploads/gij-azure-devops-banner.png' width=481 height=77 style='max-width:100%' />

<img src='/wp-content/uploads/gij-tfs-logo.png' height=auto width=350 style='max-width:100%'/>

<br>
<br>

# Integrate Azure DevOps Server/TFS with Jira Data Center/Server

Quickly learn how to connect Azure DevOps Server/TFS git repositories via Git Integration for Jira Data Center/Server.

The Git Integration for Jira app supports Azure Repos.

- [Integrate Azure DevOps Server/TFS with Jira Data Center/Server](#integrate-azure-devops-servertfs-with-jira-data-centerserver)
  - [Creating a personal access token](#creating-a-personal-access-token)
  - [Permissions](#permissions)
  - [Using Full feature integration](#using-full-feature-integration)
  - [Single repository integration (Manual integration)](#single-repository-integration-manual-integration)
  - [Webhooks and web linking](#webhooks-and-web-linking)
  - [Linking commits of Azure DevOps Server/TFS projects to Jira Data Center/Server](#linking-commits-of-azure-devops-servertfs-projects-to-jira-data-centerserver)
  - [Viewing git commits in Jira Data Center/Server](#viewing-git-commits-in-jira-data-centerserver)
  - [Working with branches and pull requests](#working-with-branches-and-pull-requests)
    - [Default branch](#default-branch)
    - [Creating branches](#creating-branches)
    - [Pushing commits to the branch](#pushing-commits-to-the-branch)
    - [Creating pull requests](#creating-pull-requests)
    - [Merging branch to master](#merging-branch-to-master)
  - [More Integration Guides](#more-integration-guides)

<br>
<br>
<hr>
<br>
<br>

## Creating a personal access token

For TFS 2017, TFS 2018 and Azure DevOps Server, you can generate a personal access token (PAT) for extra security. Use this token as password or as login key for auto-connect or manual integration with Git Integration for Jira app.

To create PATs, follow the simple steps outlined in [in this article](/git-integration-for-jira-data-center/creating-personal-access-tokens#team-foundation-server-tfs-2017--tfs-2018).

## Permissions

Set Azure DevOps Server/TFS repository permissions according to your organization's rules. Viewing commits from Jira requires the user to have at least **Read** or **View** permissions. For branch/pull request creation, set specific service users with **Write** permissions.

## Using Full feature integration

Formerly called Auto-connect integration. This process requires at least an existing _**Contributor**_ user access to Azure DevOps Server/TFS git projects.

We recommend using the Add new integration panel to connect multiple repositories from your Azure DevOps Server/TFS. This setup uses full feature integration offering functions and features not found on single repository connections.

1.  On the Jira Data Center/Server dashboard menu, go to Git ➜ **Manage repositories**.

2.  The git configuration page for connecting repositories is displayed.

3.  On the Add new integration panel, click **Microsoft**. The following screen is displayed.

    ![](/wp-content/uploads/gij-gitserver-autoconnect-azure-tfs-start-c.png)

    *   Select **Team Foundation Server (TFS)**. If you are using **Azure DevOps Server**, select that instead.

    *   Enter the **Host URL**, **Username** and **Password** for this connection.

        ![](/wp-content/uploads/gij-gitserver-azure-tfs-autoconnect-pat-option-c.png)

        *   If PAT is configured in your Azure DevOps Server/TFS, tick the _**Use Personal Access Token**_ checkbox and enter your PAT in the provided field. Do note that PAT is only supported on TFS 2017 and newer.

        *   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b><br> Do NOT include the `\<DOMAIN\>` in the **Username** field when Azure DevOps Server/TFS is connected to Active Directory. The correct example is "`BigBrassBand\johnsmith`**"** ➜ "**johnsmith**"

        *   <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>HELPFUL TIP!</b><br>
        The **› Advanced** twisty has the default **/tfs** path. Thus, there is no need to add the `/tfs` to the **Host URL** path. If you know your specific collection, type it in the provided box. The Git Integration for Jira app initially reads and imports all collection from the connected Azure DevOps Server/TFS integration.

    *   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>OPTIONAL!</b> Configuring the **Advanced** settings is not required. However, admins/power users may set how the project listing is displayed with the following options:

        ![](/wp-content/uploads/gij-gitserver-azure-tfs-advanced-opt-tfs-c.png)

        *   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less. Read about JMESPath expressions on their <a href='http://jmespath.org/' target='_blank'>website</a>.

            For help with writing expressions, please contact [support](mailto:gijsupport@gitkraken.com).

            To learn more Azure DevOps Server/TFS examples, see article [Working with JMESPath Filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed).

            *   If the field is empty, the Git Integration for Jira app will get all available accounts and then scans all available git repositories.

            *   If the field is not blank, the app will assume it as a single account path and will try to use it. To connect to all available accounts, manually create integrations for each one of them.

        *   **Fetch refspec**  –  Git refspecs contains patterns mapped as references from the remote to the local repository.  
            For more information, see **Git Internals -- The Refspec**.

            *   The first two refspec options are required.

            *   The rest of the options are OPTIONAL:

                *   **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching.  This option is enabled by default. This affects git notes which are not shown:

                    *   ...when `refs/notes` are disabled on connecting a repository.

                    *   ...when a new note comes when `refs/notes` is disabled.

                *   Clone and index changes (refs/changes) – This is a reference to `refs/changes/*` used for fetching. This option is turned off by default.

                *   Clone and index other refs – This is a user-defined list of references used for fetching. It is a comma-separated list with the format:

                    *   `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

        *   **Suffix**  –  This is a relative path that defaults to "/tfs".

            *   If this field is blank, the Git Integration for Jira app automatically appends the default "/tfs" suffix and scans for all the collections inside it.

            *   If this field is not empty, the app assumes it as a single collection path and will try to use it.

        *   **Connect specific collection**  –  Turn this on to allow setting a collection to use. Turn this off (default) to scan for all collections.

        *   **Collection**  –  Enter a specific collection to use.

4.  Click **Connect** to continue.

    The Git Integration for Jira app lists available git repositories from Azure DevOps Server/TFS. Currently, all available accounts are scanned and corresponding URLs are created internally. Enable/disable repositories for use with Jira by ticking or unticking the checkbox for the selected repositories.

5.  Click **Import repositories**. 

    Currently, all available accounts are scanned and corresponding URLs are created internally.

    Repositories of the connected Azure DevOps Server/TFS can be automatically connected to Jira Data Center/Server. Repositories that are added or removed from Azure DevOps Server/TFS will be likewise connected or disconnected from Jira Data Center/Server.

6.  After the import process, the **Settings** dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-github-autoconnect-settings-dlg-c.png)

    *   On the **Integration Settings**, setting the _**Require User PAT**_ option to `ON` will require users to provide a PAT which will be used for branch and merge/pull requests creation/deletion _(via the developer panel on the Jira issue page)_. The recommended **Selected scopes** setting for this is `Code (read and write)`.

        For more information on this feature, see [Integration settings: Require User PAT](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).

        <img src='/wp-content/uploads/bbb-alert-20.png' width=20 height=20 />&nbsp; PATs were introduced with TFS 2017 and newer. TFS 2013 and TFS 2015 do not support PATs. If this property is set to `ON`, the users will not be able to create/delete branches and pull requests.

        <img src='/wp-content/uploads/bbb-info-20.png' />&nbsp; When the above setting is enabled, a branch or pull request cannot be created until a valid personal access token (PAT) is set.

    *   Set [Smart commits](/git-integration-for-jira-data-center/smart-commits-gij-self-managed/) and [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed) to enable/disable these features.

    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed).

7.  Click **Finish** to complete this setup. For now, only **git** projects are supported from Azure DevOps Server/TFS.

The Azure DevOps Server/TFS repositories are now connected to Jira Data Center/Server.

## Single repository integration (Manual integration)

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

This process requires an existing Azure DevOps Server/TFS git repository. Look for the repository URL on the repository project page.

Choose between SSH or HTTPS. Use this information to connect the Azure DevOps Server/TFS git repository to your Jira server via Git Integration for Jira app:

<img src='/wp-content/uploads/gij-vsts-azure-clone-repo-page.png' style='display:block;margin:25px auto;max-width:100%' />

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** (_or click Git icon on the Add new integration panel_) to open the Connect Wizard.

3.  Paste the URL from Azure DevOps Server/TFS web portal in the provided box.

4.  Continue to the next step by following the screen instructions.

5.  Click **Finish** to complete this process. 


The repository is now connected to Jira Data Center/Server.

## Webhooks and web linking

The Git Integration for Jira app automatically configures web linking for Azure DevOps/VSTS git repositories.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Webhooks are supported on Azure DevOps Server / Team Foundation Services.</b><br>
        First - configure webhooks in the Git Integration app in Jira via the Git menu ➜ <b>Manage repositories</b> then click <b>Webhooks</b> (sidebar). Enable the feature and save the settings. Then <a href='https://docs.microsoft.com/en-us/azure/devops/service-hooks/services/webhooks?view=vsts' target='_blank'>follow these instructions</a> to setup the webhook triggers. Azure DevOps Server/TFS webhooks will trigger an immediate index of all repositories within the integration.
    </div>
    </div>
</div>

For detailed step-by-step guide showcasing the webhooks setup, [see this article](/git-integration-for-jira-data-center/webhooks-gij-self-managed).

For single repository connections, web link setup is optional. However, git links will become available in Git Commits tab when configured. For more information on this feature, see [Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed).

## Linking commits of Azure DevOps Server/TFS projects to Jira Data Center/Server

For the following steps, a Azure DevOps Server/TFS and a Visual Studio environment that supports git is required.

1.  Open Visual Studio IDE. Sign in to your Microsoft account, if prompted.

2.  Connect to your Azure DevOps Server/Team Foundation Server:

    ![](/wp-content/uploads/gij-vs2013-connect-tfs-server-dlg-c.png)

    *   Select a server in the dropdown list to connect to. If this is a new connection, add a new server by clicking the **Servers…** button.

    *   On the next prompt dialog that appears:

        *   Type your Azure DevOps Server/TFS **Host URL**

        *   Enter **Username** and **Password**, if prompted.

    *   Click **OK** to continue.

3.  Select a **Team Project** to work on then click **Connect**.

    <img src='/wp-content/uploads/bbb-info-20.png' />&nbsp; For first time connection to the TFS/Azure DevOps Server team project, the default work branch is _**master**_.

4.  On the Team Explorer, click **Unsynced Commits** or **Sync**.

5.  Click the **Pull** to clone the git repositories to your local machine.

6.  Make changes to the code of a file/project.

7.  On the Team Explorer, click **Changes**.

8.  Type a message for this commit.  

    <img src='/wp-content/uploads/bbb-alert-20.png' />&nbsp; To associate this commit to the Jira issue page, mention the Jira issue key along with the commit message. For example: `PRJ-123 Fix null code`;

    Where `PRJ-123` is the Jira issue key and `Fix null code` is the commit comment.

    ![](wp-content/uploads/gij-vs-ide-team-explorer-make-commit-c.png)

9.  Click **Commit and Push**.

The commit is published to Azure DevOps Server/TFS. To view the commit in Jira, go to the Jira issue mentioned in the commit message. Click the **Git Commits** tab in the _**Activity**_ row.

<img src='wp-content/uploads/gij-gitserver-azure-tfs-commits-example.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

## Viewing git commits in Jira Data Center/Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View full commit** to view the code diff.

For more information on this feature, see [Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed).

## Working with branches and pull requests

This process requires a Azure DevOps/VSTS git repository and a PAT with at least `Code (read and write)` scope.

### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Repositories added via Add new integration support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

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

1.  On your Jira Data Center/Server instance, open a Jira issue.

2.  On the [Jira developer panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed), go to **Git integration** section then click **Create branch**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-azure-tfs-create-branch-dlg-c.png)

    1.  Select a **Repository** from the list.

    2.  Choose a **Base branch** (usually _**master**_).

    3.  Enter a **Branch name** or leave it as is (recommended).

    4.  If the [Require User PAT option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) is enabled in the **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

        ![](/wp-content/uploads/gij-gitserver-azure-tfs-create-branch-dlg-reqPAT-c.png)

    5.  Click the link label below the repository selector to setup the PAT. The following dialog appears.

        ![](/wp-content/uploads/gij-gitserver-setup-pat-dlg-c.png)

        *   Enter your personal access token from your Azure profile settings.

        *   When you click **Update** to save the settings:

            *   If this field is blank and no PAT is provided, nothing is changed and saved.

            *   If PAT has been previously configured and this field is blank, the PAT will be discarded.

            *   If a PAT has changed since last configuration and is provided, the new PAT is used.

        *   PAT settings can be accessed via Repository browser ➜ **Pers. access** column.

            ![](/wp-content/uploads/gij-gitserver-repo-browser-pat-sel-c.png)

        *   Click the edit <img src='/wp-content/uploads/gij-edit-icon-dark.png' /> icon to setup/reconfigure PAT. The checkmark adjacent to the edit icon indicates PAT has been configured.

3.  Click **Create branch**. The newly-created branch is now listed in the developer panel under **Branches**.

Perform a commit to the newly-created branch to be ready for merge.

### Pushing commits to the branch

<img src='/wp-content/uploads/gij-jira-cloud-tfs-server-branches-list.png' style='display:block;margin:25px auto;max-width:100%' />

To update the branch list to your Visual Studio's Team Explorer, perform a **Pull** action on the connected team project.  The branches list in your VS IDE should be updated now.

1.  On the Team Explorer, click **Branches**.

2.  Click **New Branch** then select the newly-created branch from the dropdown list.

3.  Click **Create Branch**. The selected branch is now listed under the **Published Branches** in the Team Explorer.

4.  Make changes to a file or project then perform a commit to the selected branch:

    ![](/wp-content/uploads/gij-vs-ide-team-explorer-branch-commit-c.png)

    1.  On the Team Explorer, click **Changes**.

    2.  <img src='/wp-content/uploads/bbb-alert-20.png' />&nbsp; Make sure that **Branch:** displays the name of the newly-created branch. If not, select it again from the list.

5.  Click **Commit and Push**.

The commit is pushed to the new branch and is now ready for merge.

### Creating pull requests

The pull request feature works the same as merge request.

To create a pull request and merge it to the main source (master):

1.  On your Jira Server, open the Jira issue where your previously created a branch.

2.  On the developer panel under **Git integration**, click **Create pull request**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-azure-tfs-create-pullreq-dlg-c.png)

    *   Select a **Repository** from the list.

    *   Choose the newly-created branch as the **Source branch**.

    *   Set _**master**_ as the **Target branch**.

    *   Enter a descriptive title or leave it as is _(recommended)_.

    *   If the Require User PAT option is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead.

        ![](/wp-content/uploads/gij-gitserver-azure-tfs-create-pullreq-dlg-reqPAT-c.png)

        *   Click the link label below the repository selector to setup the PAT.

        *   If an invalid PAT was configured for the selected repository, the pull request creation process will fail.

3.  Click **Create** to create the pull request.

The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your Azure DevOps Server/TFS web portal.

![](/wp-content/uploads/gij-jira-cloud-tfs-pull-request-merge-details.png)

<br>

### Merging branch to master

Continuing from the above steps, the current branch is ready for merge.

![](/wp-content/uploads/gij-jira-cloud-tfs-pull-request-ready-to-merge.png)

1.  On your Team Explorer, go to Branches.

2.  Click **Merge**.

    ![](/wp-content/uploads/gij-vs-ide-team-explorer-branch-merge-to-master-c.png)

    *   Set the source to the branch you pushed the commits to.

    *   Set the target branch to _**master**_.

3.  Click **Merge** to continue.

The reviewer's approval is required to completely merge the pull request. This usually takes place in the Azure DevOps Server/TFS server web UI where your updated code is being reviewed.

![](/wp-content/uploads/gij-tfs-web-ui-pull-request-approved-merge.png)

<br>

Once approved, the team leader or reviewer can then complete the merge. The commit can be viewed in the associated Jira issue page.

<img src='/wp-content/uploads/gij-gitserver-tfs-commits-tab-example.png' style='display:block;margin:25px auto;max-width:100%' />

<p>&nbsp;</p>

<br>
<br>

## More Integration Guides

[GitHub.com](/git-integration-for-jira-data-center/gitHub-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub Enterprise Server](/git-integration-for-jira-data-center/gitHub-Enterprise-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab.com](/git-integration-for-jira-data-center/gitLab-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab CE/EE](/git-integration-for-jira-data-center/gitLab-com-CE-EE-gijsm-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Azure DevOps | Visual Studio Team Services (VSTS)](/git-integration-for-jira-data-center/azure-DevOps-Visual-Studio-Team-Services-(VSTS)-gij-self-managed) (Git Integration for Data Center/Jira Server)

**Azure DevOps Server | Team Foundation Services (TFS)** (this page)

[AWS CodeCommit](/git-integration-for-jira-data-center/aws-codecommit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Gerrit](/git-integration-for-jira-data-center/gerrit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Windows Network | Server Share](/git-integration-for-jira-data-center/windows-Network-Server-Share-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Tracked Folders](/git-integration-for-jira-data-center/tracked-Folders-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bitbucket Server](/git-integration-for-jira-data-center/Bitbucket-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bonobo](/git-integration-for-jira-data-center/bonobo-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Integration basics](/git-integration-for-jira-data-center/Integration-Basics-gij-self-managed) (Git Integration for Jira Data Center/Server)

