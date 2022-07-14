---

title: Smart commits overview
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## Introduction

Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

The Git Integration for Jira app, the smart commit processing is **active by default** and can be enabled/disabled via the repository configuration:

![](https://bigbrassband.com/docimgs/smart-commit-setting.png)

Smart commits configuration checklist:

*   The Jira DVCS Connector Plugin is not required.
*   Your Jira e-mail address and Git commit e-mail address matches.
*   E-mail address is not shared by other Jira users.

The basic syntax for a smart commit message is:

**\<ISSUE\_KEY\>** _\<ignored text\>_ **\#\<command\>** _\<optional command\_params\>_

<br>

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
<br>

* * *

## Did You Know?

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

* * *

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
<br>

