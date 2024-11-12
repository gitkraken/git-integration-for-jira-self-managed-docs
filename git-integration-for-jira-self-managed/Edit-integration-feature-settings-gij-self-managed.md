---

title: Edit integration feature settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Starting **v4.24+**, the integration feature settings page have been revamped and improved.

![](/wp-content/uploads/gij-gitserverdc-edit-repository-actions-menu-sel.png)

&nbsp;

On the Manage integrations list, click <img src='/wp-content/uploads/actions-icon.png' /> Action ➜ **Edit integration settings** then click **Feature settings** on the sidebar. This will open the configuration feature settings page for the selected integration.

![](/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-01.png)

Utilize the options below for configuring repository settings:

*   [Code review settings](#code-review-settings)
*   [Tags](#tags)
*   [Pull/merge requests](#pull-or-merge-requests)
*   [Smart commits](#smart-commits)
*   [Require user PAT](#require-user-pat)
*   [Project permissions](#project-permissions)
*   [Commit notification emails](#commit-notification-emails)

&nbsp;
* * *
&nbsp;

### Code review settings

The Code review settings group contains configuration options for Repository Browser and Source code diff viewing.

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-02.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

#### Repository Browser

If set to **Enabled**, this setting will allow users to have access to the Repository Browser to view git repositories of configured projects.

For more information, see [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed/).

#### Source code diff viewing

If set to **Enabled**, this setting will allow users to have access to the Repository Browser to view git repositories of configured projects.

For more information, see [Configure source code diff viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed).

&nbsp;

### Tags

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-03.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Set whether to show all tags or show only tags with matching regex pattern. You can view the list of tags at the bottom of the Jira issue Git integration panel.

For more information on git tags, see [Git Tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed/).

&nbsp;

### Pull or merge requests

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-04.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Set whether to show all pull requests or hide only the pull requests with matching regex pattern. You can view the list of available pull requests that are linked to a Jira issue on the Jira issue Git integration panel. 

For more information, see [Pull/merge requests filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed).

&nbsp;

### Smart commits

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-05.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Toggle to turn on/off the Smart commits feature. [What are Smart Commits?](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed)

&nbsp;

### Require User PAT

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-06.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Set this setting to **Enable** to force users to provide PAT which will be used for branch and merge/pull request creation/deletion (via the developer panel on the Jira issue Git integration page). This is a security feature of Git Integration for Jira app for git hosts that support two-factor authentication.

For more information, see [Require PAT for user actions](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This option requires the <a href='/git-integration-for-jira-data-center/repository-browser-gij-self-managed'>Repository Browser</a> feature enabled.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is only available for auto-connected git hosts in Jira Server and Jira Data Center.
    </div>
    </div>
</div>

&nbsp;

### Project Permissions

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-07.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

You can restrict access to the Repository Browser and Git Commits tabs for the selected repository by setting the project associations. The **Associate with all projects** setting is enabled by default.

To restrict to specific projects, uncheck the _**Associate with all projects**_ option and set/select one or more projects from the list.

For more information, see [Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed).

&nbsp;

### Commit Notification Emails

<img src='/wp-content/uploads/gij-gitserverdc-edit-integration-feature-settings-08.png' style='margin:25px auto 35px auto;display:block;max-width:100%;' />

Enable/disable this setting to allow/stop sending of commit notification emails.

Set the **Max commit age (in minutes)** as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value.

See [commit notification emails](/git-integration-for-jira-data-center/commit-email-notifications-gij-self-managed) to learn more about these settings.

* * *

Click **Save** to save the changes.

&nbsp;
* * *

[**Prev:** Edit integration connection settings](/git-integration-for-jira-data-center/edit-integration-connection-settings-gij-self-managed)

[**Next:** Edit repository settings](/git-integration-for-jira-data-center/edit-repository-settings-gij-self-managed)

