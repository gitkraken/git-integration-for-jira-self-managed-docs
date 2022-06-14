---

title: GitHub Enterprise Server
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
        These instructions apply to self-hosted GitHub Enterprise Server.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For instructions to instances hosted on GitHub.com (Free, Team, Enterprise (including <a href='https://docs.github.com/en/enterprise-cloud@latest/admin/identity-and-access-management/managing-iam-with-enterprise-managed-users/about-enterprise-managed-users'></b>EMU</b></a> plans), please go to <a href='/git-integration-for-jira-self-managed/github/'>this page</a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <b>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/github.com/'>See the corresponding article</a>.
    </div>
    </div>
</div>
<br>

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/github-ent-server-banner-logo.png?version=1&modificationDate=1646819881183&cacheVersion=1&api=v2&width=510&height=59)

# Integrate GitHub Enterprise Server with Jira Data Center/Server

Quickly learn how to connect GitHub Enterprise Server git repositories via Git Integration for Jira Server.

**What's on this page:**
- [Integrate GitHub Enterprise Server with Jira Data Center/Server](#integrate-github-enterprise-server-with-jira-data-centerserver)
  - [Creating a personal access token](#creating-a-personal-access-token)
  - [Using Full feature integration](#using-full-feature-integration)
  - [Single repository (Manual integration)](#single-repository-manual-integration)
  - [Setting up GitHub Enterprise Server permissions](#setting-up-github-enterprise-server-permissions)
    - [Default repository permission**](#default-repository-permission)
    - [Teams and collaborators](#teams-and-collaborators)
  - [Setting up GitHub web links](#setting-up-github-web-links)
  - [Viewing git commits in Jira Server](#viewing-git-commits-in-jira-server)
  - [Require User PAT settings for user access](#require-user-pat-settings-for-user-access)
  - [Working with branches and pull requests](#working-with-branches-and-pull-requests)
    - [Default branch](#default-branch)
    - [Creating branches](#creating-branches)
    - [Creating pull requests](#creating-pull-requests)


* * *

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/75nvefgz66?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/75nvefgz66'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

## Creating a personal access token

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If two-factor authentication is enabled for your GitHub Enterprise Server account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitHub Enterprise Server account for increased security.
    </div>
    </div>
</div>

While instructions from GitHub works just fine, [follow this article](/git-integration-for-jira-self-managed/creating-personal-access-tokens-gij-self-managed/) for some specific instructions to get you started.

## Using Full feature integration

This process requires an existing GitHub Enterprise account.

We recommend using the Add new integration panel to connect multiple repositories from your GitHub Enterprise Server account.

This setup uses full feature integration offering functions and features not found on single repository connections.

1.  On your Jira Server dashboard menu, go to Git ➜ **Manage repositories**. The git configuration page for connecting repositories is displayed.

2.  On the Add new integration panel, click **GitHub Enterprise**. The Add new integration Wizard is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/gitserver-42-connect-auto-ext-service-github-ent-svr(c).png?version=1&modificationDate=1648030398265&cacheVersion=1&api=v2&width=659&height=467)
    -  For the **Host URL**, enter the address of the GitHub Enterprise server.

    -  Enter the **Personal Access Token** in the provided box as required.
    
        _**Note:**_ For repository managers, collaborators or users that have enabled 2FA, enter username and the PAT as the password.

    -  Configuring the **Advanced** settings is optional. However, admins/power users may set how the project listing is displayed.

        ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/gitserver-general-advanced-autoconnect-opt(c).png?version=1&modificationDate=1644573046808&cacheVersion=1&api=v2&width=612&height=416)

        -   **Custom API Path**  –  his is a relative path that starts with "/".  The maximum allowed length is 2000 characters or less. The integration will use the relative REST API path to retrieve the list of tracked repositories. The Custom API Path is called everytime the list of repositories is loaded, on a regular scheduled reindex and a manual reindex.

            For more examples, see article [Jira Server: Working with Custom API Path - GitHub Enterprise](/git-integration-for-jira-self-managed/working-with-custom-api-path-gij-self-managed#githubcom-and-github-enterprise-examples/).

        -   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less.

            For help with writing expressions, please contact [support](mailto:support@bigbrassband.com). Read about JMESPath expressions on their [website](http://jmespath.org/).

            For some other examples, see [Working with JMESPath Filter in GitHub Enterprise](/git-integration-for-jira-self-managed/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed/).

        -   **Fetch refspec**  –  Git refspecs contains patterns mapped as references from the remote to the local repository.
            For more information, see **Git Internals -- The Refspec**.

            -  The first two refspec options are required.

            -  The rest of the options are OPTIONAL:

                -  **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching. This option is enabled by default. This affects git notes which are not shown:

                    -  ...when `refs/notes` are disabled on connecting a repository.

                    -   ...when a new note comes when `refs/notes` is disabled.

                -  **Clone and index changes (refs/changes)** – This is a reference to `refs/changes/*` used for fetching.  This option is turned off by default.

                -  **Clone and index other refs** – This is a user-defined list of references used for fetching.  It is a comma-separated list with the format:

                    -   `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

    While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

3.  Click **Connect**.

4.  On the following screen, the Git Integration for Jira app will read all available repositories from your GitHub Enterprise Server account. Click **Import repositories**.

    *   Repositories that are added or removed from GitHub Enterprise Server will be likewise connected or disconnected from Jira Server.

    *   If your git url contains multiple repositories, it will be added as tracked repositories in the git configuration list. Otherwise, a git repository is added instead.

5.  After the import process, the **Settings** dialog is displayed:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/gitserver-github-autoconnect-settings-dlg(c).png?version=1&modificationDate=1644573046812&cacheVersion=1&api=v2&width=646&height=449)

    *   On the Integration Settings, setting the _**Require User PAT**_ option to `ON`, will require users to provide PAT specific for branch and merge requests _(via the developer panel on the Jira issue page)_. For more information on this feature, see [Integration Settings: Require User PAT](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed/).

    *   Set **Smart commits** and **Repository Browser** to enable/disable these features.

    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Associating project permissions](/git-integration-for-jira-self-managed/associating-project-permissions-gij-self-managed/).

6.  Click **Finish** to complete this setup.


GitHub Enterprise Server repositories are now connected to Jira Server.

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

This process requires an existing GitHub Enterprise Server git repository. Look for the git clone URL on the repository project page.

Choose between SSH or HTTPS. Use this information to connect the GitLab git repository to your Jira server via Git Integration for Jira app.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/91914350/github-repository-home.png?version=1&modificationDate=1644573046815&cacheVersion=1&api=v2)

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

2.  Click **Connect to Git Repository** (_or click the Git icon on the Add new integration panel_) to open the Connect Wizard.

3.  Paste the URL from GitHub Enterprise Server web portal in the provided box.

4.  Continue to the next step by following the screen instructions.

5.  Click **Finish** to complete this process. 


The repository is now connected to Jira Server.

## Setting up GitHub Enterprise Server permissions

We recommend using a "service user" in GitHub Enterprise _(example:_ `GitIntegrationforJira`_)_ to be used to integrate with Git Integration for Jira app. This dedicated "service user" will allow the GitHub Enterprise Server administrator to set permissions so the app clones only the desired repositories.

Assign GitHub Enterprise Server permissions for team members or collaborators to allow which resources are accessible for service users. This feature is only available in a GitHub Organization.

### Default repository permission**

1.  Login to your GitHub Enterprise Server account.

2.  Go to Profile ➜ **Settings**.

3.  Under _Organization settings_, click **Member Privileges**.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/91914350/github-default-repo-permission(c).png?version=1&modificationDate=1644573046819&cacheVersion=1&api=v2)
    *   Choose the default permission level for organization members.

    *   The default repository permission only applies to organization members and not to outside collaborators. If the default permission is set to _**None**_, organization members will need to be given access to repositories using the Teams or Collaborators methods (see below).

4.  **Save** the changes.


For more information, see **Access Permissions on GitHub »**.

### Teams and collaborators

To give a member additional access, they must be added to a team or make them collaborators on individual repositories.

<br>

**Set default repository permission for the current team:**

1.  Open an organization team. (_Your org ➜ Team ➜ scroll down to the bottom then click the desired team._)

2.  Click the **Repositories** tab.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/91914350/github-manage-repo-permission-tab(c).png?version=1&modificationDate=1644573046823&cacheVersion=1&api=v2)

3.  Set **Read**, **Write** or **Admin** repository access as desired.

<br>

**Assign members to a team on your GitHub repository:**

1.  Create a team in your GitHub Organization.

2.  Invite a member to add it into the team.  An email invitation is sent to that GitHub service user.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/add-members-to-team(c).png?version=1&modificationDate=1644573046826&cacheVersion=1&api=v2&width=408&height=287)

    The service user is then added to the team if the invitation has been accepted.

3.  Click the service user to manage permissions for this member to:

    *   Set desired **Role** for this member.

    *   Convert this member to outside collaborator.

    *   Give this member access to organization repositories.

    *   Remove this member from the team.

4.  Click **Manage access** to manage repository access for this member.


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/manage-team-repo-permission.png?version=1&modificationDate=1644573046830&cacheVersion=1&api=v2&width=680&height=155)

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        While users have configured PAT for repository access, users in a GitHub Enterprise Server must at least have <b>Read</b> permissions. This allows them to view commits and smart commits, and browse repositories (if enabled) of connected GitHub Enterprise Server repositories inside Jira.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For repository managers, collaborators and commit authors, set these users to have <b>Write</b> permissions. This will allow them to view commits and smart commits, browse repositories and also enables them to create branches and pull requests to specified GitHub git repositories via developer panel of a Jira issue.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The user PAT for "Require User PAT" setting should have <b>Write</b> permission. Otherwise, the user will not be able to use it for branch or pull request creation/deletion.
    </div>
    </div>
</div>

For more information on organization teams, see [**GitHub: Organizing Members into Teams »**](https://docs.github.com/en/organizations/organizing-members-into-teams).

For more information on inviting collaborators, see [**Inviting Collaborators to a Personal/Organization Repository »**](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository).

## Setting up GitHub web links

The Git Integration for Jira app automatically configures web linking for GitHub Enterprise Server git repositories.

For single repository connections, web link setup is optional. However, git links will become available in Git Commits tab when configured.

For more information on this feature, see [Documentation: Web linking](/git-integration-for-jira-self-managed/web-linking-gij-self-managed).

## Viewing git commits in Jira Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View full commit** to view the code diff.


For more information about this feature, see [Documentation: Viewing commit code diffs](/git-integration-for-jira-self-managed/viewing-commit-code-diffs-gij-self-managed/).

## Require User PAT settings for user access

For teams looking to maintain user attribution, Jira administrators can place a requirement where individual Jira users must provide personal access tokens to perform certain actions. This includes actions such as creating a branch or pull request in Jira using their git service account - rather than the integration account.

For more information, see [Require personal access tokens for user access](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed/).

If the **Require User PAT option** is enabled in the **Integration Feature Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, a text label about setting up your PAT is displayed on the create branch and create pull/merge request dialogs.

Click this text label to open the Setup PAT dialog and paste your personal access token in the provided box. Click **Update**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/gitserver-setup-pat-dlg.png?version=1&modificationDate=1644573046835&cacheVersion=1&api=v2&width=544&height=272)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Updating this dialog with a blank entry will remove the configured PAT for the current integration.
    </div>
    </div>
</div>

The Setup PAT dialog is also accessible via Repository Browser (dashboard menu Git ➜ **Repository browser**) ➜ Click the <img src='/wp-content/uploads/gij-edit-icon-dark.png' style='vertical-align: middle; margin: 0 3px;' /> icon under _**Pers. Access**_ column.

## Working with branches and pull requests

This process requires a GitHub Enterprise Server git repository and a PAT with `repo` scopes.

For GitHub Organization, the user must have the **Write** permissions and the `repo` PAT scopes.

### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

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

### Creating branches

On your Jira Server, open a Jira issue. On the Jira developer panel under **Git Integration**, click **Create branch**. The following dialog is displayed.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/gitserver-create-branch-dlg.png?version=1&modificationDate=1644573046839&cacheVersion=1&api=v2&width=544&height=272)

**Pointers:**

1.  Select a **Repository** from the list.

    *  If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.

    *  Use the search box to look for the specific repository that will be used.

2.  Choose a **Base branch**.

3.  Enter a **Branch name** or leave it as is (recommended).

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira Server app gets the default branch from almost all integrations. However, the exception is with Gerrit which always has 'master' as its default branch.
    </div>
    </div>
</div>

The newly-created branch is now listed in the developer panel under **Branches**. Perform a commit to the newly-created branch to be ready for merge.

### Creating pull requests

The pull request feature works the same as merge request. On your Jira Server, open the Jira issue where your previously created a branch. On the developer panel under **Git Integration**, click **Create pull request**. The following dialog is displayed.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/91914350/gitserver-create-pull-req-dlg.png?version=1&modificationDate=1644573046844&cacheVersion=1&api=v2&width=544&height=282)

**Pointers:**

1.  Select a **Repository** from the list.

    *  If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.

    *  Use the search box to look for the specific repository that will be used.

2.  Choose the newly-created branch as the **Source branch**.

3.  Set _**master**_ as the **Target branch**.

4.  Enter a descriptive **Title** or leave it as is _(recommended)_.

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
<br>

The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your GitHub web portal.

