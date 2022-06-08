---

title: Repository settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

This setting is part of the [**General Settings**](/git-integration-for-jira-self-managed/General-Settings) configuration page.

VERSION 4.0.1+ This setting is now moved to the **Advanced settings** in General settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795977/gitserver-gencfg-repo-max-open-pack-files.png?version=1&modificationDate=1647774893084&cacheVersion=1&api=v2&width=680&height=97)

## Max open pack files count

Set the maximum number of open files the Git Integration for Jira app uses. For new Git Integration for Jira app install or upgrade, the default value is **16**. This is the **recommended** value.

You may set this value higher but NOT EXCEEDING the maximum number of open files allowed in the system.


The maximum number of open files vary for each operating system you are working with. The same units for each OS is used.

For systems that has a lot of connected repositories, increasing this value to a higher setting may improve the performance of the Git Integration for Jira app -- such as during repository browsing. This is also applicable to very busy systems that has large repository connections. Configure the maximum open files allowed by the system accordingly.

