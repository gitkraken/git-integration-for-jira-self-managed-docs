---

title: Smart commits overview
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### Introduction

Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

The Git Integration for Jira app, the smart commit processing is **active by default** and can be enabled/disabled via the repository configuration:

![](/wp-content/uploads/gij-smart-commit-setting.png)

  
Smart commits configuration checklist:

*   The Jira DVCS Connector Plugin is not required.
*   Your Jira e-mail address and Git commit e-mail address matches.
*   E-mail address is not shared by other Jira users.

The basic syntax for a smart commit message is:

**\<ISSUE\_KEY\>** _\<ignored text\>_ **\#\<command\>** _\<optional command\_params\>_

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For more information on the Smart Commits feature, see <a href='/git-integration-for-jira-data-center/smart-commits-gij-self-managed/'>Documentation: Smart commits</a>.
    </div>
    </div>
</div>

* * *

### Did You Know?

<br>

**Jira User**<br>
The committers’ email address in the git configuration must match with the email address of the corresponding Jira user (or vice versa) for the smart commit to work.

<br>

**Project Permissions**<br>
The Jira user must have the appropriate project permissions to transition issues.

<br>

**Workflow Transition**<br>
When you hover a status on the Issue Workflow - it will highlight available transitions.  This is the transition name that is used in Smart Commits.

<br>

**Email Notifications**<br>
If a smart commit fails, an email notification is sent to either the Jira user, or to the Git user if a Jira user cannot be identified.

<br>

**Transition Names**<br>
To avoid conflict when transitioning issues, give a unique name to a workflow transition.

<br>

**Smart Commit Helper**<br>
When the **Smart Commits** setting is disabled for that repository, the Git Integration for Jira app will not show the [COMMIT indicators](/git-integration-for-jira-data-center/smart-commits-helper-gij-self-managed).

<br>

**Multi-line Commits**<br>
The Git Integration for Jira app support multi-line commit messages for smart commits.

[Related topic »](/git-integration-for-jira-data-center/Advanced-examples-gij-self-managed#multi-line-examples)

<br>

**Smart Commit Status**<br>
The commit status shown on the Issue page depends on the Smart Commits setting that was set at the time the commits were processed.

&nbsp;
* * *
&nbsp;

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Need to know more?  Read further at  <a href='/git-integration-for-jira-data-center/smart-commits-gij-self-managed'>Documentation: Smart commits</a>.
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

**Smart commits overview** (this page)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/) (Git Integration for Jira Data Center)

[Issue Git integration panel – Features](/git-integration-for-jira-data-center/issue-git-integration-panel-gij-self-managed/) (Git Integration for Jira Data Center)

