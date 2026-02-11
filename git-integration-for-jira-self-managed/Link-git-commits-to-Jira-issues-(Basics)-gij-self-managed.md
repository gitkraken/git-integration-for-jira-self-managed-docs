---

title:  Link git commits to Jira issues (Integration basics)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/7kj43knu4m?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:12px;margin-bottom:30px;'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/7kj43knu4m'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

Open a Jira issue then go to the Git Commits tab. In this tab, you will see commits, files changed, links to external repository, commit author and more.

<img src='/wp-content/uploads/gij-gitserver-git-commits-tab-view-c1.png' style='display:block;margin:25px auto;max-width:100%' />

In the above example, the issue key **GIT-4322** text is inserted into a git commit message to link the commit to this issue.

The git commit will get associated with the Jira issue if the commit message includes the exact issue ID. The Git Integration for Jira add-on will automatically index new commits and associate the referenced issue. For better readability, place the issue key text at the start of the commit message.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only the commits that are <b>linked to Jira issues</b> will show on the Jira Activity Stream (not all commits in repositories).
    </div>
    </div>
</div>

&nbsp;

**Git administrator »**

If you want to enforce the commit with a hook, please install this Git commit hook script - [Commit-msg Hook](/git-integration-for-jira-data-center/commit-msg-Hook-gij-self-managed).

### More related articles on integration basics

[Connecting to a git host account via Add new integration panel](/git-integration-for-jira-data-center/connecting-to-a-git-host-account-via-Add-new-integration-panel-gij-self-managed)

[Connecting to a single git repository (HTTPS \| SSH)](/git-integration-for-jira-data-center/connecting-to-a-single-git-repository-(HTTPS-SSH)-gij-self-managed)

[Setting up web links](/git-integration-for-jira-data-center-gij-self-managed/setting-up-web-links-gij-self-managed)

**Link git commits to Jira issues (Basics)** (this page)

[Using smart commits](/git-integration-for-jira-data-center/using-smart-commits-gij-self-managed)

[Using the Repository Browser](/git-integration-for-jira-data-center/using-the-repository-browser-gij-self-managed)

[Creating branches and pull \| merge requests (Basics)](/git-integration-for-jira-data-center/Creating-branches-and-pull-merge-requests-(Basics)-gij-self-managed)

