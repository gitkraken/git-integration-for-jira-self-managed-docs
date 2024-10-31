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

&nbsp;

### Introduction

The **Create pull/merge request** feature offers Jira users the ability to create a git pull request directly from the Jira issue.

<img src='/wp-content/uploads/gij-gitserver-create-pull-merge-req-dlg.png' width=603 height=313 style='display:block;margin:25px auto;max-width:100%' />

For information about creating a branch from a Jira issue, see [Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed).

&nbsp;

### Advantages

When creating a pull request from within Jira:

*   Automatically populates the pull request title with issue key (necessary for pull request **⇿** Jira issue association) and issue summary.

*   Require each Jira user to provide their [Personal Access Token](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed) for creating pull requests. This option adds some friction to creating pull requests/branches but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions. See [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) for more information.

&nbsp;

### Supported platforms

*   Full feature (Auto-connect) integrations:

    *   GitHub

    *   GitLab

    *   AWS CodeCommit

    *   Azure DevOps

    *   Microsoft Visual Studio Team Services (VSTS)

    *   Microsoft Team Foundation Server (TFS)

&nbsp;

### Steps to creating a git pull request in Jira

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

&nbsp;

### Video: Creating pull/merge request from Git integration development panel ( UPDATED VIDEO COMING SOON )

<br>
<div class='embed-container' style='padding-bottom: 77.71%'>
    <iframe width='709' height='551' src='https://fast.wistia.com/embed/iframe/rsccl5wxps?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px;margin-bottom:30px;'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rsccl5wxps'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
    <p>The video shows Git Integration for Jira Cloud process but is also applicable to the Jira Server version.</p>
</div>

If you still have a question – reach out to our [Support Desk](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/) or email us at [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com).

&nbsp;

### Associating pull/merge request to Jira issue

A git service user can create a PR/MR via the Git host service portal and adding/inserting a Jira issue key in the PR/MR title. This is automatically added to the Pull/Merge request list in the Jira issue Git developer panel.

| Git service portal |
| :---: |
| ![](/wp-content/uploads/gij-gitserverdc-associate-pull-req-example-host.png) |

| Jira issue PR/MR list view |
| :---: |
| ![](/wp-content/uploads/gij-datacenter-assoc-pull-req-dev-panel-list.png) |

| Git service portal draft example |
| :---: |
| ![](/wp-content/uploads/git-datacenter-github-pullreq-draft-example.png)<br><br>GIJ will be supporting the draft PRs for GitHub, GitLab and Azure in the future versions. For example, you can create GitHub draft PRs with a GitHub Org repository. For other supported git services, please see their respective requirements. Please note that the draft pull/merge requests cannot be merged until their state is changed for merging. |

Additionally, creating PR/MR via the Git developer panel automatically associates the PR/MR to a Jira issue. This also adds a description in the PR/MR to the git host service portal containing the link to the Jira issue.

&nbsp;

### Administrators

For users without access to a git repository (like GitHub or GitLab), the "Create Pull/Merge Request" action in the Git Integration panel of a Jira issue will be restricted, preventing the creation of a pull/merge request from Jira. Although users can still click on these integration actions, an error message will appear on the Create PR/MR dialog, preventing any changes.

&nbsp;

### See more Git Integration for Jira app features

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

[Cancel indexing](/git-integration-for-jira-data-center/cancel-indexing-revision-indexing-gij-self-managed/) (Git Integration for Jira Data Center)

[Pull request filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Tag filters](/git-integration-for-jira-data-center/tag-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Indexing queue viewer](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/) (Git Integration for Jira Data Center)

[Deep linking feature](/git-integration-for-jira-data-center/deeplinking-feature-gij-self-managed/) (Git Integration for Jira Data Center)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + ScriptRunner](/git-integration-for-jira-data-center/gij-plus-scriptrunner-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + Jira Automation](/git-integration-for-jira-data-center/git-integration-plus-jira-automation-gij-self-managed/) (Git Integration for Jira Data Center)

[Enforced git permissions for Jira users – Features](/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed/) (Git Integration for Jira Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/shared-reindex-queue-between-dc-nodes-gij-self-managed/) (Git Integration for Jira Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed/) (Git Integration for Jira Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

**Creating pull/merge requests** (this page)

[Issue Git integration panel – Features](/git-integration-for-jira-data-center/issue-git-integration-panel-gij-self-managed/) (Git Integration for Jira Data Center)

