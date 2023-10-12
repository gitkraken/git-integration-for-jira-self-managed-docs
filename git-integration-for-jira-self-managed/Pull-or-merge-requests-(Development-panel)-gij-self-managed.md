---

title: Pull or merge requests (Development panel)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The **Pull Requests** (GitHub or other connected git hosts) or **Merge Requests** (if GitLab is connected) section lists the merge/pull requests and their status. All merge/pull requests from all types of sources are shown here (for now, GitLab/GitHub/Azure/TFS/VSTS).

The displayed information depends on which supported git hosts are connected to Jira. For example:

*   GitLab integrations only  –  merge requests

*   Other integrations  –  pull requests

*   Both GitLab and GitHub integrations  –  separate sections for merge requests and pull requests

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For necessary permissions that GitLab users must have for creating pull/merge requests, see <a href='https://docs.gitlab.com/ee/user/permissions.html' target='_blank'><b>GitLab Documentation: Permissions</b></a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This function does not work for connected single git repositories. Use the auto-connect integration instead.
    </div>
    </div>
</div>

&nbsp;

### Getting started

If a git host is connected to Jira, create a pull/merge request by clicking **Create pull request** or **Create merge request** label link on the Git integration panel. The following dialog is displayed:

<img src='/wp-content/uploads/gij-gitserver-create-pullreq-dlg-pat-ok.png' style='display:block;margin:25px auto;max-width:100%' />

*   Select **Repository** from the list.<br>

    <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>GITHUB</b> If there are several repositories with the same name, the listed GitHub repositories will have their names attached with a GitHub organization name. For example, `BigBrassBand/second-webhook-test-repo`.<br>

    <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>GITLAB</b> If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, `johnsmith/second-webhook-test-repo`.

*   Choose a branch as the **Source branch**. This branch will be merged to the Target branch.

*   Set _**master**_ as the **Target branch**.

*   Enter a descriptive **Title** for this pull/merge request or leave it as is (recommended).

*   Click **Create** to finish this process.

&nbsp;

If the [Require User PAT option](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) is enabled in **Integration Settings** and a user PAT isn't configured yet for the selected repository via Repository Browser, the dialog below is displayed instead:

<img src='/wp-content/uploads/gij-gitserver-create-pullreq-dlg-pat-cfg.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If an invalid PAT was configured for the selected repository, the pull/merge request creation process will fail.
        <div style='margin-top:5px;margin-bottom:-10px'>
            This feature is available on connected GitLab1 and GitHub2 git hosts for Jira Server; GitLab, GitHub, Microsoft TFS/VSTS and AWS CodeCommit git hosts for Jira Cloud.
        </div>
    </div>
    </div>
</div>

&nbsp;

### GitLab merge request

If you want to create a merge request for GitLab, click **Create merge request**. It has the same process described in the pull request creation steps above.

The merge request is displayed on the developer panel and will also be associated to the mentioned Jira issue by fulfilling the following condition:

*   A merge request **Title** must contain the issue key. For example, `TEST-1-Fix-binaries`.

This will also allow a service user to associate a Merge/Pull Request with multiple Jira issues regardless of commit associations.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We recommends service users to enable pull/merge requests webhook trigger events. This way, any changes to pull/merge requests gets reindexed quickly.
    </div>
    </div>
</div>

The Pull/merge request list provides status information about the pull/merge request if it is opened or merged. Hover the mouse pointer on the pull/merge request label to see information of the repository and branch where it belongs.

<img src='/wp-content/uploads/gij-gitserver-dev-panel-pullreq-list-hover.png' style='display:block;margin:25px auto;max-width:100%' />

For detailed information on this feature, see [Creating pull/merge requests](/git-integration-for-jira-data-center/creating-branches-gij-self-managed).

&nbsp;
### Video Guide

_(UPDATED VIDEO COMING SOON)_

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/1jwzeex5qa?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:12px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/1jwzeex5qa'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

### Associating pull or merge request to Jira issue

A git service user can create a PR/MR via the Git host service portal and adding/inserting a Jira issue key in the PR/MR title. This is automatically added to the Pull/Merge request list in the Jira issue Git developer panel.

| Git service portal |
| :---: |
| ![](/wp-content/uploads/gij-gitserverdc-associate-pull-req-example-host.png) |

| Jira issue PR/MR list view |
| :---: |
| ![](/wp-content/uploads/gij-gitserverdc-assoc-pull-req-dev-panel-list.png) |

Additionally, creating PR/MR via the Git Integration developer panel automatically associates the PR/MR to a Jira issue. This also adds a description in the PR/MR to the git host service portal containing the link to the Jira issue.


&nbsp;
* * *

[**Prev:** Branches (Development panel)](/git-integration-for-jira-data-center/branches-(development-panel)-gij-self-managed)

[**Next:** Git tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed)

