---

title: Jira project page
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Project page allows you to manage project related options.

### All Versions

History of commits can also be viewed within the whole project scope. To do this, select a project then click the Git Commits tab. The format of commits is similar to that on the issue page.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399252/gitserver-proj-git-commits-tab.png?version=1&modificationDate=1630642928218&cacheVersion=1&api=v2)

To view commit code diff information, click the **View full commit** button to the right of the commit message.

To view code diff information of the particular file, click the filename for each file adjacent to the rollup counter markers.

Click on the issue name of the commit to open it with the Repository Browser. Related commits for that issue name are displayed.

Click on a commit ID to open it with the Repository Browser. Related issues and commits for that GUID are displayed.

The Git Commits tab displays a notification when no commits are present.

If Repository Browser setting is disabled for that project, the user will not be able to view files for commit from any repositories associated with that project.

## Commits for Select Version

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399252/gitserver-proj-select-versions-tab.png?version=1&modificationDate=1630642928449&cacheVersion=1&api=v2)

Commits can also be limited using a particular revision. Revision and commits are connected using the logic below:

*   All issues linked with particular revision are selected (using both ‘fix version’ and ‘affects version’ fields).

*   Commits linked with these tickets are fetched.


[« Git tags](/git-integration-for-jira-self-managed/Git-tags)

[Reindexing »](/git-integration-for-jira-self-managed/Reindexing)