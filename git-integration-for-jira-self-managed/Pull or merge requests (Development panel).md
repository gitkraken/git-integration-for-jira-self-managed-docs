---

title: Pull or merge requests (Development panel)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The **Pull Requests** (GitHub or other connected git hosts) or **Merge Requests** (if GitLab is connected) section lists the merge/pull requests and their status. All merge/pull requests from all types of sources are shown here (for now, GitLab/GitHub/Azure/TFS/VSTS).

The displayed information depends on which supported git hosts are connected to Jira. For example:

*   GitLab integrations only  –  merge requests

*   Other integrations  –  pull requests

*   Both GitLab and GitHub integrations  –  separate sections for merge requests and pull requests


For necessary permissions that GitLab users must have for creating pull/merge requests, see [**GitLab Documentation: Permissions**](https://docs.gitlab.com/ee/user/permissions.html).

This function does not work for connected single git repositories. Use the auto-connect integration instead.

##
Getting started

If a git host is connected to Jira, create a pull/merge request by clicking **Create pull request** or **Create merge request** label link on the Git integration panel. The following dialog is displayed:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399144/jira-server-issue-create-pull-request-dialog.png?version=1&modificationDate=1630642922913&cacheVersion=1&api=v2&width=544&height=282)

*   Select **Repository** from the list.
    GITHUB If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.
    GITLAB If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, `johnsmith/second-webhook-test-repo`.

*   Choose a branch as the **Source branch**. This branch will be merged to the Target branch.

*   Set _**master**_ as the **Target branch**.

*   Enter a descriptive **Title** for this pull/merge request or leave it as is (recommended).

*   Click **Create** to finish this process.



If the [Require User PAT option](/wiki/spaces/GIJDC/pages/317390849) is enabled in **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the dialog below is displayed instead:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399144/jira-server-issue-create-pull-req-dlg-cfg-pat.png?version=1&modificationDate=1630642923158&cacheVersion=1&api=v2&width=544&height=272)

If an invalid PAT was configured for the selected repository, the pull/merge request creation process will fail.

This feature is available on connected GitLab1 and GitHub2 git hosts for Jira Server; GitLab, GitHub, Microsoft TFS/VSTS and AWS CodeCommit git hosts for Jira Cloud.

Git Integration for Jira Server/Data Center:
1 VERSION 2.12.3+
2 VERSION 2.13.0+

##
GitLab merge request

If you want to create a merge request for GitLab, click **Create merge request**. It has the same process described in the pull request creation steps above.

The merge request is displayed on the developer panel and will also be associated to the mentioned Jira issue by fulfilling the following condition:

*   Merge request **Title** contains the issue key. For example, `TEST-1-Fix-binaries`.


This will also allow a service user to associate a Merge/Pull Request with multiple Jira issues regardless of commit associations.

BigBrassBand recommends service users to enable pull/merge requests webhook trigger events. This way, any changes to pull/merge requests gets reindexed quickly.


The Pull/merge request list provides status information about the pull/merge request if it is opened or merged. For example:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399144/dev-panel-pull-req-example.png?version=1&modificationDate=1630642923880&cacheVersion=1&api=v2)


Hover the mouse pointer on the pull/merge request label to see information of the repository and branch where it belongs.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399144/dev-panel-pull-req-example-hover.png?version=1&modificationDate=1630642924123&cacheVersion=1&api=v2)

For detailed information on this feature, see [Creating pull/merge requests](/wiki/spaces/GIJDC/pages/1932460359).

* * *

### Video Guide (UPDATED VIDEO COMING SOON)

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/1jwzeex5qa) _to open this video in a new tab/window for more viewing options._

