---

title: Integration basics - Using smart commits
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Smart commits enable users to perform actions on Jira issues from a single commit. In a commit message, enter the issue key and some desired action such as resolving an issue, closing an issue, time tracking or all of them.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2045149209/gitserver-git-commits-tab-example-new.png%3Fversion=1&modificationDate=1640706006442&cacheVersion=1&api=v2?version=1&modificationDate=1640866071249&cacheVersion=1&api=v2)

For example, if a user wants to log specified time with worklog comment, adds a comment, and resolve the issue TEST-100, enter the commit message as follows:

**TEST-100** **#time** 2h 30m _Fixed code_ **#comment** _Merge to master_ **#resolve**

<br>

Enable/disable this feature via:

*   Connect to Git Repository wizard

*   Connect to Git Repository ➜ **Advanced setup**

*   Apps/Applications ➜ Manage repositories ➜ <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit Repository**


To learn more about Smart Commits, see [Git Integration for Jira: Smart Commits](/git-integration-for-jira-self-managed/Smart-commits).

