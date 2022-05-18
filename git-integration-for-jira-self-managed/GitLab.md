---

title: GitLab.com
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Using **Jira Cloud**? [See the corresponding article](/wiki/spaces/GITCLOUD/pages/85622895/GitLab.com).

![](https://bigbrassband.com/confluence/images/gitlab_wm_no_bg.png)

**Integrate GitLab.com with Jira Data Center**

GitLab introduced personal access tokens (PAT) since version 8.8 and now (v10+) prefers this type of authentication for accessing the git repositories.  Service users are strongly advised to switch from using username/password to using Personal Access Tokens (PAT) for GitLab.com.



We are dropping support for Gitlab API v3. Please use **GitLab API v4** when adding new integrations for increased security.

Quickly learn how to connect GitLab.com git repositories via Git Integration for Jira app.

**What's on this page:**



* * *







## **Permissions**

GitLab can have users with different access level to a group or project. If the user's connected GitLab repositories to Jira are not accessible or commits are not showing for that user -- it's related to permission issues. This can be a per user, repository or a project level restriction.

If you encounter access permission issues, you will need to ask your Git administrator to grant you the required level of access to specific projects. If you are a Git administrator, you will need to setup a GitLab user with the minimum required permissions to view GitLab projects from Jira.

Take the following cases for example:

*   The personal access token (PAT) that the GitLab user provided doesn't have the correct permisions within GitLab to view source code for specific repositories.
*   The GitLab user doesn't have access privileges to a GitLab repository or is not a member of a group that has access to specific repositories.

We recommend creating a specific GitLab user for the integration.  This way, the GitLab user can have specific permissions to do the given tasks.

![](https://bigbrassband.com/images/bbb/gitlab-member-role-screen.png)

**For minimum access (read-only) permissions:**

1.  Set the user account profile's PAT scope to **read\_repository**.
2.  The GitLab user is set to only **read** a specific repository.  Set to **Reporter** role.

This level of access allows the user to view commits for the specific repository.



**For users who will be tasked with creating branches and merge requests:**

1.  Set the user account profile's PAT scope to **api**.
2.  The GitLab user should be set to **read/write** access for the specific repository.  Set to **Developer** role.

This level of access allows the user to create/delete branches and create merge requests.

For more information, see **[GitLab Permissions »](https://docs.gitlab.com/ee/user/permissions.html "GitLab User Documentation - Permissions")**.



## **Using Auto-Connect**

This process requires an existing GitLab.com account.  Multiple git repositories in a GitLab.com account will be connected via Git Integration for Jira app.

While instructions from GitLab works just fine, here are some specific instructions to get you up and running.

We recommend using the Auto-connect integration panel[1](/wiki/pages/resumedraft.action?draftId=91881531#GitLab.com-gitlab-logo-license) to connect multiple repositories from your GitLab.com account.

1. Go to **Manage Git Repositories** (_Dashboard_ > **Git** menu) in Jira Data Center.

2\. Click **GitLab** in the Auto-connect integration panel.

3\. GitLab.com is selected by default. Paste the personal access token in the provided field.

![](https://bigbrassband.com/docimgs/connect-to-gitlab-com-auth-screen.png)

Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed.

![](https://bigbrassband.com/images/bbb/github-integration-auto-connect-advanced.png)

*   **C**ustom API Path****  –  this is a relative path that starts with "/".  The maximum allowed length is 2000 characters or less. The integration will use the relative REST API path to retrieve the list of tracked repositories. For more information on GitLab custom API paths, see **[GitLab API](https://docs.gitlab.com/ee/api/projects.html)**. To learn more examples, see article [**Jira Data Center: Working with Custom API Path**](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path).



**GitLab version API support:**
Gitlab v9.5 and above -- only API v4
Gitlab v9.0 to v9.4.x -- API v4 (API v3 unsupported)



**Remember**
The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible.

*   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less. Read about JMESPath expressions on their [website](http://jmespath.org/). For help with writing expressions, please contact [support](mailto:support@bigbrassband.com?subject=Help%20with%20writing%20JMESPath%20filter%20expressions). To learn more examples, see article **[Jira Data Center: Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters)**.

While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

4\. Click Connect.

5\. On the following screen, the Git Integration for Jira app will read all available repositories from your GitLab account.  Click Import repositories.

Repositories of the logged-in GitLab user can be automatically connected to Jira Data Center.  Repositories that are added or removed from GitLab will be likewise connected or disconnected from Jira Data Center.

On the first connection of this integration, the first 30 repositories are displayed in the list for import.  The entire repository list can be viewed via Manage repositories > **Actions** > **Show integration repositories**.

6\. After the import process, enable/disable **_integration settings_** and set **Project Permissions** according to your organization's rules:

![](https://bigbrassband.com/images/bbb/jira-server-connect-vsts-settings-dialog.png)

*   On the Integration Settings, setting the **_Require User PAT_** option to **`ON`**, will require users to provide PAT specific for branch and merge requests _(via the **[developer panel»](https://bigbrassband.com/git-integration-for-jira/documentation/jira-developer-panel.html "Git add-on documentation - Jira developer panel")** on the Jira issue page)_.  For more information on this feature, see **[Integration Settings: Require User PAT »](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)**.
*   Set **[Smart Commits »](https://bigbrassband.com/git-integration-for-jira/documentation/smart-commits.html "(opens in new tab/window)")** and **[Repository Browser »](https://bigbrassband.com/git-integration-for-jira/documentation/repository-browser.html "(opens in new tab/window)")** to enable/disable these features.
*   Set **Project Permissions** according to your organization's project association rules.

7\. Click Finish.

The GitLab.com git repositories are now connected to Jira Data Center.

There will be a slight delay in adding 2FA-enabled repositories compared to others.  These will show in the git configuration list eventually.



## **Single Repository**

This process requires an existing GitLab git repository.  Look for the the GitLab repository URL on the repository project page. Choose between SSH or HTTPS.

![](https://bigbrassband.com/images/bbb/gitlab-repository-home.png)

Use this information to connect the GitLab git repository to your Jira Data Center via Git Integration for Jira app:

1.  On your Jira dashboard menu, go to **Git** > **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from GitLab in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Data Center. There will be a slight delay in adding 2FA-enabled repositories compared to others.  These will show in the git configuration list eventually.



## **Post-Install Tips**

We recommend to change the following setting if there are connection issues:

Go to the general settings in Git Integration app configuration page (**Git** > **Manage repositories** > **General**) then set the Git operation timeout to **120** or **180**.

![](https://bigbrassband.com/confluence/images/int-guide-gitlab-jira-server-gen-cfg.png)



## **Creating a Personal Access Token**

If two-factor authentication is enabled for your GitLab account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitLab.com account for increased security.

While instructions from GitLab works just fine, [follow this article](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens#CreatingPersonalAccessTokens-gitlab) for some specific instructions to get you started.



## **Setting Up GitLab Web Links**

The Git Integration for Jira app automatically configures web linking for GitLab git repositories.



## **Working with Branches and Merge Requests with GitLab**

This process requires a GitLab git repository and a PAT with **`api`** scope.

For GitLab Group, the user must have the **Write** permissions and the **`api`** PAT scope.

### **Default Branch**

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.



Main branch for repositories within an integration can only be changed on the git server.

### **Creating Branches**

1. On your Jira Data Center, open a Jira issue. On the Jira developer panel under **Git Source Code**, click **Create Branch**.

2\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-issue-create-branch-dialog.png)

*   Select a **Repository** from the list.

If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, **`johnsmith/second-webhook-test-repo`**.

*   Choose a **Base branch**.
*   Enter a **Branch name** or leave it as is (recommended).

If the **[Require User PAT option »](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)** is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

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

Perform a commit to the newly-created branch to be ready for merge.

### **Creating Merge Request**

The merge request feature works the same as pull request.

To create a merge request and merge it to the main source (master):

1. On your Jira Data Center, open the Jira issue where your previously created a branch.

2\. On the developer panel under **Git Source Code**, click **Create Merge Request**.

3\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-issue-merge-request-dialog.png)

*   Select a **Repository** from the list.

If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, **`johnsmith/second-webhook-test-repo`**.

*   Choose the newly-created branch as the **Source branch**.
*   Set **_master_** as the **Target branch**.
*   Enter a descriptive title or leave it as is _(recommended)_.

If the **[Require User PAT option »](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)** is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.com/images/bbb/jira-server-issue-merge-req-dlg-cfg-pat.png)

If an invalid PAT was configured for the selected repository, the merge request creation process will fail.

4\. Click Create to create the merge request.

The merge request is listed on the developer panel of the Jira issue page.

The merge request is also ready for approval by the reviewers in your GitLab web portal.



## **Viewing Git Commits in Jira Data Center**

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.



* * *

## More Integration Guides

page icon as list [Integrate GitHub.com with Jira Data Center](/wiki/spaces/GIJDC/pages/91979804/GitHub.com)

page icon as list [Integrate GitHub Enterprise with Jira Data Center](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server)

page icon as list [Integrate GitLab CE/EE with Jira Data Center](/wiki/spaces/GIJDC/pages/91947056)

page icon as list [Integrate Azure DevOps/VSTS with Jira Data Center](/wiki/spaces/GIJDC/pages/92176406)

page icon as list [Integrate Azure DevOps Server/TFS with Jira Data Center](/wiki/spaces/GIJDC/pages/91979843)

page icon as list [Integrate AWS CodeCommit with Jira Data Center](/git-integration-for-jira-self-managed/AWS-CodeCommit)

page icon as list [Integrate Gerrit with Jira Data Center](/git-integration-for-jira-self-managed/Gerrit)

page icon as list [Integrate Bitbucket with Jira Data Center](/git-integration-for-jira-self-managed/Bitbucket-Server)

page icon as list [Integrate Bonobo with Jira Data Center](/git-integration-for-jira-self-managed/Bonobo)

page icon as list [Integrate Tracked Folders with Jira Data Center](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/81002508/Tracked+Folders)

page icon as list [Integrate Windows Network/Server Share with Jira Data Center](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/81035265)

1 Logo owned by [GitLab Inc](https://gitlab.com/) used under [license](https://creativecommons.org/licenses/by-nc-sa/4.0/)