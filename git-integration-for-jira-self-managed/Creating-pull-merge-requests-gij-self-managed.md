---

title: Features - Creating pull/merge requests
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
**Jira administrator notes**

*   Jira users can be required to provide their own Personal Access Token when creating a branch or pull request. See [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) for instructions on how to configure this feature.

*   The **View developer tools** _permission_ is required to view the Git integration development panel (see more in [Jira Issue Git integration development panel](/git-integration-for-jira-self-managed/jira-git-integration-development-panel-gij-self-managed). Jira users must also have the **Browse Project** _permissions_ to a project associated with a repository to view.

*   Creating pull/merge request feature can be disabled for all Jira users (regardless of permissions) in [General settings](/git-integration-for-jira-self-managed/general-settings-gij-self-managed).


* * *

**GitLab note**
GitLab uses the term Merge Request rather than Pull Request (used by the other major git services). In the following article, Pull Request and Merge Request can be used interchangeably.

**Feature note**
This feature is not available to single repository connections.

## Introduction

The **Create pull/merge request** feature offers Jira users the ability to create a git pull request directly from the Jira issue.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1932460359/gitserver-create-pull-merge-req-dlg.png?version=1&modificationDate=1630670055055&cacheVersion=1&api=v2)

For information about creating a branch from a Jira issue, see [Creating branches](/git-integration-for-jira-self-managed/creating-branches-gij-self-managed).

## Advantages

When creating a pull request from within Jira: 

*   Automatically populates the pull request title with issue key (necessary for pull request **⇿** Jira issue association) and issue summary.

*   Require each Jira user to provide their [Personal Access Token](/git-integration-for-jira-self-managed/creating-personal-access-tokens-gij-self-managed) for creating pull requests. This option adds some friction to creating pull requests/branches but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions. See [Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) for more information.


## Supported platforms

*   Full feature (Auto-connect) integrations:

    *   GitHub

    *   GitLab

    *   AWS CodeCommit

    *   Azure DevOps

    *   Microsoft Visual Studio Team Services (VSTS)

    *   Microsoft Team Foundation Server (TFS)


## Steps to creating a git pull request in Jira

1.  **Prerequisite:** Jira administrator configures a full feature (auto-connect) integration in the Git Integration for Jira Data Center app.  See [Integration guides](/git-integration-for-jira-self-managed/integration-guides-gij-self-managed) for more information.

2.  To access the Create pull request action, do one of the following:

    1.  Open/expand the [Jira issue Git development panel](/git-integration-for-jira-self-managed/jira-git-integration-development-panel-gij-self-managed).

    2.  If not visible or displayed, enable in [General settings](/git-integration-for-jira-self-managed/general-settings-gij-self-managed).

3.  Click **Create pull request** in one of the panels from step 2.

4.  Select git repository. Use the search box to look for the specific name of the repository that will be used.

5.  If a [personal access token is required](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) (and not yet provided) – follow on screen instructions to provide a [personal access token](/git-integration-for-jira-self-managed/creating-personal-access-tokens-gij-self-managed) with correct permissions for selected repository.

6.  Select source branch.

7.  Select target branch.

8.  Verify pull request title is correct. Edit as desired.
    **Note:** the Jira issue key must remain in the pull request name to create the pull request **⇿** Jira issue association.

9.  Click **Create**.


### Video: Creating pull/merge request from Git integration development panel ( UPDATED VIDEO COMING SOON )

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/rsccl5wxps) _to open this video in a new tab/window for more viewing options._

_The video shows Git Integration for Jira Cloud process but is also applicable to the Jira Server version._

If you still have a question – reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com).