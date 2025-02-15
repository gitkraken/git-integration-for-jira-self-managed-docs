---

title: GitLab.com
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <b>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/gitlab-com-gij-cloud'>See the corresponding article</a>.
    </div>
    </div>
</div>

&nbsp;

![](/wp-content/uploads/gitlab-mobile-custom1.png)

&nbsp;

## Integrate GitLab.com with Jira Data Center/Server

GitLab introduced personal access tokens (PAT) since version 8.8 and now (v10+) prefers this type of authentication for accessing the git repositories. Service users are strongly advised to switch from using username/password to using Personal Access Tokens (PAT) for GitLab.com.

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>GitLab API</b><br>
        Support for Gitlab API v3 is deprecated. We recommend to use <b>GitLab API v4</b> when adding new integrations for increased security.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>GitLab legacy support</b><br>
        Starting v4.19+, we will be dropping support for GitLab legacy integrations.<br>        
    </div>
    </div>
</div>

&nbsp;

Quickly learn how to connect GitLab.com git repositories via Git Integration for Jira app.

**What's on this page:**
- [Integrate GitLab.com with Jira Data Center/Server](#integrate-gitlabcom-with-jira-data-centerserver)
  - [Permissions](#permissions)
  - [Creating a personal access token](#creating-a-personal-access-token)
    - [Group access tokens](#group-access-tokens)
  - [Using Full feature integration](#using-full-feature-integration)
  - [Single repository (Manual integration)](#single-repository-manual-integration)
  - [Setting up GitLab web links](#setting-up-gitlab-web-links)
  - [Viewing git commits in Jira Server](#viewing-git-commits-in-jira-server)
  - [Working with branches and merge requests](#working-with-branches-and-merge-requests)
    - [Default branch](#default-branch)
    - [Creating branches](#creating-branches)
    - [Merge request](#merge-request)
  - [More Integration Guides](#more-integration-guides)
  
&nbsp;
* * *
&nbsp;

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/eqwv6puk4k?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/eqwv6puk4k'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

### Permissions

GitLab can have users with different access level to a group or project. If the user's connected GitLab repositories to Jira are not accessible or commits are not showing for that user -- it's related to permission issues. This can be a per user, repository or a project level restriction.

If you encounter access permission issues, you will need to ask your Git administrator to grant you the required level of access to specific projects. If you are a Git administrator, you will need to setup a GitLab user with the minimum required permissions to view GitLab projects from Jira.

Take the following cases for example:

*   The personal access token (PAT) that the GitLab user provided doesn't have the correct permissions within GitLab to view source code for specific repositories.

*   The GitLab user doesn't have access privileges to a GitLab repository or is not a member of a group that has access to specific repositories.


We recommend creating a specific GitLab user for the integration. This way, the GitLab user can have specific permissions to do the given tasks.

![](/wp-content/uploads/gij-gitlab-user-permissions-or-repository-permissions.png)

&nbsp;

**For minimum access (read-only) permissions:**

1.  Set the user account profile's PAT scope to **read\_repository**.

2.  The GitLab user is set to only **read** a specific repository. Set to **Reporter** role.

This level of access allows the user to view commits for the specific repository.

&nbsp;

**For users who will be tasked with creating branches and merge requests:**

1.  Set the user account profile's PAT scope to **api**.

2.  The GitLab user should be set to **read/write** access for the specific repository. Set to **Developer** role.


This level of access allows the user to create/delete branches and create merge requests.

For more information, see [**GitLab Permissions »**](https://docs.gitlab.com/ee/user/permissions.html).

&nbsp;

### Creating a personal access token

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If two-factor authentication is enabled for your GitLab account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitLab.com account for increased security.
    </div>
    </div>
</div>

While instructions from GitLab works just fine, [follow this article](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed#gitlab--gitlab-ceee) for some specific instructions to get you started.

#### Group access tokens

The Git Integration for Jira app natively supports group access tokens (GAT), allowing users to connect GitLab group repositories. This feature was introduced in GitLab version 14.7 and is available exclusively for self-managed instances with a Premium license tier or higher.

&nbsp;

### Using Full feature integration

This process requires an existing GitLab.com account.

We recommend using the Add new integration panel to connect multiple repositories from your GitLab.com account. This setup uses full feature integration offering functions and features not found on single repository connections.

1.  On the Jira Server dashboard menu, go to Git ➜ **Manage repositories**.

2.  The git configuration page for connecting repositories is displayed.

3.  On the Add new integration panel, click **GitLab**^1^. The following screen is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitlab-autoconnect-dlg-c.png)

    -  **GitLab.com** is selected by default. Paste the personal access token in the provided box.

        Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed.

        ![](/wp-content/uploads/gij-gitserver-general-advanced-autoconnect-opt-c.png)

        *   **Custom API Path**  –  his is a relative path that starts with "/". The maximum allowed length is 2000 characters or less. The integration will use the relative REST API path to retrieve the list of tracked repositories.

            For more information on GitLab custom API paths, see **GitLab API**.
            For more GitLab.com examples, see article [Working with Custom API Path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed#gitlab--gitlab-ceee).

            ```bash
            GitLab version API support:
            ---------------------------
            Gitlab v9.5 and above -- only API v4
            Gitlab v9.0 to v9.4.x -- API v4 (support for API v3 is deprecated)
            ```

            <img src='/wp-content/uploads/bbb-info-20.png' /> <b>Remember:</b> The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible.

        *   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less. Read about JMESPath expressions on their [website](http://jmespath.org/). For help with writing expressions, please contact [support](mailto:gijsupport@gitkraken.com).

            To learn more examples, see article [Working with JMESPath Filters](/git-integration-for-jira-data-center/gitLab-gitLab-ce-ee-jmespath-filter-examples-gij-self-managed).

        *   **Fetch refspec**  –  Git refspecs contains patterns mapped as references from the remote to the local repository.
            For more information, see **Git Internals -- The Refspec**.

            -  The first two refspec options are required.

            -  The rest of the options are OPTIONAL:

                -  **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching. This option is enabled by default. This affects git notes which are not shown:

                    -  ...when `refs/notes` are disabled on connecting a repository.

                    -  ...when a new note comes when `refs/notes` is disabled.

                -  **Clone and index changes (refs/changes)** – This is a reference to `refs/changes/*` used for fetching. This option is turned off by default.

                -  **Clone and index other refs** – This is a user-defined list of references used for fetching. It is a comma-separated list with the format:

                    -   `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

    <br>While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

4.  Click **Connect**. On the following screen, the Git Integration for Jira app will read all available repositories from your GitLab account. 

5.  Click **Import repositories**.
    Repositories of the logged-in GitLab user can be automatically connected to Jira Server. Repositories that are added or removed from GitLab will be likewise connected or disconnected from Jira Server.

    On the first connection of this integration, the first 30 repositories are displayed in the list for import. The entire repository list can be viewed via Manage repositories page ➜ ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Show integration repositories**.

6.  After the import process, the following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-auto-connect-wiz-settings-screen-c.png)

    *   On the Integration Settings, setting the _**Require User PAT**_ option to `ON`, will require users to provide PAT specific for branch and merge requests _(via the developer panel on the Jira issue page)_. For more information on this feature, see [Integration Settings: Require User PAT](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).

    *   Set **Smart Commits** and **Repository Browser** to enable/disable these features.

    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed).

7.  Click **Finish** to complete this setup.


The GitLab.com git repositories are now connected to Jira Server.

There will be a slight delay in adding 2FA-enabled repositories compared to others. These will show in the git configuration list eventually.

&nbsp;

### Single repository (Manual integration)

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

This process requires an existing GitLab git repository. Look for the GitLab repository URL on the repository project page.

Choose between SSH or HTTPS. Use this information to connect the GitLab git repository to your Jira server via Git Integration for Jira app:

![](/wp-content/uploads/gij-gitserver-gitlab-clone-home-repo-url.png)

Use this information to connect the GitLab git repository to your Jira server via Git Integration for Jira app:

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** (_or the Git icon on the Add new integration panel_) to open the Connect Wizard.

3.  Paste the URL from GitLab in the provided box.

4.  Continue to the next step by following the screen instructions.

5.  Click **Finish** to complete this process. 


The repository is now connected to Jira Server. There will be a slight delay in adding 2FA-enabled repositories compared to others. These will show in the git configuration list eventually.

&nbsp;

### Setting up GitLab web links

The Git Integration for Jira app automatically configures web linking for GitLab CE/EE git repositories.

For single repository connections, web link setup is optional. However, git links will become available in Git Commits tab when configured.

For more information on this feature, see [Documentation: Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed).

&nbsp;

### Viewing git commits in Jira Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.


For more information about this feature, see [Documentation: Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed).

&nbsp;

### Working with branches and merge requests

This process requires a GitLab git repository and a PAT with `api` scope.

For GitLab Group, the user must have the **Write** permissions and the `api` PAT scope.

#### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the Repository Settings of the Git Integration for Jira app on the next reindex. Full feature integrations support this function where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

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

&nbsp;

#### Creating branches

On your Jira Server, open a Jira issue.

1.  On the [Jira developer panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed) under **Git integration**, click **Create branch**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitlab-create-branch-dlg.png)

    -  Select a **Repository** from the list.
        If there are several repositories with the same name, the listed GitLab CE/EE repositories will have their names attached with a GitLab owner name. For example, `johnsmith/second-webhook-test-repo`.

    -  Choose a **Base branch**.

    -  Enter a **Branch name** or leave it as is (recommended).

    -  If the [Require User PAT option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

        ![](/wp-content/uploads/gij-gitserver-gitlab-create-branch-dlg-req-userpat.png)

    -  Click the link label to setup the PAT. The following dialog appears.

        ![](/wp-content/uploads/gij-gitserver-setup-pat-dlg-c.png)

        *   Enter your personal access token from your GitLab profile settings.

        *   When you click **Update** to save the settings:

            *   If this field is blank and no PAT is provided, nothing is changed and saved.

            *   If PAT has been previously configured and this field is blank, the PAT will be discarded.

            *   If a PAT has changed since last configuration and is provided, the new PAT is used.

        *   PAT settings can be accessed via Repository browser ➜ **Pers. access** column.

            ![](/wp-content/uploads/gij-gitserver-repo-browser-pat-sel-c.png)

        *   Click the **Edit** ![](/wp-content/uploads/gij-edit-icon-dark.png) icon to setup/reconfigure PAT. The checkmark adjacent to the edit icon indicates PAT has been configured.

2.  Click **Create branch**. The newly-created branch is now listed in the developer panel under **Branches**.


Perform a commit to the newly-created branch to be ready for merge.

&nbsp;

#### Merge request

The merge request feature works the same as pull request.

To create a merge request and merge it to the main source (master):

1.  On your Jira Server, open the Jira issue where your previously created a branch.

2.  On the developer panel under **Git integration**, click **Create merge request**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitlab-create-merge-request-dlg.png)

    *   Select a **Repository** from the list.
        If there are several repositories with the same name, the listed GitLab CE/EE repositories will have their names attached with a GitLab owner name. For example, `johnsmith/second-webhook-test-repo`.

    *   Choose the newly-created branch as the **Source branch**.

    *   Set _**master**_ as the **Target branch**.

    *   Enter a descriptive title or leave it as is _(recommended)_.

    *   If the [Require User PAT option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead.

        ![](/wp-content/uploads/gij-gitserver-gitlab-create-merge-request-dlg-req-userpat.png)

        *   If an invalid PAT was configured for the selected repository, the merge request creation process will fail.

3.  Click **Create** to create the merge request.


The merge request is listed on the developer panel of the Jira issue page.

The merge request is also ready for approval by the reviewers in your GitLab web portal.

&nbsp;

### More Integration Guides

[GitHub.com](/git-integration-for-jira-data-center/gitHub-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub Enterprise Server](/git-integration-for-jira-data-center/gitHub-Enterprise-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed) (Git Integration for Jira Data Center/Server)

**GitLab.com** (this page)

[GitLab CE/EE](/git-integration-for-jira-data-center/gitLab-com-CE-EE-gijsm-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Azure DevOps | Visual Studio Team Services (VSTS)](/git-integration-for-jira-data-center/azure-DevOps-Visual-Studio-Team-Services-(VSTS)-gij-self-managed) (Git Integration for Data Center/Jira Server)

[Azure DevOps Server | Team Foundation Services (TFS)](/git-integration-for-jira-data-center/azure-DevOps-Server-Team-Foundation-Services-(TFS)-gij-self-managed) (Git Integration for Jira Data Center/Server)

[AWS CodeCommit](/git-integration-for-jira-data-center/aws-codecommit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Gerrit](/git-integration-for-jira-data-center/gerrit-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bitbucket Server](/git-integration-for-jira-data-center/Bitbucket-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Bonobo](/git-integration-for-jira-data-center/bonobo-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Windows Network | Server Share](/git-integration-for-jira-data-center/windows-Network-Server-Share-gij-self-managed) (Git Integration for Jira Data Center/Server)

[Tracked Folders](/git-integration-for-jira-data-center/tracked-Folders-gij-self-managed) (Git Integration for Jira Data Center/Server)

[**Back to:** Integration basics](/git-integration-for-jira-data-center/Integration-Basics-gij-self-managed) (Git Integration for Jira Data Center/Server)

<br>
<br>
<br>
<br>
<div style='border-top: 1px solid #456; width: 40%; padding-bottom: 12px'></div>
<div style='font-size: 12px;'>
    <sup>1</sup> <i>Logo owned by <a href='https://gitlab.com/'>GitLab Inc</a> used under <a href='https://creativecommons.org/licenses/by-nc-sa/4.0/'>license</a>.
    <p>&nbsp;&nbsp;All product names, logos, and brands are property of their respective owners.</p></i>
</div>

