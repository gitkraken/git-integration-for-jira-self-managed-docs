---

title: Using smart commits (Integration basics)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Smart commits enable users to perform actions on Jira issues from a single commit. In a commit message, enter the issue key and some desired action such as resolving an issue, closing an issue, time tracking or all of them.

![](/wp-content/uploads/gij-gitserver-git-commits-tab-example-new.png)

For example, if a user wants to log specified time with worklog comment, adds a comment, and resolve the issue TEST-100, enter the commit message as follows:

**TEST-100** **#time** 2h 30m _Fixed code_ **#comment** _Merge to master_ **#resolve**

<br>

Enable/disable this feature via:

*   Connect to Git Repository wizard

*   Connect to Git Repository ➜ **Advanced setup**

*   Apps/Applications ➜ Manage repositories ➜ ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit Repository**


To learn more about Smart Commits, see [Git Integration for Jira: Smart Commits](/git-integration-for-jira-data-center/smart-commits-gij-self-managed).

### More related articles on integration basics

[Connecting to a git host account via Add new integration panel](/git-integration-for-jira-data-center/connecting-to-a-git-host-account-via-Add-new-integration-panel-gij-self-managed)

[Connecting to a single git repository (HTTPS | SSH)](/git-integration-for-jira-data-center/connecting-to-a-single-git-repository-(HTTPS-SSH)-gij-self-managed)

[Setting up web links](/git-integration-for-jira-data-center-gij-self-managed/setting-up-web-links-gij-self-managed)

[Link git commits to Jira issues (Basics)](/git-integration-for-jira-data-center/Link-git-commits-to-Jira-issues-(Basics)-gij-self-managed)

**Using smart commits** (this page)

[Using the Repository Browser](/git-integration-for-jira-data-center/using-the-repository-browser-gij-self-managed)

[Creating branches and pull | merge requests (Basics)](/git-integration-for-jira-data-center/Creating-branches-and-pull-merge-requests-(Basics)-gij-self-managed)

