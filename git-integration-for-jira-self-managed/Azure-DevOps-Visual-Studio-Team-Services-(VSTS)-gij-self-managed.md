---

title: Azure DevOps | Visual Studio Team Services (VSTS)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Using **Jira Cloud**? [See the corresponding article](/git-integration-for-jira-cloud/azure-devops-visual-studio-team-services-vsts/).

![](https://bigbrassband.atlassian.net/wiki/download/attachments/92176406/vsts-azure-devops-logo.png?version=1&modificationDate=1577430609568&cacheVersion=1&api=v2)



![](https://bigbrassband.com/confluence/images/vsts-new-logo.png)

**Integrate Azure DevOps/Visual Studio Team Services (VSTS) with Jira Data Center**



Quickly learn how to connect Azure DevOps/VSTS git repositories via Git Integration for Jira Data Center.

The Git Integration for Jira app supports Azure Repos.

* * *





## Creating Personal Access Tokens

If you have not yet generated a personal access token (PAT), create your token by following [the steps outlined in this article.](/git-integration-for-jira-self-managed/creating-personal-access-tokens/)



## Using Auto-Connect

This process requires an existing Microsoft account with Azure DevOps or VSTS **git** projects.

We recommend using the Auto-connect integration panel to connect multiple repositories from your Azure DevOps/VSTS account.

1. On the Jira Data Center dashboard menu, go to **Git** > **Manage Repositories**.

2\. The git configuration page for connecting repositories is displayed.

3\. On the Auto-connect integration panel, click **Microsoft**.

4\. On the following screen, select **Visual Studio Team Services (VSTS).**

![](https://bigbrassband.com/images/bbb/jira-server-connect-vsts-login-screen.png)

or select **Azure DevOps** from the list, if you have it instead.

*   Enter your personal access token (PAT) on the provided field.

Configuring the **Advanced** settings is optional.  However, admins/power users may set how the project listing is displayed on the following:

*   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less.
    *   If the field is empty, the Git Integration for Jira app will get all available accounts and then scans all available git repositories.

    *   If the field is not blank, the app will assume it as a single account path and will try to use it. To connect to all available accounts, manually create integrations for each one of them.

*   Read about JMESPath expressions on their [website](http://jmespath.org/). For help with writing expressions, please contact [support](mailto:support@bigbrassband.com?subject=Help%20with%20writing%20JMESPath%20filter%20expressions).
*   To learn more VSTS/Azure DevOps examples, see article **[Jira Data Center: Working with JMESPath Filters](/git-integration-for-jira-self-managed/working-with-jmespath-filters/)**.

*   Click Connect to continue.

5\. Login to your Microsoft account, if prompted.

6\. On the following dialog, Git Integration for Jira app will read all available repositories from Azure DevOps/VSTS. Click Import repositories.

Currently, all available accounts are scanned and corresponding URLs are created internally. Repositories of the logged-in Microsoft user can be automatically connected to Jira Data Center. Repositories that are added or removed from Azure DevOps/VSTS will be likewise connected or disconnected from Jira Data Center.

7\. After the import process, the **Settings** dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-connect-vsts-settings-dialog.png)

*   On the Integration Settings, setting the **_Require User PAT_** option to **`ON`**, will require users to provide PAT specific for branch and merge requests _(via the **[developer panel »](https://bigbrassband.com/git-integration-for-jira/documentation/jira-developer-panel.html "Git add-on documentation - Jira developer panel")** on the Jira issue page)_.  For more information on this feature, see **[Integration Settings: Require User PAT »](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request/)**.
*   Set **[Smart Commits »](/git-integration-for-jira-self-managed/smart-commits/ "(opens in new tab/window)")** and **[Repository Browser »](/git-integration-for-jira-self-managed/repository-browser/ "(opens in new tab/window)")** to enable/disable these features.
*   Set **Project Permissions** according to your organization's project association rules.

8\. Click Finish. For now, only **git** projects are supported from Azure DevOps/VSTS.

Azure DevOps/VSTS git repositories are now connected to Jira Data Center.



## Single Repository

![](https://bigbrassband.com/confluence/images/vsts-azure-clone-repo-page.png)

Obtain the repository URL from the Azure DevOps/VSTS repository project page.  Choose between SSH or HTTPS.

1.  On your Jira dashboard menu, go to **Git** > **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from Azure DevOps/VSTS web portal in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Data Center.



**Webhooks fail with DefaultCollection in URL Path**

To fix webhooks for old VSTS/Azure repository connections with _DefaultCollection_ in the URL path, update the **_Repository origin_** field in the Manage git repositories page > **Actions** > **Edit repository settings** with the repository URL currently being returned by Azure.

## Permissions

Set Azure DevOps/VSTS repository permissions according to your organization's rules. Viewing commits from Jira requires the user to have at least **Read** or **View** permissions. For branch/pull request creation, set specific service users with **Write** permissions.



## Webhooks and Web Linking

The Git Integration for Jira app automatically configures web linking for Azure DevOps/VSTS git repositories.



**Webhooks are supported on Azure DevOps/VSTS.**

First - configure webhooks in the Git Integration app in Jira via the **Git** menu > **Manage Git Repositories** then click **Webhooks**.  Enable the feature and save the settings.  Then [follow these instructions](https://docs.microsoft.com/en-us/azure/devops/service-hooks/services/webhooks?view=vsts "Opens in new tab/window") to setup the webhook trigger. Azure DevOps/VSTS webhooks will trigger an immediate index of all repositories within the integration.

For detailed step-by-step guide showcasing the webhooks setup, [see this article](/git-integration-for-jira-self-managed/adding-webhooks-for-azure-devops-repos-vsts/).



## Linking Azure DevOps/VSTS Git Commits to Jira Data Center

This process requires a Azure DevOps/VSTS git repository.

1. On your web browser, login to your Azure DevOps/VSTS account then go to your working repository.

2\. Clone this repository into your Visual Studio IDE.

![](https://bigbrassband.com/images/bbb/vsts-webui-get-clone-url.png)

... or update your local repository files by performing a **Pull** action via VS IDE > **Team Explorer**.

![](https://bigbrassband.com/images/bbb/vside-teamexp-sync-changes-pull.png)

3\. Create or modify a file from your local repository.

4\. Perform a commit of the changes via **Team Explorer** \> **Changes**.

![](https://bigbrassband.com/images/bbb/vs-ide-team-explorer-changes-commit-push.png)

*   Enter the commit message by mentioning the Jira issue key to associate this commit to. _(Underlined in red)_.
*   Click the dropdown on the Commit All button then select Commit All and Push.

5\. The commit is now displayed in the specified Jira issue.

![](https://bigbrassband.com/images/bbb/jira-server-vsts-repo-view-commit.png)



## Viewing Git Commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.



## Working with Branches and Pull Requests with Azure DevOps/VSTS

This process requires a Azure DevOps/VSTS git repository and a PAT with at least **`Code (read and write)`** scope.

### Default Branches

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.



Main branch for repositories within an integration can only be changed on the git server.

### Creating Branches

1. On your Jira Data Center, open a Jira issue. On the Jira developer panel under **Git Source Code**, click **Create Branch**.

2\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-issue-create-branch-dialog.png)

*   Select a **Repository** from the list.
*   Choose a **Base branch**.
*   Enter a **Branch name** or leave it as is (recommended).

If the **[Require User PAT option](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request/)** is enabled in the **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.com/images/bbb/jira-server-vsts-branch-pat-conf-dlg.png)

*   Click the link label to setup the PAT.  This will show the Repository Browser listing connected git repositories.

![](https://bigbrassband.com/images/bbb/jira-server-sel-repo-enter-user-pat.png)

*   Click 
     to setup a PAT for the selected repository. Paste a valid PAT of the current user to proceed. Invalid PATs will fail the branch creation process.

*   Click the 
    icon to use this PAT and save it to the current user profile. Otherwise, click the 
    icon on the right to cancel setting up PAT for this repository.

*   After the above steps have been taken, the users will be able to proceed with branch creation.

3\. Click Create Branch.  The newly-created branch is now listed in the developer panel under **Branches**.

4\. On your VS IDE, go to **Team Explorer** and perform a **Pull** action.  This will update your local repository with a new branch list.

5\. Go to **Team Explorer** \> **Branches**.

6\. Under **Active Repositories**, expand the **remote/origin** folder view.

7\. Right click the new branch then select **Checkout**.  The new branch will be listed in the active repositories list.

8\. Make changes to a file to prepare it for commit and branch merge.

9\. On the Team Explorer, click **Changes**.

![](https://bigbrassband.com/images/bbb/vs-ide-teamexp-branch-commit-push.png)

*   Make sure that **Branch:** displays the name of the newly-created branch.  If not, select it again from the list.
*   Add the Jira issue key to the commit message. _(Underlined in red)_.
This will associate the commit to the mentioned Jira issue key.*   Click the dropdown on the Commit All button then select Commit All and Push.

The commit is pushed to the new branch and is now ready for merge..

### Creating Pull Requests

The pull request feature works the same as merge request.

To create a pull request and merge it to the main source (master):

1. On your Jira Data Center, open the Jira issue where your previously created a branch.

2\. On the developer panel under **Git Source Code**, click **Create Pull Request**.

3\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-issue-create-pull-request-dialog.png)

*   Select a **Repository** from the list.
*   Choose the newly-created branch as the **Source branch**.
*   Set **_master_** as the **Target branch**.
*   Enter a descriptive title or leave it as is _(recommended)_.

If the **[Require User PAT option](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request/)** is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.com/images/bbb/jira-server-issue-create-pull-req-dlg-cfg-pat.png)

If an invalid PAT was configured for the selected repository, the pull request creation process will fail.

4\. Click Create to create the pull request.

The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your Azure DevOps/VSTS web portal.

![](https://bigbrassband.com/images/bbb/vsts-webui-branch-ready-for-merge.png)

### Merging Branch to master

Continuing from the above steps, the current branch is ready for merge.

1\. On the Team Explorer, update your local repository by performing a **Pull** action.

2\. Go to **Pull Requests**.

The pending pull request items are displayed here. Pull requests requires the approval of the reviewers before it can be merged from the VS IDE.

![](https://bigbrassband.com/images/bbb/vs-ide-teamexp-pull-request-approved.png)

3\. Go to **Branches**.  Click **Merge**.

4\. The following screen is displayed:

![](https://bigbrassband.com/images/bbb/vs-ide-team-explorer-branch-merge-2017.png)

*   Set the source to the branch to which you pushed the commits.
*   Set the target branch to **_master_**.

5\. Click Merge to continue.

The reviewer's approval is required to completely merge the pull request.  This usually takes place in the Azure DevOps/VSTS portal where your updated code is being reviewed.

![](https://bigbrassband.com/images/bbb/vsts-webui-pull-request-review-approve.png)

Once approved, the team leader or reviewer can then complete the merge.  The commit can be viewed in the associated Jira issue page.

![](https://bigbrassband.com/images/bbb/jira-server-issue-page-git-commits-tab-view.png)


