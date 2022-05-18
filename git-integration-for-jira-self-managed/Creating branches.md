---

title: Creating branches
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
**Jira administrator notes**

*   Jira users can be required to provide their own Personal Access Token when creating a branch or pull request. See [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849) for instructions on how to configure this feature.

*   The **View developer tools** _permission_ is required to view the Source Code panel (see more in [Jira issue Git integration development panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel)). Jira users must also have the **Browse Project** _permissions_ to a project associated with a repository to view.

*   The Create branch feature can be disabled for all Jira users (regardless of permissions) in [General settings](/wiki/spaces/GIJDC/pages/966852655/General+Settings).


**Feature note**
This feature is not available to single repository connections.

## Introduction

The Create branch feature offers Jira users the ability to create a git branch directly from the Jira issue.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1932460323/dev-panel-create-branch-dlg(c).png?version=1&modificationDate=1630669954218&cacheVersion=1&api=v2&width=544&height=272)

For information about creating pull/merge requests from a Jira issue - see article [Creating pull/merge request](/wiki/spaces/GITSERVER/pages/1923029639).

## Advantages

When creating a branch from within Jira: 

*   Automatically populates branch name with issue key (necessary for branch **⇿** Jira issue association) and issue summary.

*   Further – default branch naming conventions can be customized to match your development workflow.
    For example: `${issuetype:New Issue,new,Bug Fix,bug}/${issuekey}-${summary}` generates "`bug/PRJ-123-add-more-logging`" (See [General settings](/wiki/spaces/GIJDC/pages/966852655/General+Settings) for more information).

*   Require each Jira user to provide their Personal Access Token for creating branches. This option adds some friction to creating branches/pull requests but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions. For more information, see [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849) for more information.


## Supported platforms

*   Full feature (Auto-Connect) integrations:

    *   GitHub

    *   GitLab

    *   AWS CodeCommit

    *   Azure DevOps

    *   Microsoft Visual Studio Team Services (VSTS)

    *   Microsoft Team Foundation Server (TFS)


## Steps to creating a git branch in Jira

1.  **Prerequisite:** Jira administrator configures a a full feature integration (auto-connect) via Add new integration panel in the Git Integration for Jira Data Center app. See [Integration Guides](/wiki/spaces/GIJDC/pages/92176395/Integration+Guides) for more information.

2.  To access the Create branch action, do one of the following:

    1.  Open/expand the [Git Development panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel).

    2.  If not visible or displayed, enable in [General settings](/wiki/spaces/GIJDC/pages/1207828745).

3.  Click **Create branch** in one of the panels from step 2.

4.  Select git repository. Use the search box to look for the specific name of the repository that will be used.

5.  If a [personal access token is required](/wiki/spaces/GIJDC/pages/317390849) (and not yet provided) – follow on screen instructions to provide a [personal access token](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens) with correct permissions for selected repository.

6.  Select base branch.

7.  Verify branch name is correct. Edit as desired.
    **Note:** The Jira issue key must remain in the branch name to create the branch **⇿** Jira issue association.

8.  Click **Create branch**.


### Video: Creating branch via Git Development panel ( UPDATED VIDEO COMING SOON )

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/8cy7v6ykug) _to open this video in a new tab/window for more viewing options._

_The video shows Git Integration for Jira Cloud process but is also applicable to the Jira Server version._

If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com).