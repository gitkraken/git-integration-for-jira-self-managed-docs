---

title: Integration basics - Connecting to a git host account via Add new integration panel
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

3. The Connect Wizard is displayed. Enter login credentials. If two-factor authentication is enabled for your git host, enter the token as the password instead. Follow screen instructions to import git repositories.

4. On the following screen, change settings as required or leave the default settings as is.

    ![](https://api.media.atlassian.com/file/0c16285e-0511-4c4c-9b41-50195811a1eb/binary?token=eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiI0YTVjYjQ0OC0zMzNlLTQ5ZTctOGJkZC1lZGY3NThjZGI3MjYiLCJhY2Nlc3MiOnsidXJuOmZpbGVzdG9yZTpmaWxlOjBjMTYyODVlLTA1MTEtNGM0Yy05YjQxLTUwMTk1ODExYTFlYiI6WyJyZWFkIl19LCJleHAiOjE2NTQ3Njc5MDcsIm5iZiI6MTY1NDY4NDkyN30.yZExGqf5UuuoIR1xnI8M4UGvfTWDIkMAWJh7RaKuf2c&client=4a5cb448-333e-49e7-8bdd-edf758cdb726&name=git-server-dc-new-settings-auto-connect-wiz.png&max-age=2940)

   *   On the Integration Settings, setting the [**Require User PAT** option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) to `ON` will require users to provide PAT which will be used for branch and merge/pull request creation/deletion (via the developer panel on the Jira issue page). This is a security feature of Git Integration for Jira app for git hosts that support two-factor authentication. This option requires the **[Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed)** feature to be enabled.

        **IMPORTANT!** Do not enable this feature for connected git hosts that don't support it. For example, TFS2013/2015 does not support PATs. Users won't be able to create branches or create pull/merge request if the above setting is **`ON`**.

   *   Jira administrators can configure the **Require User PAT** setting when connecting a 2FA git host via the Add new integration panel or via **Edit integration settings** in the **Manage repositories page**. If set to **`ON`**, Jira Users are required to set their PAT for specific repositories via Repository Browser. The setup PAT link is accessible via the developer panel on Create Branch or Create Pull/Merge Request dialogs in the Jira issue page.

        This setting is only available for **auto-connected** git hosts configured via Add new integration wizard with Git Integration for Jira app.

   *   For more information on Project permissions and repository associations, see [Setting Project Permissions](/git-integration-for-jira-data-center/setting-project-permissions-gij-self-managed).

5. Click **Finish** to accept the settings and complete the setup.

