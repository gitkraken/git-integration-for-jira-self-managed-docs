---

title: Smart commits - Documentation
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

### Getting started

The smart commit processing is **active by default** and can be enabled/disabled via the git configuration page &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ **Edit integration/repository settings**):

<img src='/wp-content/uploads/gij-smart-commit-setting.png' width=374 height=80 style='display:block;margin:25px auto;max-width:100%' />

<div align='center'>
    <i>In Jira Server, Smart Commits is a setting toggle in the **Connect wizard** or the git<br>
    configuration page under <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit integration/repository settings</b>.<br>
    In Jira Cloud, this setting is always enabled.</i>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Smart commits support for project keys that has an underscore "_" character.<br>
        Smart commits support for all alphabet characters.<br>
        Smart commits support for case insensitive smart commits.
    </div>
    </div>
</div>

Smart commits configuration checklist:

*   **The Jira DVCS Connector Plugin is not required.**
    The Git Integration for Jira app has the functions of the connector plugin plus more integration support and features.

*   **Your Jira e-mail address and Git commit e-mail address matches.**
    The commit author's email should match exactly with a user's email in Jira. If they do not match, the application will add the commit as the app.

*   **E-mail address is not shared by other Jira users.**
    Verify that this email address is used by only one Jira user.

*   **Advanced:** Verify that the workflow conditions and validators are able to process successfully.

The Git Integration app supports smart commit by adding a simple syntax to a commit message.

The basic syntax for a Smart commit message is:

```java
<ISSUE_KEY> <ignored text> #<command> <optional command_params>
```

To know more about syntax, commands and examples on Smart Commits, see <a href='https://confluence.atlassian.com/bitbucket/processing-jira-software-issues-with-smart-commit-messages-298979931.html' target='_blank'><b>Processing Jira Software Issues with Smart Commit Messages</b></a> at the Atlassian website or proceed to the next page.

&nbsp;
* * *

[**Prev:** Linking git commits to Jira issues](/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed)

[**Next:** Smart commit - Basic commands](/git-integration-for-jira-data-center/basic-commands-gij-self-managed)

&nbsp;

### More articles on Smart commits

[Basic commands](/git-integration-for-jira-data-center/basic-commands-gij-self-managed)

[Advanced examples](/git-integration-for-jira-data-center/advanced-examples-gij-self-managed)

[Workflow transitions](/git-integration-for-jira-data-center/workflow-transitions-gij-self-managed)

[Viewing transitions](/git-integration-for-jira-data-center/viewing-transitions-gij-self-managed)

[Smart commit helper](/git-integration-for-jira-data-center/smart-commit-helper-gij-self-managed)

[Smart commits general setting](/git-integration-for-jira-data-center/smart-commits-general-setting-gij-self-managed)

[Jira workflow hooks (scripting)](/git-integration-for-jira-data-center/scripting-(jira-git-workflow-hooks)-gij-self-managed)


