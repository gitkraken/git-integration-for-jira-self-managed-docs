---

title: Git integration features
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This setting is part of the [General Settings](/git-integration-for-jira-self-managed/General-Settings) configuration page.


These group of settings affect how new commits are updated, how tags are displayed on Jira issues, and give administrators control if commit information is shown on JQL searches and Git activity stream or not.

VERSION 3.9+ GitKraken deep linking integration is implemented.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795905/gitserver-gencfg-git-integration-options.png?version=1&modificationDate=1647771632980&cacheVersion=1&api=v2&width=564&height=334)

**Settings index:**

* * *

## GitKraken integration

Enable/disable GitKraken deep linking feature on Jira issue development panel and Git Commit tab. Clicking the deep links opens the respective commit, branches and repositories with GitKraken git client. For more information on this feature, see [Deep linking to the GitKraken client](/wiki/spaces/GIJDC/pages/1955430423/Deep+Linking+to+the+GitKraken+Git+client).

## Jira issue updates

Enable/disable the setting to allow new commits to change the _Last Updated_ field.  Default is _**enabled**_.  For more information about this setting, see section [Reindexing – Reindex and updatedDate Filter](/git-integration-for-jira-self-managed/Reindexing).

Disabling this setting will improve Jira performance.

## Issue git integration panel

**Show Git integration panel on issue pages**  –  Enable/disable this setting to have Git Integration for Jira app show/hide the _Git Integration_ section on the Jira issue developer panel.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207795905/jira-issue-dev-panel.png?version=2&modificationDate=1632661767019&cacheVersion=1&api=v2)

For more information, see [Jira git integration development panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel).

Disabling this setting will improve Jira performance.


**Calculate and show Git tags in the Git integration panel**  –  Enable/disable the setting to have Git Integration for Jira app calculate and show the Git tags in the Git Integration panel.

For more information, see [Git Tags](/git-integration-for-jira-self-managed/Git-tags).

Disabling this setting will improve Jira performance.

## JQL searching

INTRODUCED 2.12.0+

Enables/disables the ability to use the JQL functions within the Git Integration for Jira app.

The default state for new Git for Jira app installation is **Enabled**. This setting will be automatically enabled when doing an upgrade from previous versions of the Git Integration for Jira app.

For more information, see [JQL searching](/git-integration-for-jira-self-managed/JQL-searching).

Disabling this setting will improve Jira performance.

## Git activity stream

Enable/disable the setting whether to show git commits in the Jira activity stream (Issue page or dashboard widget) or not.

For in-place upgrade of the Git Integration for Jira app, this setting is turned _off_ by default.  For new installation, the default state is enabled.

Only the commits that are [linked to Jira issues](/wiki/spaces/GIJDC/pages/1930398265/Linking+git+commits+to+Jira+issues) will show on the Jira Activity Stream (not all commits in repositories).

Disabling this setting will improve Jira performance.

* * *

### More on general settings

*   Page:

    [Git roll up issue tab](/wiki/spaces/GIJDC/pages/1207828678/Git+roll+up+issue+tab) (Git Integration for Jira Data Center)

*   Page:

    [Git commits issue and project tabs](/wiki/spaces/GIJDC/pages/1207828697/Git+commits+issue+and+project+tabs) (Git Integration for Jira Data Center)

*   Page:

    [Git integration features](/wiki/spaces/GIJDC/pages/1207795905/Git+integration+features) (Git Integration for Jira Data Center)

*   Page:

    [Branch and pull request settings (formerly Git Integration Options)](/wiki/spaces/GIJDC/pages/1207828745) (Git Integration for Jira Data Center)

*   Page:

    [Email settings](/git-integration-for-jira-self-managed/Email-settings) (Git Integration for Jira Data Center)

*   Page:

    [Scheduled jobs](/git-integration-for-jira-self-managed/Scheduled-jobs) (Git Integration for Jira Data Center)

*   Page:

    [Audit log settings](/wiki/spaces/GIJDC/pages/1207828866/Audit+log+settings) (Git Integration for Jira Data Center)

*   Page:

    [General settings](/git-integration-for-jira-self-managed/General-settings) (Git Integration for Jira Data Center)

*   Page:

    [Repository Browser general setting](/wiki/spaces/GIJDC/pages/1947140158/Repository+Browser+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Source Code Diff Viewing general setting](/wiki/spaces/GIJDC/pages/1947140173/Source+Code+Diff+Viewing+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Require User PAT general setting](/wiki/spaces/GIJDC/pages/1947107395/Require+User+PAT+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Enable Automation for Jira general setting](/wiki/spaces/GIJDC/pages/2045149338/Enable+Automation+for+Jira+general+setting) (Git Integration for Jira Data Center)

*   Page:

    [Enforce Git service permissions](/wiki/spaces/GIJDC/pages/2091810842/Enforce+Git+service+permissions) (Git Integration for Jira Data Center)

*   Page:

    [Per Node Repository Indexing](/wiki/spaces/GIJDC/pages/2095775749/Per+Node+Repository+Indexing) (Git Integration for Jira Data Center)