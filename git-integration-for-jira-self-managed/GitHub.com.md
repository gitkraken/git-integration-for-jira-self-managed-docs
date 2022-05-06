---

title: GitHub.com
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# GitHub.com

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/91979804/GitHub.com>

* * *

These instructions apply to instances on Free, Team, Cloud Enterprise (including [**EMU**](https://docs.github.com/en/enterprise-cloud@latest/admin/identity-and-access-management/managing-iam-with-enterprise-managed-users/about-enterprise-managed-users)) plans hosted on GitHub.com.

For instructions on self-hosted GitHub Enterprise Server, please see [this page](#).

Using **Jira Cloud**?  [See the corresponding article.](#)

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979804/image-20200928-125312.png?version=1&modificationDate=1639223800861&cacheVersion=1&api=v2&width=272&height=76)

# Integrate GitHub.com with Jira Data Center

Quickly learn how to connect GitHub.com git repositories via Git Integration for Jira Data Center app.  

**What's on this page:**

* * *

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/s26h3avwuo) _to open this video in a new browser tab for more viewing options._

## Creating a personal access token

If two-factor authentication is enabled for your GitHub account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitHub.com account for increased security.

While instructions from GitHub works just fine, [follow this article](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens) for some specific instructions to get you started.

## Using Full feature integration

This process requires an existing GitHub git repository.

We recommend using the Add new integration panel (_formerly Auto-connect integration_) to connect multiple repositories from your GitHub.com account.

This setup uses full feature integration offering functions and features not found on single repository connections.

On November 13, 2020, GitHub.com is going to stop allowing API authentication via username/password. For more information, see [**GitHub.com - Deprecating Password Authentication**](https://developer.github.com/changes/2020-02-14-deprecating-password-auth/).

We strongly recommend to use personal access tokens for GitHub.com account integration.

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.
    
2.  Click **GitHub.com** on the Add new integration panel. The Add new integration wizard dialog is displayed.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979804/gitserver-42-connect-auto-ext-service-github-com(c).png?version=1&modificationDate=1648029908462&cacheVersion=1&api=v2&width=659&height=467)
3.  **GitHub.com and GitHub Enterprise Cloud** is selected by default. Paste the personal access token in the provided box.
    
    1.  Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed.
        
        ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55378058/gitserver-general-advanced-autoconnect-opt(c).png?version=1&modificationDate=1601303104028&cacheVersion=1&api=v2)
        *   **Custom API Path**  –  this is a relative path that starts with "/". The maximum allowed length is 2000 characters or less. The integration will use the supported relative REST API path to retrieve the list of tracked repositories.  
            For more examples, see article [Working with Custom API Path - GitHub.com](#).
            
        *   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated.   The maximum allowed length is 2000 characters or less.  
            For help with writing expressions, please contact [support](mailto:support@bigbrassband.com). Read about JMESPath expressions on their **website**.  
            For some other examples, see [Working with JMESPath Filter in GitHub.com](#).
            
        *   **Fetch refspec**  –  Git refspecs contains patterns mapped as references from the remote to the local repository.  
            For more information, see [**Git Internals -- The Refspec**](https://git-scm.com/book/en/v2/Git-Internals-The-Refspec).
            
            1.  The first two refspec options are required.
                
            2.  The rest of the options are OPTIONAL:
                
                1.  **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching.  This option is enabled by default.  This affects git notes which are not shown:
                    
                    1.  ...when `refs/notes` are disabled on connecting a repository.
                        
                    2.  ...when a new note comes when `refs/notes` is disabled.
                        
                2.  Clone and index changes (refs/changes) – This is a reference to `refs/changes/*` used for fetching.  This option is turned off by default.
                    
                3.  Clone and index other refs – This is a user-defined list of references used for fetching.  It is a comma-separated list with the format:
                    
                    *   `+refs/refname1/*:refs/refname1/*, refs/refname2/*:refs/refname2/*, ...`
                        
        *   While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.
            
4.  Click **Connect**.
    
5.  On the following screen, the Git Integration for Jira app will read all available repositories from your GitHub account. Click **Import repositories**.
    
    *   Repositories of the logged-in GitHub user can be automatically connected to Jira Data Center. Repositories that are added or removed from GitHub will be likewise connected or disconnected from Jira Data Center.
        
6.  After the import process, the **Settings** screen is displayed.
    
7.  ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55378058/gitserver-github-autoconnect-settings-dlg(c).png?version=1&modificationDate=1601303105374&cacheVersion=1&api=v2)
    *   On the Integration Settings, setting the _**Require User PAT**_ option to `ON`, will require users to provide PAT specific for branch and merge requests _(via the_ [developer panel](#) _on the Jira issue page)_.   
        For more information on this feature, see [Integration Settings: Require User PAT](#).
        
    *   Set [Smart Commits](#) and [Repository Browser](#) to enable/disable these features.
        
    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Associating project permissions](#).
        
8.  Click **Finish** to complete this setup.
    

The GitHub.com repositories are now connected to Jira Data Center.

There will be a slight delay in adding 2FA-enabled repositories compared to others. These will show in the git configuration list eventually.

## Single repository (Manual integration)

This section is for users who are using SSH connections or those who wanted to only connect a single specific repository.

This process requires an existing GitHub git repository. Look for the GitHub repository URL on the repository project page.

Choose between SSH or HTTPS. Use this information to connect the GitHub git repository to your Jira Data Center via Git Integration for Jira app:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/91979804/github-repository-home-aug2020.png?version=1&modificationDate=1639223800867&cacheVersion=1&api=v2)

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.
    
2.  Click **Connect to Git Repository** (_or click the Git icon on the Add new integration panel_) to open the Connect Wizard.
    
3.  Paste the URL from GitHub in the provided box.
    
4.  Continue to the next step by following the screen instructions.
    
5.  Click **Finish** to complete this process. 
    

The repository is now connected to Jira Data Center.

## Setting up GitHub permissions

We recommend using a "service user" in GitHub _(example:_ `Git-Integration-for-Jira`_)_ to be used to integrate GitHub with the Git Integration for Jira app. This dedicated "service user" will allow the GitHub administrator to set permissions so the app clones only the desired repositories.

Assign GitHub permissions for team members or collaborators to allow which resources are accessible for service users. This feature is only available in a GitHub Organization.

### Default repository permission

1.  Login to your GitHub.com account.
    
2.  Go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Profile** ➜ **Settings**.
    
3.  On your sidebar, click **Organizations**.
    
4.  Click **Settings** for the selected organization.
    
5.  On your sidebar, click **Member Privileges**. The following screen is displayed.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55378058/github-org-repo-base-permissions(c).png?version=1&modificationDate=1601303108084&cacheVersion=1&api=v2)
6.  Under the **Base permissions**, click on the dropdown button.
    
    *   Choose the base permission level for organization members. The base repository permission only applies to organization members and not to outside collaborators. If the base permission is set to _**None**_, organization members will need to be given access to repositories using the _**Teams or Collaborators**_ methods (see below).
        
7.  **Save** the changes.
    

For more information, see [**Access Permissions on GitHub »**](https://help.github.com/articles/access-permissions-on-github/).

### Teams and collaborators

To give a member additional access, they must be added to a team or make them collaborators on individual repos.

**Set default repository permission for the current team:**

1.  Open an organization team. (_Your org ➜ Teams ➜ scroll down to the bottom then click the desired team._)
    
2.  Click the **Repositories** tab.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55378058/github-org-repo-team-repo-permissions(c).png?version=1&modificationDate=1601303109956&cacheVersion=1&api=v2)
3.  Set **Read**, **Write** or **Admin** repository access as desired.
    

**Assign members to a team on your GitHub repository:**

1.  Create a team in your GitHub Organization.
    
2.  Invite a member to add it into the team.  An email invitation is sent to that GitHub service user.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55378058/github-add-members-to-team(c).png?version=1&modificationDate=1601303110595&cacheVersion=1&api=v2)
    
    The service user is then added to the team if the invitation has been accepted.
    
3.  Click the service user to manage permissions for this member to:
    
    *   Set desired Role for this member.
        
    *   Convert this member to outside collaborator.
        
    *   Give this member access to organization repositories.
        
    *   Remove this member from the team.
        
4.  Click **Manage access** to manage repository access for this member.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55378058/github-manage-team-repo-permission(c).png?version=1&modificationDate=1601303111100&cacheVersion=1&api=v2)

**Organization permissions**  
While users have configured PAT for repository access, users in a GitHub Organization must at least have **Read** permissions. This allows them to view commits and smart commits, and browse repositories (if enabled) of connected GitHub Organization repositories inside Jira.

**GitHub Organization**  
For collaborators and commit authors, set these users to have **Write** permissions. This will allow them to view commits and smart commits, browse repositories and also enables them to create branches and pull requests to specified GitHub git repositories via developer panel of a Jira issue.

The user PAT for "Require User PAT" setting should have **Write** permission. Otherwise, the user will not be able to use it for branch or pull request creation/deletion.

For more information on organization teams, see [**GitHub: Organizing Members into Teams »**](https://help.github.com/articles/organizing-members-into-teams/).

For more information on inviting collaborators, see [**Inviting Collaborators to a Personal/Organization Repository »**](https://help.github.com/articles/inviting-collaborators-to-a-personal-repository/).

## Setting up GitHub web links

The Git Integration for Jira app automatically configures web linking for GitHub git repositories.

For single repository connections, web link setup is optional. However, git links will become available in Git Commits tab when configured.

For more information on this feature, see [Documentation: Web linking](#).

## Viewing git commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
    
2.  Open the Jira issue.
    
3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.
    
4.  Click **View Full Commit** to view the code diff.
    

For more information about this feature, see [Documentation: Viewing commit code diffs](#).

## Require User PAT settings for user access

For teams looking to maintain user attribution, Jira administrators can place a requirement where individual Jira users must provide personal access tokens to perform certain actions. This includes actions such as creating a branch or pull request in Jira using their git service account - rather than the integration account.

For more information, see [Require personal access tokens for user access](#).

If the **Require User PAT option** is enabled in the **Integration Feature Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, a text label about setting up your PAT is displayed on the create branch and create pull/merge request dialogs.

Click this text label to open the Setup PAT dialog and paste your personal access token in the provided box. Click **Update**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979804/gitserver-setup-pat-dlg.png?version=1&modificationDate=1639223800871&cacheVersion=1&api=v2&width=544&height=272)

Updating this dialog with a blank entry will remove the configured PAT for the current integration.

The Setup PAT dialog is also accessible via Repository Browser (dashboard menu Git ➜ **Repository browser**) ➜ Click the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) icon under _**Pers. Access**_ column.

## Working with branches and pull requests

This process requires a GitHub git repository and a PAT with `repo` scopes.

For GitHub Organization, the user must have the **Write** permissions and the `repo` PAT scopes.

### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the Repository Settings of the Git Integration for Jira app on the next reindex. Full integration supports this function where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

Main branch for repositories within an integration can only be changed on the git server.

### Creating branches

On your Jira Data Center, open a Jira issue. On the Jira developer panel under **Git Integration**, click **Create branch**. The following dialog is displayed.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979804/gitserver-create-branch-dlg.png?version=1&modificationDate=1639223800875&cacheVersion=1&api=v2&width=544&height=272)

**Pointers:**

1.  Select a **Repository** from the list.
    
    1.  If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.
        
    2.  Use the search box to look for the specific repository that will be used.
        
2.  Choose a **Base branch**.
    
3.  Enter a **Branch name** or leave it as is (recommended).
    

The Git Integration for Jira Data Center app gets the default branch from almost all integrations. However, the exception is with Gerrit which always has “master” as its default branch.

The newly-created branch is now listed in the developer panel under **Branches**. Perform a commit to the newly-created branch to be ready for merge.

### Creating pull requests

The pull request feature works the same as merge request. On your Jira Data Center, open the Jira issue where your previously created a branch. On the developer panel under **Git Integration**, click **Create pull request**. The following dialog is displayed.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91979804/gitserver-create-pull-req-dlg.png?version=1&modificationDate=1639223800879&cacheVersion=1&api=v2&width=544&height=282)

**Pointers:**

1.  Select a **Repository** from the list.
    
    1.  If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.
        
    2.  Use the search box to look for the specific repository that will be used.
        
2.  Choose the newly-created branch as the **Source branch**.
    
3.  Set _**master**_ as the **Target branch**.
    
4.  Enter a descriptive **Title** or leave it as is _(recommended)_.
    

**Preview** allows you to see the comparison view of the current changes in the selected **Source branch** vs **Target branch** (_usually_ _master_).

The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your GitHub web portal.

## More integration guides

*   Page:
    
    [Integration Basics](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics) (Git Integration for Jira Data Center)
    
*   Page:
    
    [GitHub.com](/wiki/spaces/GIJDC/pages/91979804/GitHub.com) (Git Integration for Jira Data Center)
    
*   Page:
    
    [GitHub Enterprise Server](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server) (Git Integration for Jira Data Center)
    
*   Page:
    
    [GitLab CE/EE](/wiki/spaces/GIJDC/pages/91947056) (Git Integration for Jira Data Center)
    
*   Page:
    
    [GitLab.com](/wiki/spaces/GIJDC/pages/91881531/GitLab.com) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Azure DevOps | Visual Studio Team Services (VSTS)](/wiki/spaces/GIJDC/pages/92176406) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Azure DevOps Server | Team Foundation Services (TFS)](/wiki/spaces/GIJDC/pages/91979843) (Git Integration for Jira Data Center)
    
*   Page:
    
    [AWS CodeCommit](/wiki/spaces/GIJDC/pages/92176493/AWS+CodeCommit) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Gerrit](/wiki/spaces/GIJDC/pages/91979855/Gerrit) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Bitbucket Server](/wiki/spaces/GIJDC/pages/92012653/Bitbucket+Server) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Bonobo](/wiki/spaces/GIJDC/pages/91947111/Bonobo) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Windows Network | Server Share](/wiki/spaces/GIJDC/pages/91881564/Windows+Network+%7C+Server+Share) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Tracked Folders](/wiki/spaces/GIJDC/pages/91947120/Tracked+Folders) (Git Integration for Jira Data Center)