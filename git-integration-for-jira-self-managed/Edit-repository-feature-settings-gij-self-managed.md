---

title: Edit repository feature settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Starting **v4.24+**, the Edit repository feature settings page have been revamped and improved.

![](/wp-content/uploads/gij-gitserverdc-edit-repository-actions-menu-sel.png)

&nbsp;

On the Manage integrations list, click <img src='/wp-content/uploads/actions-icon.png' /> Action ➜ **Edit repository settings**. This will open the repository connection settings page for the chosen repository. The available settings depends on which type of repository you are currently working on: `HOSTED`, `EXTERNAL` or `FOLDER`.

![](/wp-content/uploads/gij-gitserverdc-edit-repo-connection-settings-01.png)

On the integration panel, the repository origin and the connection status of the repository is displayed. <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW!</b>

Utilize the options below for configuring repository settings:

*   [Main branch](#main-branch)
*   [Code review settings](#code-review-settings)
*   [Tags](#tags)
*   [Pull/merge requests](#pull-or-merge-request)
*   [Smart commits](#smart-commits)
*   [Project permissions](#project-permissions)
*   [Commit notification emails](#commit-notification-emails)
*   [Web linking](#web-linking)

&nbsp;
* * *
&nbsp;

### Main branch

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-repo-feature-settings-02.png' style='margin:25px auto 35px auto;display:block;max-width:100%;'>

Set the main branch for this repository. The default branch is set to your main branch.

&nbsp;

### Code review settings

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b>

The Code review settings group contains configuration options for Repository Browser and Source code diff viewing.

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-02.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

#### Repository Browser

If set to **Enabled**, this setting will allow users to have access to the Repository Browser to view git repositories of configured projects.

For more information, see [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed).

#### Source code diff viewing

If set to **Enabled**, this setting allows or denies access to users to view the diff by commit and file.

For detailed information, see [Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed).

&nbsp;

### Tags

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-03.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Set whether to show all tags or show only tags with matching regex pattern. You can view the list of tags at the bottom of the Jira issue Git integration panel.

For more information on git tags, see [Git Tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed).

&nbsp;

### Pull or merge requests

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-04.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Set whether to show all pull requests or hide only the pull requests with matching regex pattern. You can view the list of available pull requests that are linked to a Jira issue on the Jira issue Git integration panel.

For more information, see [Pull or merge requests filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed).

&nbsp;

### Smart commits

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-05.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Toggle to turn on/off the Smart commits feature. [What are Smart Commits?](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed)

&nbsp;

### Project permissions

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-07.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

You can restrict access to the Repository Browser and Git Commits tabs for the selected repository by setting the project associations. The **Associate with all projects** setting is enabled by default.

To restrict to specific projects, uncheck the _**Associate with all projects**_ option and set/select one or more projects from the list.

For more information, see [Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed).

&nbsp;

### Commit notification emails

<b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>HOSTED</b> <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b> <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>FOLDER</b>

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-08.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Enable/disable **Send notifications** setting to allow/stop sending of commit notification emails.

Set the **Max commit age (in minutes)** as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value.

See [commit notification emails](/git-integration-for-jira-data-center/commit-email-notifications-gij-self-managed) to learn more about these settings.

&nbsp;

### Web linking

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>EXTERNAL</b>

The web linking feature adds links to your git hosting provider directly into the Git Commits tab. For special integrations (Auto-Connect), this feature is configured automatically.

For more information, see [Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed).

* * *

Click **Save** to save the settings.

&nbsp;
* * *

[**Prev:** Edit repository connection settings](/git-integration-for-jira-data-center/edit-repository-settings-gij-self-managed)

[**Next:** SSL verify](/git-integration-for-jira-data-center/ssl-verify-gij-self-managed)

