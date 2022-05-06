---

title: Azure DevOps Server | Team Foundation Services (TFS)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Azure DevOps Server | Team Foundation Services (TFS)

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/91979843>

* * *

  

Using **Jira Cloud**? [See the corresponding article](/wiki/spaces/GITCLOUD/pages/86409345).

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979843/azure-devops-server-logo.png?version=1&modificationDate=1577429734090&cacheVersion=1&api=v2&width=441&height=70)

  

![](https://bigbrassband.com/confluence/images/tfs-logo.png)

**Integrate Azure DevOps Server/TFS with Jira Data Center**

Quickly learn how to connect Azure DevOps Server/TFS git repositories via Git Integration for Jira Data Center.

The Git Integration for Jira app supports Azure Repos.

**What's on this page:**

  

* * *

  

  

## Creating Personal Access Tokens

If you have not yet generated a personal access token (PAT), create your token by following [the steps outlined in this article.](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens#CreatingPersonalAccessTokens-tfs-server)

## Using Auto-Connect

This process requires at least an existing _**Contributor**_ user access to Azure DevOps Server/TFS git projects.

We recommend using the Auto-connect integration panel to connect multiple repositories from your Azure DevOps Server/TFS.

1. On the Jira Data Center dashboard menu, go to **Git** ➜ **Manage Git Repositories**.

2\. The git configuration page for connecting repositories is displayed.

3\. On the Auto-connect integration panel, click **Microsoft**. The following screen is displayed:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/91979843/jira-server-connect-tfs-login-screen.png?version=1&modificationDate=1577429884641&cacheVersion=1&api=v2)

Select **Team Foundation Server (TFS)**. If you are using **Azure DevOps Server**, select this instead.

Enter the **Host URL**, **Username** and **Password** for this connection.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/91979843/tfs-integration-use-pat-login.png?version=1&modificationDate=1577429734681&cacheVersion=1&api=v2)

If PAT is configured in your TFS or Azure DevOps server, tick the _**Use Personal Access Token**_ checkbox and enter your PAT in the provided field.

  

**Important!**

Do NOT include the <DOMAIN> in the **Username** field when Azure DevOps Server/TFS is connected to Active Directory.  

Example: "**BigBrassBand\\johnsmith"** ==> "johnsmith"

  

The **› Advanced** twisty has the default **/tfs** path. Thus, there is no need to add the **`/tfs`** to the **Host URL** path. If you know your specific collection, type it in the provided box. The Git Integration for Jira app defaults to read and import all collection in the connected Azure DevOps Server/TFS.

Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed with the following options:

