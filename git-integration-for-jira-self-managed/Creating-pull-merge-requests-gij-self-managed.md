---

title: Features - Creating pull/merge requests
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Jira administrator notes</b><br>
        <ul>
            <li>
                Jira users can be required to provide their own Personal Access Token when creating a branch or pull request. See <a href='/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed'>Require Personal Access Tokens for user actions (create branch/pull request)</a> for instructions on how to configure this feature.
            </li>
            <li>
                The <b>View developer tools</b> <i>permission</i> is required to view the Git integration development panel (see more in <a href='/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed'>Jira Issue Git integration development panel</a>). Jira users must also have the <b>Browse Project</b> <i>permissions</i> to a project associated with a repository to view.
            </li>
            <li>
                Creating pull/merge request feature can be disabled for all Jira users (regardless of permissions) in <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'>General settings</a>.
            </li>
        </ul>
    </div>
    </div>
</div>
<br>

<hr>

<br>
<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>GitLab note</b><br>
        GitLab uses the term Merge Request rather than Pull Request (used by the other major git services). In the following article, Pull Request and Merge Request can be used interchangeably.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Feature note</b><br>
        This feature is not available to single repository connections.
    </div>
    </div>
</div>
<br>

## Introduction

The **Create pull/merge request** feature offers Jira users the ability to create a git pull request directly from the Jira issue.

<img src='/wp-content/uploads/gij-gitserver-create-pull-merge-req-dlg.png' width=603 height=313 style='display:block;margin:25px auto;max-width:100%' />

For information about creating a branch from a Jira issue, see [Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed).

## Advantages

When creating a pull request from within Jira:

*   Automatically populates the pull request title with issue key (necessary for pull request **⇿** Jira issue association) and issue summary.

*   Require each Jira user to provide their [Personal Access Token](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed) for creating pull requests. This option adds some friction to creating pull requests/branches but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions. See [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) for more information.


## Supported platforms

*   Full feature (Auto-connect) integrations:

    *   GitHub

    *   GitLab

    *   AWS CodeCommit

    *   Azure DevOps

    *   Microsoft Visual Studio Team Services (VSTS)

    *   Microsoft Team Foundation Server (TFS)


## Steps to creating a git pull request in Jira

1.  **Prerequisite:** Jira administrator configures a full feature (auto-connect) integration in the Git Integration for Jira Data Center app. See [Integration guides](/git-integration-for-jira-data-center/integration-guides-gij-self-managed) for more information.

2.  To access the Create pull request action, do one of the following:

    1.  Open/expand the [Jira issue Git development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed).

    2.  If not visible or displayed, enable in [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed).

3.  Click **Create pull request** in one of the panels from step 2.

4.  Select git repository. Use the search box to look for the specific name of the repository that will be used.

5.  If a [personal access token is required](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) (and not yet provided) – follow on screen instructions to provide a [personal access token](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed) with correct permissions for selected repository.

6.  Select source branch.

7.  Select target branch.

8.  Verify pull request title is correct. Edit as desired.
    **Note:** the Jira issue key must remain in the pull request name to create the pull request **⇿** Jira issue association.

9.  Click **Create**.


### Video: Creating pull/merge request from Git integration development panel ( UPDATED VIDEO COMING SOON )

<br>
<div class='embed-container' style='padding-bottom: 77.71%'>
    <iframe width='709' height='551' src='https://fast.wistia.com/embed/iframe/rsccl5wxps?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rsccl5wxps'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
    <p>The video shows Git Integration for Jira Cloud process but is also applicable to the Jira Server version.</p>
</div>
<br>

If you still have a question – reach out to our [Support Desk](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/) or email us at [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com).

