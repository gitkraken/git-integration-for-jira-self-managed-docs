---

title: Branches (Development panel)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The **Branches** section lists the branches names, linking the selected branch to view via the Repository Browser.

The branch is displayed on the developer panel and is also associated to the mentioned Jira issue by fulfilling one of the following conditions:

*   The **branch name** contains the issue key. For example, `TEST-1-fix-binaries`.

*   The branch has associated unmerged commits with the issue key in the comments. For example, `TEST-1 fixed-binaries`.


The branch panel will show a summary of all the unmerged branches (regardless of the number of commits and the number of repositories) -- that either contain the name of the issue or have unmerged commits that reference the issue. This also gives users a view into the behind/ ahead status and provide links to the Repository Browser for those branch names.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For example, <code>TST-1-new-branch</code> branch will be visible on the developer panel of the <b>TST-1</b> issue page even if the <code>TST-1-new-branch</code> branch has just been forked from master and does not have any new commit.
    </div>
    </div>
</div>

## Create branch

Click **Create branch** to create a branch for the selected repository. The following dialog is displayed:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399090/dev-panel-create-branch-dlg(c).png?version=1&modificationDate=1630642920515&cacheVersion=1&api=v2&width=544&height=272)

1.  Select a **Repository**.<br>
    
    **GITHUB** &nbsp; If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.<br>

    **GITLAB** &nbsp; If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, `johnsmith/second-webhook-test-repo`.

2.  Set **Base branch** and **Branch name**.

3.  The Git Integration for Jira app will populate the **Branch name** field according to the _Branch Name Template_ declared in the [Git integration settings](/git-integration-for-jira-data-center/git-integration-features/) via **General Settings**. Enter a descriptive name or leave it as is (recommended).

## Create branch (Require user PAT enabled)

If the [Require User PAT option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request/) is enabled in the **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399090/gitserver-create-branch-req-user-pat-enabled.png?version=3&modificationDate=1630669620374&cacheVersion=1&api=v2&width=550&height=276)

*   Click the link label to setup the PAT. This will immediately open the Setup personal access dialog and the user should enter a valid PAT to continue creating branches.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399090/gitserver-setup-your-user-pat-dlg-new(c).png?version=1&modificationDate=1630668474897&cacheVersion=1&api=v2&width=578&height=318)

    *   Paste a valid PAT of the current user to proceed. Invalid PATs will fail the branch creation process.

    *   Click **Update** to use this PAT and save it to the current user profile. Otherwise, click **Cancel** to discard setting up PAT for this repository.

    *   After the above steps have been taken, the users will be able to proceed with branch creation.

<br>

The Setup PAT dialog can also be accessed on the Repository Browser under _**Pers. Access**_ column. This will display connected git repositories and which repositories have **Required User PAT** feature enabled..

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399090/gitserver-repo-browser-setup-pat-highlight.png?version=1&modificationDate=1630669274634&cacheVersion=1&api=v2&width=680&height=381)

*   Click <img  src='/wp-content/uploads/gij-edit-icon-dark.png'  style='vertical-align: middle; margin: 0 3px' width=20 height=20> to setup a PAT for the selected repository. The PAT setup dialog appears.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399090/gitserver-setup-your-user-pat-dlg-new(c).png?version=1&modificationDate=1630668474897&cacheVersion=1&api=v2&width=544&height=300)
*   Paste a valid PAT of the current user to proceed. Invalid PATs will fail the branch creation process.

*   Click **Update** to use this PAT and save it to the current user profile. Otherwise, click **Cancel** to discard setting up PAT for this repository.

*   After the above steps have been taken, the users will be able to proceed with branch creation.

*   The adjacent checkmark indicates that the repository has configured PAT.

<br>

Click **Create branch** on the Create Branch dialog. The newly-created branch is now listed in the developer panel under **Branches**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399090/dev-panel-delete-branch-on-hover.png?version=1&modificationDate=1630642921461&cacheVersion=1&api=v2&width=319&height=157)

Hover the mouse pointer on the branch label to reveal the **Delete** icon. Click this icon to remove the created branch from the Branch list. This action will also delete it from the repository in which it was created.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This feature is available on connected GitLab and GitHub git hosts for Jira Server; GitLab, GitHub, Microsoft TFS/VSTS and AWS CodeCommit git hosts for Jira Cloud.
    </div>
    </div>
</div>
<br>

## Commits ahead and behind

The numbers **ahead** and **behind** represent the number of commits that are ahead/behind the main branch:

*   **Ahead**  –  number of commits in the branch which are not merged to the main branch.

*   **Behind**  –  number of commits in the main branch which are not merged to the branch.


Clicking on the branch text links will open that issue in the Repository Browser. If Repository Browser is disabled for this repository, the text links will be inactive.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <b>Branches</b> section is only visible if commits from this branch are not merged to the <b><i>main branch</i></b>. It's also not displayed if the repository is not associated with a project.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the user does not have the <b>View Development Tools</b> <i>project permission</i> for the project, the developer panel will be unavailable for that user.
    </div>
    </div>
</div>
<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For detailed information about creating branches, see article <a href='/git-integration-for-jira-data-center/Creating-branches/'>Creating branches</a>.
    </div>
    </div>
</div>

