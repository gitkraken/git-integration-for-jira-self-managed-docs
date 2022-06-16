---

title: Git integration features
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This setting is part of the [General Settings](/git-integration-for-jira-self-managed/general-settings-gij-self-managed) configuration page.


These group of settings affect how new commits are updated, how tags are displayed on Jira issues, and give administrators control if commit information is shown on JQL searches and Git activity stream or not.

VERSION 3.9+ GitKraken deep linking integration is implemented.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795905/gitserver-gencfg-git-integration-options.png?version=1&modificationDate=1647771632980&cacheVersion=1&api=v2&width=564&height=334)

**Settings index:**

* * *

## GitKraken integration

Enable/disable GitKraken deep linking feature on Jira issue development panel and Git Commit tab. Clicking the deep links opens the respective commit, branches and repositories with GitKraken git client. For more information on this feature, see [Deep linking to the GitKraken client](/git-integration-for-jira-self-managed/deep-linking-to-the-gitkraken-git-client-gij-self-managed).

## Jira issue updates

Enable/disable the setting to allow new commits to change the _Last Updated_ field.  Default is _**enabled**_.  For more information about this setting, see section [Reindexing – Reindex and updatedDate Filter](/git-integration-for-jira-self-managed/reindexing-gij-self-managed).

Disabling this setting will improve Jira performance.

## Issue git integration panel

**Show Git integration panel on issue pages**  –  Enable/disable this setting to have Git Integration for Jira app show/hide the _Git Integration_ section on the Jira issue developer panel.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207795905/jira-issue-dev-panel.png?version=2&modificationDate=1632661767019&cacheVersion=1&api=v2)

For more information, see [Jira git integration development panel](/git-integration-for-jira-self-managed/jira-git-integration-development-panel-gij-self-managed).

Disabling this setting will improve Jira performance.


**Calculate and show Git tags in the Git integration panel**  –  Enable/disable the setting to have Git Integration for Jira app calculate and show the Git tags in the Git Integration panel.

For more information, see [Git Tags](/git-integration-for-jira-self-managed/git-tags-gij-self-managed).

Disabling this setting will improve Jira performance.

## JQL searching

INTRODUCED 2.12.0+

Enables/disables the ability to use the JQL functions within the Git Integration for Jira app.

The default state for new Git for Jira app installation is **Enabled**. This setting will be automatically enabled when doing an upgrade from previous versions of the Git Integration for Jira app.

For more information, see [JQL searching](/git-integration-for-jira-self-managed/jql-searching-gij-self-managed).

Disabling this setting will improve Jira performance.

## Git activity stream

Enable/disable the setting whether to show git commits in the Jira activity stream (Issue page or dashboard widget) or not.

For in-place upgrade of the Git Integration for Jira app, this setting is turned _off_ by default.  For new installation, the default state is enabled.

Only the commits that are [linked to Jira issues](/git-integration-for-jira-self-managed/linking-git-commits-to-jira-issues-gij-self-managed) will show on the Jira Activity Stream (not all commits in repositories).

Disabling this setting will improve Jira performance.

