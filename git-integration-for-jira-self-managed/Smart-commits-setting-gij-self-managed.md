---

title: Smart commits setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
JIRA SERVER ONLY JIRA DATA CENTER ONLY

This setting is part of the [**General Settings**](/git-integration-for-jira-self-managed/general-settings-gij-self-managed) configuration page.

VERSION 4.0.1+ This setting is now moved to the **Advanced settings** in General settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207828834/gitserver-gencfg-smart-commits-age.png?version=1&modificationDate=1647775792877&cacheVersion=1&api=v2&width=668&height=99)

**Max commit age**  –  Set a limit (in days) for Smart Commit processing.  Commits older than the _Max commit age_ can be associated to the Jira issue but any Smart Commit commands will not be processed.  This protects against cases where old commits are merged into a new repository.

