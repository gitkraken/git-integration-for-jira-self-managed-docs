---

title: Working with Tracked folders
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396479/gitserver-gitcfg-connect2git-menu-add-tracked-folder.png?version=1&modificationDate=1630642795837&cacheVersion=1&api=v2&width=680&height=303)

This feature scans a locally accessible path for cloned Git repositories and automatically imports those Git repository references into Jira. A repository group called FOLDER is added in the Git Integration for Jira app repository settings.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <b><i>Add tracked folder</i></b> feature requires that Jira and the git servers must be on the same filesystem. Make sure that the user that Jira is running with has access permissions to the path with the git repositories.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Tracked Folder feature helps save disk space in case of a mounted folder. Thus, improving Jira performance.
    </div>
    </div>
</div>

If you have a local folder that contains multiple repositories, the Git Integration for Jira app will auto-detect and connect this folder to Jira as a tracked folder.

For more information about this feature, see [Integration guide - Adding tracked folders](/git-integration-for-jira-self-managed/tracked-folders/).

* * *

[Previous: Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-self-managed/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull/)

[Next: Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-self-managed/recommended-upgrade-method-for-git-integration-for-jira/)

