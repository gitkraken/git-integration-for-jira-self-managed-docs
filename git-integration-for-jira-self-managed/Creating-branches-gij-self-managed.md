---

title: Creating branches
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
        <b>Jira administrator notes</b>
        <ul>
            <li>
                Jira users can be required to provide their own Personal Access Token when creating a branch or pull request. See <a href='/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed'>Require Personal Access Tokens for user actions (create branch/pull request)</a> for instructions on how to configure this feature.
            </li>
            <li>
                The <b>View developer tools</b> <i>permission</i> is required to view the Source Code panel (see more in <a href='/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed'>Jira issue Git integration development panel</a>. Jira users must also have the <b>Browse Project</b> <i>permissions</i> to a project associated with a repository to view.
            </li>
            <li>
                The Create branch feature can be disabled for all Jira users (regardless of permissions) in <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'>General settings</a>.
            </li>
        </ul>
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

The Create branch feature offers Jira users the ability to create a git branch directly from the Jira issue.

<img src='/wp-content/uploads/gij-dev-panel-create-branch-dlg-c.png' width=603 height=302 style='display:block;margin:25px auto;max-width:100%' />

For information about creating pull/merge requests from a Jira issue - see article [Creating pull/merge request](/git-integration-for-jira-data-center/create-pull-merge-requests-gij-self-managed).

## Advantages

When creating a branch from within Jira:

*   Automatically populates branch name with issue key (necessary for branch **⇿** Jira issue association) and issue summary.

*   Further – default branch naming conventions can be customized to match your development workflow.

    For example:<br>
    `${issuetype:New Issue,new,Bug Fix,bug}/${issuekey}-${summary}` generates `bug/PRJ-123-add-more-logging`

    See [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed) for more information.

*   Require each Jira user to provide their Personal Access Token for creating branches. This option adds some friction to creating branches/pull requests but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions.

    For more information, see [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) for more information.


## Supported platforms

*   Full feature (Auto-Connect) integrations:

    *   GitHub

    *   GitLab

    *   AWS CodeCommit

    *   Azure DevOps

    *   Microsoft Visual Studio Team Services (VSTS)

    *   Microsoft Team Foundation Server (TFS)


## Steps to creating a git branch in Jira

1.  **Prerequisite:** Jira administrator configures a a full feature integration (auto-connect) via Add new integration panel in the Git Integration for Jira Data Center app. See [Integration Guides](/git-integration-for-jira-data-center/integration-guides-gij-self-managed) for more information.

2.  To access the Create branch action, do one of the following:

    1.  Open/expand the [Git Development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed).

    2.  If not visible or displayed, enable in [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed).

3.  Click **Create branch** in one of the panels from step 2.

4.  Select git repository. Use the search box to look for the specific name of the repository that will be used.

5.  If a [personal access token is required](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) (and not yet provided) – follow on screen instructions to provide a [personal access token](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed) with correct permissions for selected repository.

6.  Select base branch.

7.  Verify branch name is correct. Edit as desired.
    **Note:** The Jira issue key must remain in the branch name to create the branch **⇿** Jira issue association.

8.  Click **Create branch**.

<br>

### Video: Creating branch via Git Development panel

**(UPDATED VIDEO COMING SOON)**

<div class='embed-container' style='padding-bottom: 82.08%'>
    <iframe width='709' height='582' src='https://fast.wistia.com/embed/iframe/8cy7v6ykug?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div style='text-align: center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/8cy7v6ykug'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i><br>
    <i>The video shows Git Integration for Jira Cloud process but is also <br>applicable to the Jira Server version.</i>
</div>
<br>

If you still have a question - reach out to our [Support Desk](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/) or email us at [support@gitkraken.com](mailto:support@gitkraken.com).

