---

title: Git commits issue and project tabs
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This setting is part of the [**General Settings**](/git-integration-for-jira-self-managed/general-settings-gij-self-managed) configuration page.


This setting affects how the information is displayed in the **Git commits issue** and **Project** tabs on the Jira issue.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207828697/gitserver-gencfg-git-commits-issue-and-proj-tabs.png?version=3&modificationDate=1647771448090&cacheVersion=1&api=v2&width=564&height=206)

*   **Do not display**  –  This tab is not displayed on the **Issue** and **Project** screens for all Jira projects.

*   **Show for all projects**  –  This tab will be displayed on the issue and project screens for all Jira projects.

*   **Show for selected projects**  –  This tab will only be displayed on the issue and project screens on selected projects. Define one or more required projects into the textbox.


* * *

#### **Reverse commit tab sort order**

Turn this setting to `ON` to sort commits in the Git Commits tab from newest (top) to oldest (bottom). Set this to off to sort commits from oldest (top) to newest (bottom). This setting is `ON` by default. On app upgrade, it defaults to `ON`.

This only sets the default sorting of commits when opening/loading the Git Commits tab.

* * *

**Commits limit**

_Required_. Set the maximum number of commits to display on the Jira issue Git Commits tab. The default setting is **20**.

Increasing this value impacts Jira display performance.

