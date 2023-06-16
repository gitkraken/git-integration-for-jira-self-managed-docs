---

title: Jira project page
description:
taxonomy:
    category: git-integration-for-jira-data-center

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

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Commits tab displays a notification when no commits are present.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If Repository Browser setting is disabled for that project, the user will not be able to view files for commit from any repositories associated with that project.
    </div>
    </div>
</div>

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


