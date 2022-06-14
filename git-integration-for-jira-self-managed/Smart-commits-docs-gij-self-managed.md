---

title: Smart commits - Documentation
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

## Getting started

The smart commit processing is **active by default** and can be enabled/disabled via the git configuration page &nbsp;<img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> **Actions ➜ Edit integration/repository settings**):

<img src='https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398395/smart-commit-setting.png?version=1&modificationDate=1630642887746&cacheVersion=1&api=v2&width=374&height=80' class='center img-responsive img-bordered' />

<div align='center'>
    <i>In Jira Server, Smart Commits is a setting toggle in the **Connect wizard** or the git<br>
    configuration page under <b>Actions</b> ➜ <b>Edit integration/repository settings</b>.<br>
    In Jira Cloud, this setting is always enabled.</i>
</div>
<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Smart commits support for project keys that has an underscore "_" character.<br>
        <b>VERSION 3.2.0+</b> Smart commits support for all alphabet characters.<br>
        <b>VERSION 3.5.0.2+</b> Smart commits support for case insensitive smart commits.
    </div>
    </div>
</div>
<br>

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

To know more about syntax, commands and examples on Smart Commits, see [**Processing Jira Software Issues with Smart Commit Messages**](https://confluence.atlassian.com/bitbucket/processing-jira-software-issues-with-smart-commit-messages-298979931.html) at the Atlassian website or proceed to the next page.

