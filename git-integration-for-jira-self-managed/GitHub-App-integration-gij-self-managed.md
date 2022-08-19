---

title: GitHub App integration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

GitHub offers a variety of integration options, including: API, OAuth, and more recently GitHub Apps. There are a number of benefits to using GitHub app over OAuth:

*   GitHub apps are by nature an organization installation. A separate GitHub account or service user is not required.

*   Because GitHub apps require GitHub administrator authorization, we can rely on the GitHub app having administrator permissions.

*   Determine repository access at the organization or repository level for the integration

*   GitHub apps have a higher rate limit than OAuth.

For more details, see the [GitHub Apps article](https://docs.github.com/en/developers/apps/getting-started-with-apps/differences-between-github-apps-and-oauth-apps).

## New integration options

Two new integration options are added into the Add new integration wizard Connect screen:

1.  GitHub App (GitHub.com and GitHub Enterprise Cloud)

2.  GitHub Enterprise App (GitHub Enterprise Server)

There are two terms:

*   **GitHub Application (GHA)** – GHA itself is a set of authorization information. It is created in some GitHub organization during the first step of connecting a GHA integration with the Git Integration for Jira app.  

*   **Installation of a GitHub Application** –  To get access to repositories inside the organization, an admin has to install the GHA in the organization. During the installation of GHA, the administrator selects the scope that will be available for this installation of this GHA. It is the second step of connecting a GHA integration.

## Permissions

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        You must be an organization owner or have admin permissions in a repository to install/uninstall a GitHub App on an organization. If a GitHub App is installed in a repository and requires organization permissions, the organization owner must approve the application.
    </div>
    </div>
</div>
<br>

Check GitHub Apps permission for your organization:

1.  On your GitHub web portal, go to your organization ➜ **Settings** tab.

2.  On the sidebar, click Developer settings ➜ **GitHub Apps**.

![](/wp-content/uploads/gij-github-app-org-setting-GHA-c.png)

## Integrate to a GitHub App

As an initial configuration requirement, admins need to install the GHA in an organization. After this setup, only then Jira can read the repositories with Git Integration for Jira app:

1.  On your Jira dashboard menu, go to Git ➜ **Manage repositories**.

    ![](/wp-content/uploads/gij-dashboard-git-menu-repo-manager-c.png)

2.  On the Add new integration panel, click **GitHub**.

3.  With version 4.6, the GitHub App integration feature is added to the External service list.

    ![](/wp-content/uploads/gij-github-integration-external-host-selection-c.png)

4.  Pick the integration that conforms to your configuration:

    *   GitHub.com and GitHub Enterprise Cloud

    *   GitHub Enterprise Server

5.  Enter **Organization name**.

    ![](/wp-content/uploads/gij-github-app-integration-ready-connect-c.png)

    For GHA on GitHub Enterprise Server external service, enter **Host URL** and **Organization name**.

6.  Click **Connect** to continue.

    ![](/wp-content/uploads/gij-github-app-integration-settings-userpat-c.png)

7.  On the Settings screen, the _**Require user PAT**_ setting is enabled and cannot be changed because it is directly affected by the _**Enforce Git service permissions**_ setting in the **General settings** page. For the GHA feature, the user’s PAT is not mandatory since it can interact with the Git server using the GHA access token.

8.  Click Connect to start configuring this GitHub App integration.
The Git Integration for Jira app will perform this task automatically. Provide password credentials if prompted.

9.  On the following screen, enter a **descriptive name** for the new GitHub App. _(Changing this name later on will have a negative impact on the GHA integration)_

    ![](/wp-content/uploads/gij-github-app-create-GHA-github-name-c.png)

10. Click **Create GitHub App…** to proceed.

    ![](/wp-content/uploads/gij-github-app-repository-selector-screen-c.png)

11. Choose:

    *   **All repositories** – to connect all repositories from this organization.

    *   **Only select repositories** – lets you select a specific repository for this setup.

12. Click Install to complete this process.

The GitHub App integration is now displayed in the Git repositories configuration list.

## Post-install notes

The GHA is created automatically by Git Integration for Jira app. For any related questions, please contact [support@gitkraken.com](mailto:support@gitkraken.com.)

*   You can reconfigure connected repositories in the Edit integration connection settings page for this GHA integration (_Actions_).

    ![](/wp-content/upload/gij-github-app-edit-integration-connection-cfg-c.png)

*   Make sure that the following properties must not be changed for this GHA integration:
    *   GitHub App name
    *   Post installation
    *   Webhook attributes
    *   Private keys
    *   Any settings on the Permissions and Events page
    *   Any settings on the installation page

