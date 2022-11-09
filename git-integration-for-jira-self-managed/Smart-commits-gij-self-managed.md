---

title: Smart commits
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- documentation  -->

Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

## Getting started

The smart commit processing is **active by default** and can be enabled/disabled via the git configuration page (![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit integration/repository settings**):

<img src='/wp-content/uploads/gij-smart-commit-setting.png' style='display:block;margin:25px auto;max-width:100%' />

<div style='text-align:center;font-style:italic;'>
    In Jira Server, Smart Commits is a setting toggle in the <b>Connect wizard</b> or <br>the git configuration page under <img src='/wp-content/uploads/actions-icon.png' style='margin:0 3px' /> Actions ➜ <b>Edit integration/repository settings</b>. <br>In Jira Cloud, this setting is always enabled.
</div>

<p>&nbsp;</p>

<br>

Smart commits support for project keys that has an underscore "\_" character.<br>
<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 3.2.0+</b> Smart commits support for all alphabet characters.<br>
<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 3.5.0.2+</b> Smart commits support for case insensitive smart commits.

<br>
<br>

Smart commits configuration checklist:

*   **The Jira DVCS Connector Plugin is not required.**
    The Git Integration for Jira app has the functions of the connector plugin plus more integration support and features.

*   **Your Jira e-mail address and Git commit e-mail address matches.**
    The commit author's email should match exactly with a user's email in Jira. If they do not match, the application will add the commit as the app.

*   **E-mail address is not shared by other Jira users.**
    Verify that this email address is used by only one Jira user.

*   **Advanced:** Verify that the workflow conditions and validators are able to process successfully.

<br>
<br>

The Git Integration app supports smart commit by adding a simple syntax to a commit message.

The basic syntax for a Smart commit message is:

```java
<ISSUE_KEY> <ignored text> #<command> <optional command_params>
```

To know more about syntax, commands and examples on Smart Commits, see <a href='https://confluence.atlassian.com/bitbucket/processing-jira-software-issues-with-smart-commit-messages-298979931.html' target='_blank'><b>Processing Jira Software Issues with Smart Commit Messages</b></a> at the Atlassian website or proceed to the next page.

