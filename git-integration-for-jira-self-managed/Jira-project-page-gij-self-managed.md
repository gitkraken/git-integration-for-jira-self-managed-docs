---

title: Jira project page
description: "View the Git Commits tab on a Jira project page to browse commit history across the project or for a selected version, and open code diffs."
product: Git Integration for Jira Data Center
feature: Git Commits Tab
content_type: how-to
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [jira project page, git commits tab, versions, code diff, repository browser]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Jira project page"
    nav_order: 210
    nav_parent: "documentation-gij-self-managed"
    page_type: "content"
    card_icon: "git-commit"
    card_color: "blue"
    card_description: "View the Git Commits tab on a Jira project page to browse commit history across the project or for a selected version, and open code diffs"
---

The Project page allows you to manage project related options.

&nbsp;

### All Versions

History of commits can also be viewed within the whole project scope. To do this, select a project then click the Git Commits tab. The format of commits is similar to that on the issue page.

![](/wp-content/uploads/gij-gitserver-proj-git-commits-tab.png)

To view commit code diff information, click the **View full commit** button to the right of the commit message.

To view code diff information of the particular file, click the filename for each file adjacent to the rollup counter markers.

Click on the issue name of the commit to open it with the Repository Browser. Related commits for that issue name are displayed.

Click on a commit ID to open it with the Repository Browser. Related issues and commits for that GUID are displayed.

> **Info:** The Git Commits tab displays a notification when no commits are present.

> **Warning:** If Repository Browser setting is disabled for that project, the user will not be able to view files for commit from any repositories associated with that project.

&nbsp;

### Commits for Select Version

![](/wp-content/uploads/gij-gitserver-proj-select-versions-tab.png)

Commits can also be limited using a particular revision. Revision and commits are connected using the logic below:

*   All issues linked with particular revision are selected (using both ‘fix version’ and ‘affects version’ fields).

*   Commits linked with these tickets are fetched.

&nbsp;
* * *

[**Prev:** Git tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed)

[**Next:** Reindexing](/git-integration-for-jira-data-center/reindexing-gij-self-managed)


