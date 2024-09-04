---

title: Issue Git integration panel - Features
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        By default, <a href='https://marketplace.atlassian.com/4984'>Git Integration for Jira</a> has the Git integration panel enabled. (<a href='#how-can-a-jira-administrator-enable-or-disable-the-issue-git-integration-development-panel'>How to disable?</a>)
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <b>View developer tools</b> <i>permission</i> is required to view the Issue Git integration panel. Jira users must also have the <b>Browse Project</b> <i>permissions</i> to a project associated with a repository to view.
    </div>
    </div>
</div>

&nbsp;

### Overview

The Issue Git integration panel displays:

<ul>
    <li>
        <b>Git Commits:</b> number of commits and link to <a href='/git-integration-for-jira-data-center/git-commits-tab-gij-self-managed'>Git Commits Issue Tab</a>, link to <a href='/git-integration-for-jira-data-center/git-roll-up-tab-docs-gij-self-managed'>Git Roll Up Issue Tab</a>.
    </li>
    <li>
        <b>Branches:</b> Create branch function, list of branches associated to Jira issue (Jira issue key must be in branch title).<br><b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>NEW v4.17+</b> The main branch can now be displayed in the Branches list. This is controlled by <a href='/git-integration-for-jira-data-center/git-integration-features-gij-self-managed/#issue-git-integration-panel'>enabling/disabling this General setting</a> under Issue Git integration panel.
    </li>
    <li>
        <b>Pull/Merge Requests:</b> Create pull/merge request function, list of pull/merge requests associated to Jira issue (Jira issue key must be in PR/MR title), status of pull/merge request
    </li>
    <li>
        <b>Tags:</b> git tags associated to Jira issue (via associated commit). Tags are sometimes referred to as Releases in some products.
    </li>
</ul>

![](/wp-content/uploads/gij-gitserver-git-integration-panel-view-417.png)

&nbsp;

### How can a Jira administrator enable or disable the Issue Git integration development panel?

1.  Install the [Git Integration for Jira](https://marketplace.atlassian.com/4984) app.

2.  Navigate to the [**General settings**](/git-integration-for-jira-data-center/general-settings-docs-gij-self-managed) page of the application.

3.  Enable or disable the setting: `Show Git integration panel on issue pages`.

4.  Click **Update** button.

&nbsp;

![](/wp-content/uploads/gij-gitserver-gencfg-dev-panel-sel-417.png)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='mailto:gijsupport@gitkraken.com'>gijsupport@gitkraken.com</a>.
    </div>
    </div>
</div>

&nbsp;

### See more Git Integration for Jira app features

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

[Cancel indexing](/git-integration-for-jira-data-center/cancel-indexing-revision-indexing-gij-self-managed/) (Git Integration for Jira Data Center)

[Pull request filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Tag filters](/git-integration-for-jira-data-center/tag-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Indexing queue viewer](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/) (Git Integration for Jira Data Center)

[Deep linking feature](/git-integration-for-jira-data-center/deeplinking-feature-gij-self-managed/) (Git Integration for Jira Data Center)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + ScriptRunner](/git-integration-for-jira-data-center/gij-plus-scriptrunner-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + Jira Automation](/git-integration-for-jira-data-center/git-integration-plus-jira-automation-gij-self-managed/) (Git Integration for Jira Data Center)

[Enforced git permissions for Jira users – Features](/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed/) (Git Integration for Jira Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/shared-reindex-queue-between-dc-nodes-gij-self-managed/) (Git Integration for Jira Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed/) (Git Integration for Jira Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/) (Git Integration for Jira Data Center)

**Issue Git integration panel – Features** (this page)

