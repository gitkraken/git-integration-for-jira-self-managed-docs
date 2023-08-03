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

[Indexing queue viewer](/git-integration-for-jira-data-center/Indexing-queue-viewer-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking to the GitKraken Git client](/git-integration-for-jira-data-center/Deep-Linking-to-the-GitKraken-Git-client-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking into GitLens](/git-integration-for-jira-data-center/Deep-Linking-into-GitLens-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Git Integration + Jira Automation (Jira Server \| DC)](/git-integration-for-jira-data-center/Git-integration-plus-Jira-automation-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating branches](/git-integration-for-jira-data-center/Creating-branches-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/Creating-pull-merge-requests-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/Associate-Pull-Merge-Requests-to-Issues-Based-on-Commits-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Issue Git integration panel](/git-integration-for-jira-data-center/Issue-Git-integration-panel-gij-self-managed) (Git Integration for Jira Server/Data Center)

**Smart commits overview** (this page)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/Shared-reindex-queue-between-DC-nodes-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Enforced git permissions for Jira users](/git-integration-for-jira-data-center/Enforced-git-permissions-for-Jira-users-gij-self-managed) (Git Integration for Jira Server/Data Center)

