---

title: Diff settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This setting is part of the [**General Settings**](/git-integration-for-jira-self-managed/general-settings-gij-self-managed) configuration page.

VERSION 4.0.1+ This setting is now moved to the **Advanced settings** in General settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795993/gitserver-gencfg-adv-diff-count-encoding.png?version=1&modificationDate=1647775224812&cacheVersion=1&api=v2&width=680&height=159)

## Max diff line count

Set the maximum size of diffs that is allowed to be displayed in the diff dialog.  Setting this option to a higher value will affect diff display performance.

## File encoding

While the Git for Jira app uses default Jira System Encoding (utf-8) to deliver source files and diffs of repository, this setting is for those who have several repositories with source files encoded under different encodings.

For now, the diff encoding option accepts only one encoding type (utf-8).  Several encodings aren't supported yet.

