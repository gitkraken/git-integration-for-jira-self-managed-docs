---

title: GitHub.com
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
      These instructions apply to instances on Free, Team, Cloud Enterprise (including <a href="https://docs.github.com/en/enterprise-cloud@latest/admin/managing-iam/understanding-iam-for-enterprises/about-enterprise-managed-users" target="_blank"><b>EMU</b></a>) plans hosted on GitHub.com.
    </div>
  </div>
</div>

<div class="bbb-callout bbb--info">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      For instructions on self-hosted GitHub Enterprise Server, please see <a href="/git-integration-for-jira-data-center/github-enterprise-server-gij-self-managed">this page</a>.
    </div>
  </div>
</div>

<div class="bbb-callout bbb--info">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      Using <b>Jira Cloud</b>?  <a href="/git-integration-for-jira-cloud/github-com-gij-cloud">See the corresponding article</a>.
    </div>
  </div>
</div>

&nbsp;

![](/wp-content/uploads/gij-github-mobile-logo-dark.png)

&nbsp;

## Integrate GitHub.com with Jira Data Center/Server

Quickly learn how to connect GitHub.com git repositories via Git Integration for Jira Data Center app.

**What's on this page:**
- [Integrate GitHub.com with Jira Data Center/Server](#integrate-githubcom-with-jira-data-centerserver)
  - [Creating a personal access token](#creating-a-personal-access-token)
  - [Setting up GitHub permissions](#setting-up-github-permissions)
    - [Default repository permission](#default-repository-permission)
    - [Teams and collaborators](#teams-and-collaborators)
  - [Using Full feature integration](#using-full-feature-integration)
  - [Single repository (Manual integration)](#single-repository-manual-integration)
  - [Setting up GitHub web links](#setting-up-github-web-links)
  - [Viewing git commits in Jira Data Center](#viewing-git-commits-in-jira-data-center)
  - [Require User PAT settings for user access](#require-user-pat-settings-for-user-access)
  - [Working with branches and pull requests](#working-with-branches-and-pull-requests)
    - [Default branch](#default-branch)
    - [Creating branches](#creating-branches)
    - [Creating pull requests](#creating-pull-requests)
  - [How to enable GetRepositories log response from GitHub to the Jira log?](#how-to-enable-getrepositories-log-response-from-github-to-the-jira-log)
  - [More Integration Guides](#more-integration-guides)

&nbsp;
* * *
&nbsp;

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/s26h3avwuo?seo=false' frameborder='0' allowfullscreen></iframe>
</div>

<div align="center" style='margin-top:15px;margin-bottom:35px'>
  <i>Watch the video guide by clicking <a href="https://bigbrassband.wistia.com/medias/s26h3avwuo" target="_blank"><b>here</b></a> to open this video in a <br>new browser tab for more viewing options.</i>
</div>

&nbsp;

### Creating a personal access token

<div class="bbb-callout bbb--alert">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      If two-factor authentication is enabled for your GitHub account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitHub.com account for increased security.
    </div>
  </div>
</div>

While instructions from GitHub works just fine, [follow this article](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed#github--github-enterprise) for some specific instructions to get you started.

<b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.27+</b><br>
There will be two new options now available in the GIJ General Settings. Enabling these settings requires an "extended" scope for your PATs.

![](/wp-content/uploads/gij-datacenter-git-pull-merge-req-group-gencfg-sel.png)

To utilize the new GitHub share PR events, we recommend that users must update their personal access token to have the following scopes:
* `read:discussion`
* `read:org`
* `read:user`
* `repo` (all)
* `user:email`

&nbsp;

### Setting up GitHub permissions

We recommend using a "service user" in GitHub (_example: `Git-Integration-for-Jira`_) to be used to integrate GitHub with the Git Integration for Jira app. This dedicated "service user" will allow the GitHub administrator to set permissions so the app clones only the desired repositories.

Assign GitHub permissions for team members or collaborators to allow which resources are accessible for service users. This feature is only available in a GitHub Organization.

&nbsp;

#### Default repository permission

1.  Login to your GitHub.com account.

2.  Go to <img style='margin: 0 3px;' src='/wp-content/uploads/gij-profile-icon.png' alt='' /> **Profile** ➜ **Settings**.

3.  On your sidebar, click **Organizations**.

4.  Click **Settings** for the selected organization.

5.  On your sidebar, click **Member Privileges**. The following screen is displayed.

    ![](/wp-content/uploads/gij-github-org-repo-base-permissions-dark-c.png)

6.  Under the **Base permissions**, click on the dropdown button.

    Choose the base permission level for organization members. The base repository permission only applies to organization members and not to outside collaborators. If the base permission is set to _**None**_, organization members will need to be given access to repositories using the _**Teams or Collaborators**_ methods (see below).

7.  **Save** the changes.

For more information, see [**Access Permissions on GitHub »**](https://help.github.com/articles/access-permissions-on-github/).

&nbsp;

#### Teams and collaborators

To give a member additional access, they must be added to a team or make them collaborators on individual repos.

<br>

**Set default repository permission for the current team:**

1.  Open an organization team. (_Your org ➜ Teams ➜ scroll down to the bottom then click the desired team._)

2.  Click the **Repositories** tab.

    ![](/wp-content/uploads/gij-github-org-repo-team-repo-permissions-dark-c.png)

3.  Set **Read**, **Write** or **Admin** repository access as desired.

<br>

**Assign members to a team on your GitHub repository:**

1.  Create a team in your GitHub Organization.

2.  Invite a member to add it into the team.  An email invitation is sent to that GitHub service user.

    ![](/wp-content/uploads/gij-github-add-members-to-team-c.png)

    The service user is then added to the team if the invitation has been accepted.

3.  Click the service user to manage permissions for this member to:

    *   set the desired **Role** for this member.
    *   convert this member to outside collaborator.
    *   give this member access to organization repositories.
    *   remove this member from the team.

4.  Click **Manage access** to manage repository access for this member.

    ![](/wp-content/uploads/gij-github-manage-team-repo-permission-c.png)

<div class="bbb-callout bbb--info">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      <b>Organization permissions</b><br>
      While users have configured PAT for repository access, users in a GitHub Organization must at least have <b>Read</b> permissions. This allows them to view commits and smart commits, and browse repositories (if enabled) of connected GitHub Organization repositories inside Jira.
    </div>
  </div>
</div>

<div class="bbb-callout bbb--info">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      <b>GitHub Organization</b><br>
      For collaborators and commit authors, set these users to have <b>Write</b> permissions. This will allow them to view commits and smart commits, browse repositories and also enables them to create branches and pull requests to specified GitHub git repositories via developer panel of a Jira issue.
    </div>
  </div>
</div>

For more information on organization teams, see [**GitHub: Organizing Members into Teams »**](https://help.github.com/articles/organizing-members-into-teams/).

For more information on inviting collaborators, see [**Inviting Collaborators to a Personal/Organization Repository »**](https://help.github.com/articles/inviting-collaborators-to-a-personal-repository/).

&nbsp;

### Using Full feature integration

This process requires an existing GitHub git repository.

We recommend using the Add new integration panel (_formerly Auto-connect integration_) to connect multiple repositories from your GitHub.com account.

This setup uses full feature integration offering functions and features not found on single repository connections.

&nbsp;

<div class="bbb-callout bbb--error">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      On November 13, 2020, GitHub.com is going to stop allowing API authentication via username/password. For more information, see <a href="https://developer.github.com/changes/2020-02-14-deprecating-password-auth/" title="Opens this link in a new tab" target="_blank">GitHub.com - Deprecating Password Authentication</a>.
    </div>
  </div>
</div>

We strongly recommend to use personal access tokens for GitHub.com account integration.

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

2.  Click **GitHub.com** on the Add new integration panel. The Add new integration wizard dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-connect-auto-ext-service-github-com-c.png)

3.  **GitHub.com and GitHub Enterprise Cloud** is selected by default. Paste the personal access token in the provided box.

    -  Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed.

        ![](/wp-content/uploads/gij-gitserver-general-advanced-autoconnect-opt-c.png)

        -  **Custom API Path**  –  this is a relative path that starts with "/". The maximum allowed length is 2000 characters or less. The integration will use the supported relative REST API path to retrieve the list of tracked repositories.

            For more examples, see article [Working with Custom API Path - GitHub.com](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed#githubcom-and-github-enterprise-examples).

        -  **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated.   The maximum allowed length is 2000 characters or less.

            For help with writing expressions, please contact [support](mailto:gijsupport@gitkraken.com). Read about JMESPath expressions on their **website**.

            For some other examples, see [Working with JMESPath Filter in GitHub.com](/git-integration-for-jira-data-center/gitHub-gitHub-enterprise-jmespath-filter-examples-gij-self-managed).

        -  **Fetch refspec**  –  Git refspecs contains patterns mapped as references from the remote to the local repository.
            For more information, see [**Git Internals -- The Refspec**](https://git-scm.com/book/en/v2/Git-Internals-The-Refspec).

            -  The first two refspec options are required.

            -  The rest of the options are OPTIONAL:

                -  **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching.  This option is enabled by default.  This affects git notes which are not shown:

                    - ...when `refs/notes` are disabled on connecting a repository.

                    - ...when a new note comes when `refs/notes` is disabled.

                -  **Clone and index changes (refs/changes)** – This is a reference to `refs/changes/*` used for fetching.  This option is turned off by default.

                -  **Clone and index other refs** – This is a user-defined list of references used for fetching.  It is a comma-separated list with the format:

                    - `+refs/refname1/*:refs/refname1/*, refs/refname2/*:refs/refname2/*, ...`

    While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

4.  Click **Connect**.

5.  On the following screen, the Git Integration for Jira app will read all available repositories from your GitHub account. Click **Import repositories**.

    Repositories of the logged-in GitHub user can be automatically connected to Jira Data Center. Repositories that are added or removed from GitHub will be likewise connected or disconnected from Jira Data Center.

6.  After the import process, the **Settings** screen is displayed.

    ![](/wp-content/uploads/gij-gitserver-github-autoconnect-settings-dlg-c.png)

    *   On the Integration Settings, setting the _**Require User PAT**_ option to `ON`, will require users to provide PAT specific for branch and merge requests _(via the_ [developer panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed) _on the Jira issue page)_.

        <div class="bbb-callout bbb--alert">
          <div class="irow">
            <div class="ilogobox">
              <span class="logoimg"></span>
            </div>
            <div class="imsgbox">
              <b>Personal access token</b><br>
              The user PAT for "Require User PAT" setting should have <b>Write</b> permission. Otherwise, the user will not be able to use it for branch or pull request creation/deletion.
            </div>
          </div>
        </div>

        For more information on this feature, see [Integration Settings: Require User PAT](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).

    *   Set **Smart Commits** and **Repository Browser** to enable/disable these features.

    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed).

7.  Click **Finish** to complete this setup.

The GitHub.com repositories are now connected to Jira Data Center.

There will be a slight delay in adding 2FA-enabled repositories compared to others. These will show in the git configuration list eventually.

&nbsp;

### Single repository (Manual integration)

<div class="bbb-callout bbb--alert">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      This section is for users who are using SSH connections or those who wanted to only connect a single specific repository.
    </div>
  </div>
</div>

This process requires an existing GitHub git repository. Look for the GitHub repository URL on the repository project page.

Choose between SSH or HTTPS. Use this information to connect the GitHub git repository to your Jira Data Center via Git Integration for Jira app:

![](/wp-content/uploads/gij-github-repository-home-dark.png)

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** (_or click the Git icon on the Add new integration panel_) to open the Connect Wizard.

3.  Paste the URL from GitHub in the provided box.

4.  Continue to the next step by following the screen instructions.

5.  Click **Finish** to complete this process.

The repository is now connected to Jira Data Center.


### Setting up GitHub web links

The Git Integration for Jira app automatically configures web linking for GitHub git repositories.

For single repository connections, web link setup is optional. However, git links will become available in Git Commits tab when configured.

For more information on this feature, see [Documentation: Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed).

&nbsp;

### Viewing git commits in Jira Data Center

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.

For more information about this feature, see [Documentation: Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed).

&nbsp;

### Require User PAT settings for user access

For teams looking to maintain user attribution, Jira administrators can place a requirement where individual Jira users must provide personal access tokens to perform certain actions. This includes actions such as creating a branch or pull request in Jira using their git service account - rather than the integration account.

For more information, see [Require personal access tokens for user access](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).

If the **Require User PAT option** is enabled in the **Integration Feature Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, a text label about setting up your PAT is displayed on the create branch and create pull/merge request dialogs.

Click this text label to open the Setup PAT dialog and paste your personal access token in the provided box. Click **Update**.

<img src='/wp-content/uploads/gij-gitserver-setup-pat-dlg.png' style='display:block;margin:25px auto;max-width:100%;' alt='Setup PAT dialog' width=602 height=302 />

<div class="bbb-callout bbb--alert">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      Updating this dialog with a blank entry will remove the configured PAT for the current integration.
    </div>
  </div>
</div>

The Setup PAT dialog is also accessible via Repository Browser (dashboard menu Git ➜ **Repository browser**) ➜ Click the &nbsp;![](/wp-content/uploads/gij-edit-icon-dark.png) icon under _**Pers. Access**_ column.

&nbsp;

### Working with branches and pull requests

This process requires a GitHub git repository and a PAT with `repo` scopes.

For GitHub Organization, the user must have the **Write** permissions and the `repo` PAT scopes.

&nbsp;

#### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the Repository Settings of the Git Integration for Jira app on the next reindex. Full integration supports this function where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

<div class="bbb-callout bbb--info">
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

On your Jira Data Center, open a Jira issue. On the Jira developer panel under **Git Integration**, click **Create branch**. The following dialog is displayed.

<img src='/wp-content/uploads/gij-gitserver-create-branch-dlg.png' style='display:block;margin:25px auto;max-width:100%' width=602 height=302 />

**Pointers:**

1.  Select a **Repository** from the list.

    If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.

2.  Use the search box to look for the specific repository that will be used.

3.  Choose a **Base branch**.

4.  Enter a **Branch name** or leave it as is (recommended).

<div class="bbb-callout bbb--info">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      The Git Integration for Jira Data Center app gets the default branch from almost all integrations. However, the exception is with Gerrit which always has 'master' as its default branch.
    </div>
  </div>
</div>

The newly-created branch is now listed in the developer panel under **Branches**. Perform a commit to the newly-created branch to be ready for merge.

&nbsp;

#### Creating pull requests

The pull request feature works the same as merge request. On your Jira Data Center, open the Jira issue where your previously created a branch. On the developer panel under **Git Integration**, click **Create pull request**. The following dialog is displayed.

<img src='/wp-content/uploads/gij-gitserver-create-pull-req-dlg.png' width=602 height=313 style='display:block;margin:25px auto;max-width:100%' />

**Pointers:**

1.  Select a **Repository** from the list.

    If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.

2.  Use the search box to look for the specific repository that will be used.

3.  Choose the newly-created branch as the **Source branch**.

4.  Set _**master**_ as the **Target branch**.

5.  Enter a descriptive **Title** or leave it as is _(recommended)_.

<div class="bbb-callout bbb--tip">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      <b>Preview</b> allows you to see the comparison view of the current changes in the selected <b>Source branch</b> vs <b>Target branch</b> (<i>usually master</i>).
    </div>
  </div>
</div>

The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your GitHub web portal.

&nbsp;

### How to enable GetRepositories log response from GitHub to the Jira log?

1.  Open ![](/wp-content/uploads/actions-icon.png) Jira System Administration then click **Logging and profiling** on the left sidebar.

2.  Under the Default loggers section, click **Configure….**

3.  Set the Package name to `com.bigbrassband.jira.git.services.integration`.

4.  Set Logging Level to **DEBUG**.

5.  Click **Add** to proceed.

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b> Remember to turn this setting off after you have obtained the log file for analysis.

&nbsp;

### More Integration Guides

**GitHub.com** (this page)

[GitHub Enterprise Server](/git-integration-for-jira-data-center/gitHub-Enterprise-Server-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed) (Git Integration for Jira Data Center/Server)

[GitLab.com](/git-integration-for-jira-data-center/gitLab-gij-self-managed) (Git Integration for Jira Data Center/Server)

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

