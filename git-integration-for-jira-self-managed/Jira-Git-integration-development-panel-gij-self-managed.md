---

title: Jira Git integration development panel
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This page applies to Git Integration for Jira Server and Jira Data Center.
    </div>
    </div>
</div>

&nbsp;

### Permissions

**Create Branches and Branch Names**<br>
For connected GitHub git host, this feature requires enabled `public_repo` scope permissions.

**Commits Ahead and Behind**<br>
If the user does not have the **View Development Tools** _project permission_ for the project, the developer panel will be unavailable for that user.

### Getting started

The **Refresh** action is available for manually reloading the git information on the Git Integration development panel. Use it to repopulate Git data without reloading the Jira issue page.

<img src='/wp-content/uploads/gij-cloud-jira-git-integration-panel-refresh.png' style='margin:25px auto;max-width:100%;display:block;' />

Git links are now available on the developer panel in the following locations:

*   Issue page
*   Search page in detailed view
*   Jira Agile screen

<img src='/wp-content/uploads/gij-gitserver-new-jira-developer-panel-419.png' style='display:block;margin:25px auto;max-width:100%' />

The **30 commits** refers to an existing Git Commits view, which the issue tab have now. Clicking this text link will reload the page and automatically switches to the **Git Commits** tab to view the commits.

The **Roll Up** refers to an existing Git Roll Up view, which the issue tab have now. Clicking this link will reload the page and automatically switches to the **Git Roll Up** tab to view the git code summary.

Click **Compare code** to open the following dialog:

<img src='/wp-content/uploads/gij-dev-panel-compare-code-dlg.png' width=544 height=285 style='display:block;margin:25px auto;max-width:100%' />

Compare code diff of different branches by performing the following options:

1.  Select a **Repository**.

2.  Set **Compare** branch and **Base** branch.

3.  Click **Compare** to proceed.

The view redirects to the Repository Browser ➜ **Compare** tab showing changes between the compared branches.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The most commonly used name for the main branch is <code>master</code>. For this documentation, the <b><i>master</i></b> branch is also the main branch.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Code syntax highlighter](/git-integration-for-jira-data-center/code-syntax-highlighter-gij-self-managed)

[**Next:** Development panel locations](/git-integration-for-jira-data-center/development-panel-locations-gij-self-managed)

&nbsp;

### More articles on Jira Git integration development panel

[Development panel locations](/git-integration-for-jira-data-center/development-panel-locations-gij-self-managed)

[Branches (Development panel)](/git-integration-for-jira-data-center/Branches-(Development-panel)-gij-self-managed)

[Pull or merge requests (Development panel)](/git-integration-for-jira-data-center/Pull-or-merge-requests-(Development-panel)-gij-self-managed)


