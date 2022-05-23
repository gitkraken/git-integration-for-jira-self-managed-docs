---

title: Working with Tracked folders
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
JIRA SERVER JIRA DATA CENTER

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396479/gitserver-gitcfg-connect2git-menu-add-tracked-folder.png?version=1&modificationDate=1630642795837&cacheVersion=1&api=v2&width=680&height=303)

This feature scans a locally accessible path for cloned Git repositories and automatically imports those Git repository references into Jira. A repository group called FOLDER is added in the Git Integration for Jira app repository settings.

The _**add tracked folder**_ feature requires that Jira and the git servers must be on the same filesystem.  Make sure that the user that Jira is running with has access permissions to the path with the git repositories.

The Tracked Folder feature helps save disk space in case of a mounted folder. Thus, improving Jira performance.

If you have a local folder that contains multiple repositories, the Git Integration for Jira app will auto-detect and connect this folder to Jira as a tracked folder.

For more information about this feature, see [Integration guide - Adding tracked folders](/git-integration-for-jira-self-managed/Tracked-Folders).

[« Increasing timeout threshold for large repositories while doing a Git pull](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull)

[Recommended upgrade method for Git Integration for Jira »](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira)

