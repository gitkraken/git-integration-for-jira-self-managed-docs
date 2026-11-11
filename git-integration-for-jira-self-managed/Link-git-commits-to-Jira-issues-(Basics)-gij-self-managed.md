---

title:  Link git commits to Jira issues (Integration basics)
description: "Link Git commits to a Jira issue by including the issue key in the commit message, then view them in the Git Commits tab."
product: Git Integration for Jira Data Center
feature: Linking Commits to Issues
content_type: how-to
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-08
llms_include: true
tags: [commit messages, issue keys, git commits tab, activity stream, commit-msg hook]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "integration-guides-gij-self-managed"
    nav_label: "– Link git commits to Jira issues (Integration basics)"
    nav_order: 30
    nav_parent: "integration-basics-gij-self-managed"
    page_type: "content"
    card_icon: "link"
    card_color: "green"
    card_description: "Link Git commits to a Jira issue by including the issue key in the commit message, then view them in the Git Commits tab"
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

> **Note:** Only the commits that are <b>linked to Jira issues</b> will show on the Jira Activity Stream (not all commits in repositories).

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

