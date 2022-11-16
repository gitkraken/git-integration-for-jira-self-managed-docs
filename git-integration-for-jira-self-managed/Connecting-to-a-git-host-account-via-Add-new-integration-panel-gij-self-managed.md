---

title: Connecting to a git host account via Add new integration panel (Integration basics)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

This process requires a git host account (e.g. GitHub/GitLab/VSTS etc.) Use the Add new integration panel in Jira Cloud/Server to connect git repositories from git hosts to Jira. This is the recommended way of integrating your multiple git repositories to Jira.

1.  On your Jira dashboard menu, click Git ➜ **Manage repositories**.

2.  Click a git host on the Add new integration panel.

    Select from the supported git host integration (_or click the integration links below to follow to their own integration guide_):

    *   [GitHub.com](/git-integration-for-jira-data-center/github-gij-self-managed)

    *   [GitHub Enterprise Server](/git-integration-for-jira-data-center/github-enterprise-server-gij-self-managed)

    *   [Bitbucket](/git-integration-for-jira-data-center/bitbucket-server-gij-self-managed)

    *   [GitLab.com](/git-integration-for-jira-data-center/gitlab-gij-self-managed)

    *   [GitLab CE/EE](/git-integration-for-jira-data-center/gitlab-ce-ee-gij-self-managed)

    *   [AWS CodeCommit](/git-integration-for-jira-data-center/aws-codecommit-gij-self-managed)

    *   [Azure DevOps / VSTS](/git-integration-for-jira-data-center/azure-devops-visual-studio-team-services-vsts-gij-self-managed)

    *   [Azure DevOps Server / TFS](/git-integration-for-jira-data-center/azure-devops-server-team-foundation-services-tfs-gij-self-managed)

    *   [Gerrit](/git-integration-for-jira-data-center/gerrit-gij-self-managed)

    *   [Git](/git-integration-for-jira-data-center/connecting-to-a-single-git-repository-http-https-gij-self-managed)

3.  The Add new integration Wizard is displayed.

    *    Enter login credentials. If two-factor authentication is enabled for your git host, enter the token as the password instead.

    *    Follow screen instructions to import git repositories.

4.  On the following screen, change settings as required or leave the default settings as is.

    ![](/wp-content/uploads/git-server-dc-new-settings-auto-connect-wiz.png)

    *   On the Integration Settings, setting the [**Require User PAT** option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) to `ON` will require users to provide PAT which will be used for branch and merge/pull request creation/deletion (via the developer panel on the Jira issue page). This is a security feature of Git Integration for Jira app for git hosts that support two-factor authentication. This option requires the [**Repository Browser**](/git-integration-for-jira-data-center/repository-browser-gij-self-managed) feature to be enabled.

   *   Jira administrators can configure the **Require User PAT** setting when connecting a 2FA git host via the Add new integration panel or via **Edit integration settings** in the **Manage repositories page**. If set to **`ON`**, Jira Users are required to set their PAT for specific repositories via Repository Browser. The setup PAT link is accessible via the developer panel on Create Branch or Create Pull/Merge Request dialogs in the Jira issue page.

        <img src='/wp-content/uploads/bbb-alert-20.png' /> This setting is only available for **auto-connected** git hosts configured via Add new integration wizard with Git Integration for Jira app.

   *   For more information on Project permissions and repository associations, see [Setting Project Permissions](/git-integration-for-jira-data-center/setting-project-permissions-gij-self-managed).

5. Click **Finish** to accept the settings and complete the setup.

<br>

## More related articles on integration basics

**Connecting to a git host account via Add new integration panel** (this page)

[Connecting to a single git repository (HTTPS \| SSH)](/git-integration-for-jira-data-center/connecting-to-a-single-git-repository-(HTTPS-SSH)-gij-self-managed)

[Setting up web links](/git-integration-for-jira-data-center-gij-self-managed/setting-up-web-links-gij-self-managed)

[Link git commits to Jira issues (Basics)](/git-integration-for-jira-data-center/Link-git-commits-to-Jira-issues-(Basics)-gij-self-managed)

[Using smart commits](/git-integration-for-jira-data-center/using-smart-commits-gij-self-managed)

[Using the Repository Browser](/git-integration-for-jira-data-center/using-the-repository-browser-gij-self-managed)

[Creating branches and pull \| merge requests (Basics)](/git-integration-for-jira-data-center/Creating-branches-and-pull-merge-requests-(Basics)-gij-self-managed)

