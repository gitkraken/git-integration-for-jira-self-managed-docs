---

title: Repository Browser
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The **Repository Browser** allows users to view git repositories of configured projects via the **Git** menu on the Jira dashboard or on the **Applications** sidebar.

## Getting started

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Permissions</b><br>
        Users must have the <b>View Development Tools</b> <i>project permission</i> in order to gain access to the Repository Browser. For more information on assigning Jira permissions, see <a href='https://confluence.atlassian.com/display/Jira/Managing+Global+Permissions' target='_blank'><b>Managing Permissions in Jira</b></a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Git menu</b><br>
        After installing the Git Integration for Jira app, the <b>Git</b> dropdown menu is added to the dashboard.
        <div class='nextpara'>
            The <b>Git</b> header is hidden for all users if there are no repositories with Repository Browser enabled for that user. The Git Integration for Jira app will always show the <b>Git</b> header to Jira administrators.
        </div>
        <div class='nextpara' style='margin-bottom:0px !important'>
            The <b>Git</b> header is visible to other users who have repositories with Repository Browser enabled and have no history of using the Repository Browser (<i>for example -- no previously viewed or repositories set as favorite</i>).
        </div>
    </div>
    </div>
</div>
<br>

<img src='/wp-content/uploads/gij-gitserver-gitmenu-repo-browser.png' width=163 height=111 style='display:block;margin:25px auto;max-width:100%' />

<br>

## Repository list

Available git repositories of configured projects are displayed.

![Repository browser screen showing list of connected repositories, recent issue, last updated by, last commit and personal access (if require PAT setting is enabled).](/wp-content/uploads/gij-gitserver-repo-browser-view.png)

*   Use the search bar to search and filter the Repositories list.

*   On the list table, you will see git repositories, recent issues updated by the user, and the last commits made.

*   The personal access token configuration column (_Pers. Access_) displays the PAT setup option if require user pat setting is enabled). Click the <img src='/wp-content/uploads/gij-edit-icon-dark.png' /> edit icon to setup PAT to allow branch and PR/MR creation functions via [Jira Git integration development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed). The adjacent checkmark indicates a PAT has already been configured.

*   On the bottom left of the list, the view options control how many rows the list will display. The default view is 10 rows. Larger row view affects page loading time.

*   On the right of the view options are the pagination options. Use the controls to navigate through the page list.


## Repository view

Click a git repository under Git repository column to browse its contents and switch to repository view. For example:

<img src='/wp-content/uploads/gij-repo-browser-repo-view-c.png' style='display:block;margin:25px auto;max-width:100%' />

*   Clicking **Repositories** at the top right of the screen will open the git app repositories page.

*   Select a branch from the dropdown list to browse repository contents for that branch _(default view is master branch)_.

*   Click a folder to view its contents. Click a file to view its code diff.

*   Click on an issue link under **Commit message** to view that ticket.

*   Click on the  **Latest commit: UUID** link to view code diff for that commit.

*   Click on an item link under **Latest commit** _column_ to view code diff for that particular commit.

*   Clicking on the **Repositories** button at the top right of the page returns the view to the Repository Browser.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Commit revisions</b><br>
        The revisions of the commits are displayed on the Repository Browser in addition to branches and tags. See <a href='/git-integration-for-jira-data-center/viewing-list-of-commits-in-repository-browser-gij-self-managed'>Repository Browser - Git Commits tab</a> for detailed information.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the selected path is a <b><i>root</i></b> of the repository and no files are present, a message will be displayed instead of an empty file list.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Administration</b><br>
        Administrators can turn off the Repository Browser via &nbsp;<img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit repository settings</b> in the Git Integration for Jira app configuration.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Sort header</b><br>
        The displayed repositories can be sorted by clicking the corresponding list header. The Git Integration for Jira app will remember the sorting choice per user.
    </div>
    </div>
</div>
<br>

<br>
<br>

[**Prev:** Smart commits](/git-integration-for-jira-data-center/smart-commits-gij-self-managed)

[**Next:** Viewing list of commits via Repository Browser](/git-integration-for-jira-data-center/viewing-list-of-commits-in-repository-browser-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More articles on Repository browser

[Viewing list of commits in Repository Browser](/git-integration-for-jira-data-center/viewing-list-of-commits-in-repository-browser-gij-self-managed)

[Comparing branches/tags in Repository browser](/git-integration-for-jira-data-center/comparing-branches-tags-in-repository-browser-gij-self-managed)

[Enable/disable Repository Browser via git repository configuration page](/git-integration-for-jira-data-center/enable-disable-repository-browser-via-git-repository-configuration-page-gij-self-managed)