![](https://bigbrassband.com/images/bbb/tfs-azure-vsts-advanced-twisty.png)

*   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less.
    *   If the field is empty, the Git Integration for Jira app will get all available accounts and then scans all available git repositories.
        
    *   If the field is not blank, the app will assume it as a single account path and will try to use it. To connect to all available accounts, manually create integrations for each one of them.
        
*   Read about JMESPath expressions on their [website](http://jmespath.org/). For help with writing expressions, please contact [support](mailto:support@bigbrassband.com?subject=Help%20with%20writing%20JMESPath%20filter%20expressions).
*   To learn more Azure DevOps Server/TFS examples, see article **[Jira Data Center: Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters)**.

*   **Suffix**  –  This is a relative path that defaults to "/tfs".

If this field is blank, the Git Integration for Jira app automatically appends the default "/tfs" suffix and scans for all the collections inside it.

If this field is not empty, the app assumes it as a single collection path and will try to use it.

*   **Connect specific collection**  –  Turn this on to allow setting a collection to use. Turn this off (default) to scan for all collections.
*   **Collection**  –  Enter a specific collection to use.

5\. Click Connect to continue.

The Git Integration for Jira app lists available git repositories from Azure DevOps Server/TFS. Enable/disable repositories for use with Jira by ticking or unticking the checkbox for the selected repositories.

6. Click Import repositories.

Currently, all available accounts are scanned and corresponding URLs are created internally. Repositories of the connected Azure DevOps Server/TFS can be automatically connected to Jira Data Center. Repositories that are added or removed from Azure DevOps Server/TFS will be likewise connected or disconnected from Jira Data Center.

7\. After the import process, the **Settings** dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-connect-vsts-settings-dialog.png)

*   On the **Integration Settings**, setting the **_Require User PAT_** option to **`ON`** will require users to provide a PAT which will be used for branch and merge/pull requests creation/deletion _(via the developer panel on the Jira issue page)_. The recommended **Selected scopes** setting for this is **`Code (read and write)`**.  For more information on this feature, see **[Integration Settings: Require User PAT »](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)**.

  

PATs were introduced with TFS 2017 and newer. TFS 2013 and TFS 2015 do not support PATs. If this property is set to **`ON`**, the users will not be able to create/delete branches and pull requests.

  

When the above setting is enabled, a branch or pull request cannot be created until a valid personal access token (PAT) is set.

*   Set **[Smart Commits »](https://bigbrassband.com/git-integration-for-jira/documentation/smart-commits.html "(opens in new tab/window)")** and **[Repository Browser »](https://bigbrassband.com/git-integration-for-jira/documentation/repository-browser.html "(opens in new tab/window)")** to enable/disable these features.
*   Set **Project Permissions** according to your organization's project association rules.

8\. Click Finish. For now, only **git** projects are supported from Azure DevOps Server/TFS.

The Azure DevOps Server/TFS repositories are now connected to Jira Data Center.

  

## Single Repository

![](https://bigbrassband.com/confluence/images/vsts-azure-clone-repo-page.png)

Obtain the repository URL from the Azure DevOps Server/TFS repository project page.  Choose between SSH or HTTPS.

1.  On your Jira dashboard menu, go to **Git** > **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from Azure DevOps Server/TFS web portal in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Data Center.

  

## Permissions

Set Azure DevOps Server/TFS repository permissions according to your organization's rules. Viewing commits from Jira requires the user to have at least **Read** or **View** permissions. For branch/pull request creation, set specific service users with **Write** permissions.

  

## Webhooks and Web Linking

The Git Integration for Jira app automatically configures web linking for Azure DevOps Server/TFS git repositories.

  

**Webhooks are supported on Azure DevOps Server/TFS.**

First - enable webhooks in the Git Integration app in Jira via the **Git** menu > **Manage Git Repositories** then click Webhooks.  Enable the feature and save the settings.  Then [follow these instructions](https://docs.microsoft.com/en-us/azure/devops/service-hooks/services/webhooks?view=vsts "Opens in new tab/window") to setup the webhook trigger.  Azure DevOps Server/TFS webhooks will trigger an immediate index of all repositories within the integration.

For detailed step-by-step guide showcasing webhooks setup, [see this article](/wiki/spaces/GIJDC/pages/235274262/Adding+Webhooks+for+Azure+DevOps+Server+%7C+TFS).

  

## Linking Commits of Azure DevOps Server/TFS Projects to Jira Data Center

For the following steps, a Azure DevOps Server/TFS and a Visual Studio environment that supports git is required.

1. Open Visual Studio IDE. Sign in to your Microsoft account, if prompted.

2\. Connect to your Azure DevOps Server/Team Foundation Server:

![](https://bigbrassband.com/images/bbb/vs2013-connect-tfs-server-dlg.png)

Select a server in the dropdown list to connect to.

If this is a new connection, add a new server by clicking Servers...:

*   Type your Azure DevOps Server/TFS **Host URL**
*   Enter **Username** and **Password**, if prompted.

Click    OK   to continue.

3\. Select a **Team Project** to work on then click Connect.

  

For first time connection to the TFS/Azure DevOps Server team project, the default work branch is _**master**_.

4\. On the Team Explorer, click Unsynced Commits or Sync.

5\. Click the **Pull** to clone the git repositories to your local machine.

6\. Make changes to the code of a file/project.

7\. On the Team Explorer, click Changes.

8\. Type a message for this commit.

  

To associate this commit to the Jira issue page, mention the Jira issue key along with the commit message.

**For example:**

**`PRJ-123 Fix null code`**

Where **`PRJ-123`** is the Jira issue key and **`Fix null code`** is the commit comment.

![](https://bigbrassband.com/images/bbb/vs-ide-team-explorer-make-commit.png)

9\. Click **Commit and Push**.

The commit is published to Azure DevOps Server/TFS.  To view the commit in Jira, go to the Jira issue mentioned in the commit message. Click the **Git Commits** tab in the _**Activity**_ row.

![](https://bigbrassband.com/images/bbb/tfs-jira-git-commits-tab-showcase.png)

  

## Viewing Git Commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.

  

## Working with Branches and Pull Requests with Azure DevOps Server/TFS

This process requires a Azure DevOps Server/TFS git repository and a PAT with at least **`Code (read and write)`** scope.

The Git Integration for Jira app supports creation of branches from Jira via the developer panel.

### Default Branch

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

  

Main branch for repositories within an integration can only be changed on the git server.

### Creating Branches

1. On your Jira Data Center, open a Jira issue. On the Jira developer panel under **Git Source Code**, click **Create Branch**.

2\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-cloud-create-branch-tfs.png)

*   Select a **Repository** from the list.
*   Choose a **Base branch** (usually _**master**_).
*   Enter a **Branch name** or leave it as is (recommended).

If the **[Require User PAT option](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)** is enabled in the **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.com/images/bbb/jira-server-tfs-branch-pat-conf-dlg.png)

  

PATs were introduced with TFS 2017 and newer.  TFS 2013 and TFS 2015 do not support PATs.  If the repository setting **Require User PAT** property is set to **`ON`**, the users will not be able to create/delete branches and pull requests.

*   Click the link label to setup the PAT.  This will show the Repository Browser listing of connected git repositories.

![](https://bigbrassband.com/images/bbb/jira-server-sel-repo-enter-user-pat.png)

*   Click   
     to setup a PAT for the selected repository. Paste a valid PAT of the current user to proceed. Invalid PATs will fail the branch creation process.
    
*   Click the   
    icon to use this PAT and save it to the current user profile. Otherwise, click the   
    icon on the right to cancel setting up PAT for this repository.
    
*   After the above steps have been taken, the users will be able to proceed with branch creation.

3\. Click Create Branch.  The branch is created and can be viewed under the **Branches** tab in your TFS server.

![](https://bigbrassband.com/images/bbb/jira-cloud-tfs-server-branches-list.png)

4\. To update the branch list to your Visual Studio's Team Explorer, perform a **Pull** action on the connected team project.  The branches list in your VS IDE should be updated now.

5\. On the Team Explorer, click Branches.

6\. Click **New Branch** then select the newly-created branch from the dropdown list.

7\. Click Create Branch. The selected branch is now listed under the **Published Branches** in the Team Explorer.

8\. Make changes to a file or project then perform a commit to the selected branch:

![](https://bigbrassband.com/images/bbb/vs-ide-team-explorer-branch-commit.png)

*   On the Team Explorer, click Changes.
*   Make sure that **Branch:** displays the name of the newly-created branch.  If not, select it again from the list.
*   Click **Commit and Push**.

The commit is pushed to the new branch and is now ready for merge..

### Creating Pull Requests

The pull request feature works the same as merge request.

To create a pull request and merge it to the main source (master):

1. On your Jira Data Center, open the Jira issue where your previously created a branch.

2\. On the developer panel under **Git Source Code**, click **Create Pull Request**.

3\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-cloud-tfs-create-pull-request-dialog.png)

*   Select your working **Repository**.
*   Set the **Source branch** to the newly-created branch.
*   Set the **Target branch** to **_master_**.
*   Give the pull request **Title** a descriptive name or leave it as is.

If the **[Require User PAT option](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)** is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.com/images/bbb/jira-server-issue-tfs-pull-req-dlg-cfg-pat.png)

If an invalid PAT was configured for the selected repository, the pull request creation process will fail.

4\. Click Create to create the pull request.

![](https://bigbrassband.com/images/bbb/jira-cloud-tfs-branch-and-pull-request-dev-panel.png)

The branch and the pull request status are displayed on the developer panel.

The pull request is also listed in the Azure DevOps Server/TFS:

![](https://bigbrassband.com/images/bbb/jira-cloud-tfs-pull-request-merge-details.png)

### Merging Branch to master

Continuing from the above steps, the current branch is ready for merge.

![](https://bigbrassband.com/images/bbb/jira-cloud-tfs-pull-request-ready-to-merge.png)

1\. On your Team Explorer, go to Branches.

2\. Click **Merge**.

![](https://bigbrassband.com/images/bbb/vs-ide-team-explorer-branch-merge-to-master.png)

*   Set the source to the branch you pushed the commits to.
*   Set the target branch to _**master**_.

3\. Click Merge to continue.

The reviewer's approval is required to completely merge the pull request. This usually takes place in the Azure DevOps Server/TFS server web UI where your updated code is being reviewed.

![](https://bigbrassband.com/images/bbb/tfs-web-ui-pull-request-approved-merge.png)

Once approved, the team leader or reviewer can then complete the merge.  The commit can be viewed in the associated Jira issue page.

![](https://bigbrassband.com/images/bbb/jira-cloud-tfs-branch-and-pull-request-merge-commit.png)

  

  

* * *

## More Integration Guides

page icon as list [Integrate GitHub.com with Jira Data Center](/wiki/spaces/GIJDC/pages/91979804/GitHub.com)

page icon as list [Integrate GitHub Enterprise with Jira Data Center](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server)

page icon as list [Integrate GitLab.com with Jira Data Center](/wiki/spaces/GIJDC/pages/91881531/GitLab.com)

page icon as list [Integrate GitLab CE/EE with Jira Data Center](/wiki/spaces/GIJDC/pages/91947056)

page icon as list [Integrate Azure DevOps/VSTS with Jira Data Center](/wiki/spaces/GIJDC/pages/92176406)

page icon as list [Integrate AWS CodeCommit with Jira Data Center](/wiki/spaces/GIJDC/pages/92176493/AWS+CodeCommit)

page icon as list [Integrate Gerrit with Jira Data Center](/wiki/spaces/GIJDC/pages/91979855/Gerrit)

page icon as list [Integrate Bitbucket with Jira Data Center](/wiki/spaces/GIJDC/pages/92012653/Bitbucket+Server)

page icon as list [Integrate Bonobo with Jira Data Center](/wiki/spaces/GIJDC/pages/91947111/Bonobo)

page icon as list [Integrate Tracked Folders with Jira Data Center](/wiki/spaces/GIJDC/pages/91947120/Tracked+Folders)

page icon as list [Integrate Windows Network/Server Share with Jira Data Center](/wiki/spaces/GIJDC/pages/91881564/Windows+Network+%7C+Server+Share)