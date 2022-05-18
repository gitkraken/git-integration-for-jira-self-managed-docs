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

*   Apps/Applications ➜ Manage repositories ➜ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit Repository**


To learn more about Smart Commits, see [Git Integration for Jira: Smart Commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits).

* * *

### More related articles on integration guides

*   Page:

    [Connecting to a git host account via Add new integration panel](/wiki/spaces/GIJDC/pages/2044035170/Connecting+to+a+git+host+account+via+Add+new+integration+panel) (Git Integration for Jira Data Center)

*   Page:

    [Connecting to a single git repository (HTTPS | SSH)](/wiki/spaces/GIJDC/pages/2044035207) (Git Integration for Jira Data Center)

*   Page:

    [Setting up web links](/wiki/spaces/GIJDC/pages/2045181986/Setting+up+web+links) (Git Integration for Jira Data Center)

*   Page:

    [Link git commits to Jira issues (Basics)](/wiki/spaces/GIJDC/pages/2045149189) (Git Integration for Jira Data Center)

*   Page:

    [Using smart commits](/wiki/spaces/GIJDC/pages/2045149209/Using+smart+commits) (Git Integration for Jira Data Center)

*   Page:

    [Using the Repository Browser](/wiki/spaces/GIJDC/pages/2045214758/Using+the+Repository+Browser) (Git Integration for Jira Data Center)

*   Page:

    [Creating branches and pull | merge requests (Basics)](/wiki/spaces/GIJDC/pages/2045149234) (Git Integration for Jira Data Center)