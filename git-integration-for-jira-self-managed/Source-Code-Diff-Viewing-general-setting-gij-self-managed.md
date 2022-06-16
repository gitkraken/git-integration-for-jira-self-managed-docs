---

title: Source Code Diff Viewing general setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
For detailed information on this feature, see [Documentation: Viewing commit code diffs](/git-integration-for-jira-self-managed/viewing-commit-code-diffs-gij-self-managed).

VERSION 3.8.1 Git Integration for Jira adds three new settings in the General settings configuration page:

*   Repository Browser

*   Source Code Diff Viewing (this page)

*   Require user personal access tokens for branch and PR/MR creation


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1947140173/gitserver-gencfg-code-diff.png?version=1&modificationDate=1631802604022&cacheVersion=1&api=v2&width=442&height=90)

[Source Code Diff Viewing](/git-integration-for-jira-self-managed/source-code-diff-viewing-general-setting-gij-self-managed) allows users to view source code commit diffs inside Jira:

*   Jira issues ➜ Git Commits tab

*   Jira issues ➜ Git Roll Up tab

*   Repository Browser ➜ file source code diff

*   Repository Browser ➜ Compare tab



The default setting is `Enabled` for new and existing Git Integration for Jira app installations. This setting is retained on restore/upgrade of the app.

If this setting is disabled (_unchecked_) in General settings, the above locations will not show the code diff or is not accessible to view to users. This also overrides repository and integration settings, by changing them to `Disabled`.

