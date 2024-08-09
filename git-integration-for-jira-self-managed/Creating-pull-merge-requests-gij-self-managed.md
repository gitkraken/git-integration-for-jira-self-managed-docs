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

<div align='center' style='margin-top:10px;margin-bottom:30px;'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rsccl5wxps'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
    <p>The video shows Git Integration for Jira Cloud process but is also applicable to the Jira Server version.</p>
</div>

If you still have a question – reach out to our [Support Desk](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/) or email us at [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com).

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

## See more Git Integration for Jira app features

[Indexing queue viewer](/git-integration-for-jira-data-center/Indexing-queue-viewer-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking to the GitKraken Git client](/git-integration-for-jira-data-center/Deep-Linking-to-the-GitKraken-Git-client-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Deep Linking into GitLens](/git-integration-for-jira-data-center/Deep-Linking-into-GitLens-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Git Integration + Jira Automation (Jira Server \| DC)](/git-integration-for-jira-data-center/Git-integration-plus-Jira-automation-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Creating branches](/git-integration-for-jira-data-center/Creating-branches-gij-self-managed) (Git Integration for Jira Server/Data Center)

**Creating pull/merge requests** (this page)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/Associate-Pull-Merge-Requests-to-Issues-Based-on-Commits-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Issue Git integration panel](/git-integration-for-jira-data-center/Issue-Git-integration-panel-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/Smart-commits-overview-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/Shared-reindex-queue-between-DC-nodes-gij-self-managed) (Git Integration for Jira Server/Data Center)

[Enforced git permissions for Jira users](/git-integration-for-jira-data-center/Enforced-git-permissions-for-Jira-users-gij-self-managed) (Git Integration for Jira Server/Data Center)

