---

title: Discard cloned files in Jira Home directory (General setting)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396547/gitserver-discard-cloned-files-gencfg.png?version=1&modificationDate=1630642798827&cacheVersion=1&api=v2)

This feature will reduce Jira server storage by deleting files from cloned git repositories after indexing.  Discarding files can save disk space but may limit some features such as displaying diffs of files.

Access this feature via Jira dashboard menu Git ➜ Manage repositories ➜ **General settings** (sidebar). Alternatively, go to Jira dashboard menu – ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ Applications ➜ **General settings** (sidebar).

There are three options to choose from:

*   **Keep all cloned binary files. No storage savings. All features available.** This option will leave all cloned repositories intact.

*   **Discard all files that match the mask below. Some features limited.** This option will delete all files in the cloned repositories matching the declared file extensions.

*   **Discard all files EXCEPT those that match the mask below. Some features limited.** This option will delete all other files in the cloned repositories except those files with extensions declared.


Select any option with the _discard_ label to enable editing of the file mask field.

For full list of features, version history and supported Jira version of the Git for Jira app, see [**Git Integration for Jira app Version History**](https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions).

Whenever the setting is changed, BigBrassBand recommends to perform a manual re-clone of the repositories to ensure an error-free operation.
