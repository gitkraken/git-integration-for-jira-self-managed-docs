---

title: Creating pull/merge requests
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
**Jira administrator notes**

*   Jira users can be required to provide their own Personal Access Token when creating a branch or pull request. See [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849) for instructions on how to configure this feature.

*   The **View developer tools** _permission_ is required to view the Git integration development panel (see more in [Jira Issue Git integration development panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel)). Jira users must also have the **Browse Project** _permissions_ to a project associated with a repository to view.

*   Creating pull/merge request feature can be disabled for all Jira users (regardless of permissions) in [General settings](/wiki/spaces/GIJDC/pages/1207828745).


* * *

**GitLab note**
GitLab uses the term Merge Request rather than Pull Request (used by the other major git services). In the following article, Pull Request and Merge Request can be used interchangeably.

**Feature note**
This feature is not available to single repository connections.

## Introduction

The **Create pull/merge request** feature offers Jira users the ability to create a git pull request directly from the Jira issue.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1932460359/gitserver-create-pull-merge-req-dlg.png?version=1&modificationDate=1630670055055&cacheVersion=1&api=v2)

For information about creating a branch from a Jira issue, see [Creating branches](/wiki/spaces/GIJDC/pages/1932460323/Creating+branches).

## Advantages

When creating a pull request from within Jira: 

*   Automatically populates the pull request title with issue key (necessary for pull request **⇿** Jira issue association) and issue summary.

*   Require each Jira user to provide their [Personal Access Token](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens) for creating pull requests. This option adds some friction to creating pull requests/branches but enabling this setting will enforce the git server user permissions as well as give better attribution for the actions. See [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849) for more information.


## Supported platforms

*   Full feature (Auto-connect) integrations:

    *   GitHub

    *   GitLab

    *   AWS CodeCommit

    *   Azure DevOps

    *   Microsoft Visual Studio Team Services (VSTS)

    *   Microsoft Team Foundation Server (TFS)


## Steps to creating a git pull request in Jira

1.  **Prerequisite:** Jira administrator configures a full feature (auto-connect) integration in the Git Integration for Jira Data Center app.  See [Integration guides](/wiki/spaces/GIJDC/pages/92176395/Integration+Guides) for more information.

2.  To access the Create pull request action, do one of the following:

    1.  Open/expand the [Jira issue Git development panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel).

    2.  If not visible or displayed, enable in [General settings](/wiki/spaces/GIJDC/pages/1207828745).

3.  Click **Create pull request** in one of the panels from step 2.

4.  Select git repository. Use the search box to look for the specific name of the repository that will be used.

5.  If a [personal access token is required](/wiki/spaces/GIJDC/pages/317390849) (and not yet provided) – follow on screen instructions to provide a [personal access token](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens) with correct permissions for selected repository.

6.  Select source branch.

7.  Select target branch.

8.  Verify pull request title is correct. Edit as desired.
    **Note:** the Jira issue key must remain in the pull request name to create the pull request **⇿** Jira issue association.

9.  Click **Create**.


### Video: Creating pull/merge request from Git integration development panel ( UPDATED VIDEO COMING SOON )

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/rsccl5wxps) _to open this video in a new tab/window for more viewing options._

_The video shows Git Integration for Jira Cloud process but is also applicable to the Jira Server version._

If you still have a question – reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com).