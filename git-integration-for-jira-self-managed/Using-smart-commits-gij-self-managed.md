---

title: Using smart commits
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Smart commits enable users to perform actions on Jira issues from a single commit. In a commit message, enter the issue key and some desired action such as resolving an issue, closing an issue, time tracking or all of them.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2045149209/gitserver-git-commits-tab-example-new.png%3Fversion=1&modificationDate=1640706006442&cacheVersion=1&api=v2?version=1&modificationDate=1640866071249&cacheVersion=1&api=v2)

For example, if a user wants to log specified time with worklog comment, adds a comment, and resolve the issue TEST-100, enter the commit message as follows:

**TEST-100** **#time** 2h 30m Fixed code **#comment** Merge to master **#resolve**

Enable/disable this feature via:

*   Connect to Git Repository wizard

*   Connect to Git Repository ➜ **Advanced setup**

*   Apps/Applications ➜ Manage repositories ➜ Actions ➜ **Edit Repository**


To learn more about Smart Commits, see [Git Integration for Jira: Smart Commits](/git-integration-for-jira-self-managed/Smart-commits).

