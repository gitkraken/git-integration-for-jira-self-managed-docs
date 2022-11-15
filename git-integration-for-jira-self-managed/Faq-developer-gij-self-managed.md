---

title: Developer FAQ
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

This page contains solutions targeted for developers.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com?subject=Developer%20questions%20-)) or visit our [support portal](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/) if you don't see what you're looking for.

- [How do Git commits get associated with a Jira issue?](#how-do-git-commits-get-associated-with-a-jira-issue)
- [How do I ensure people are following our organization's process for source code?](#how-do-i-ensure-people-are-following-our-organizations-process-for-source-code)
- [What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?](#what-will-happen-to-jira-issue-associations-with-commits-if-the-jira-issue-is-moved-to-a-new-project)
- [What are developer licenses?](#what-are-developer-licenses)
- [How to associate a commit, branch or pull request AFTER it has been created?](#how-to-associate-a-commit-branch-or-pull-request-after-it-has-been-created)

<br>
<br>
<hr>
<br>
<br>

## How do Git commits get associated with a Jira issue?

On every Git commit, make sure the message includes the exact issue ID at the beginning of the text. Git Integration for Jira app will automatically index new commits and associate the referenced issue.

To create a link between your Git commit and a Jira issue, developers must include the issue key into the commit comment.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Example git commit message:<br>
        <div class='nextpara'>
            "<code>PROJ-913 - Plugin version change from 2.6.7 to 2.6.8</code>"; where <b><i>PROJ-913</i></b> is the issue key that links the commit message to the Jira issue.
        </div>
    </div>
    </div>
</div>

If you want to enforce the commit with a hook, please install this [**Git commit hook script »**](/git-integration-for-jira-data-center/commit-msg-hook-gij-self-managed).

## How do I ensure people are following our organization's process for source code?

Open the project summary in your browser and click on the **"Git Commits"** tab.

From **"Select Version"** drop-down, make sure that **"All versions"** is selected.

All changes that developers have submitted will be listed in reverse chronologically order. From this view, you can audit all of the changes that developers have recently submitted.

## What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?

The commit retains the association even in the new project. The Git Integration for Jira app supports history tracking. Thus, when moving a ticket to a new project whose issue key has changed, the association will still work.

The steps below provides an outline that you can follow to verify that the issue associations with commits are retained:

1.  Associate a commit with issue (ex. **TEST-1**)

2.  Move the issue **TEST-1** to a new project (ex. **PM**)

3.  New issue key for **TEST-1** is **PM-18**

4.  Check that original commit in **TEST-1** is still available in **PM-18**. The commit should be there (Git Commits tab).

5.  In the **Git Repositories** configuration page, perform **Reset** and **Reindex** (under Actions) on the selected repository to make sure that the commits are in the correct location.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app also supports multiple issue keys in a commit message.
    </div>
    </div>
</div>
<br>

## What are developer licenses?

Developer licenses are available to existing commercial and academic service license holders who wish to deploy testing and development installations of the Atlassian software. It is provided free of charge and the license maintenance expiration date is the same as your commercial/academic product. This is not available for cloud or server Starter products.

Only the technical contact can generate a developer key from your commercial/academic license.

![](/wp-content/uploads/gij-atlassian-view-dev-license.png)

For more information, see [**What are developer licenses and how are they used?**](https://www.atlassian.com/licensing/purchase-licensing#licensing-10) and [**Getting a Developer License**](https://confluence.atlassian.com/jirakb/get-a-developer-license-for-jira-server-744526918.html).

## How to associate a commit, branch or pull request AFTER it has been created?

**For commits:** – these can be associated either via [manual association feature](/git-integration-for-jira-data-center/manually-link-git-commits-to-jira-issues-gij-self-managed) of the Git Integration for Jira app or via _**Git Notes**_.

**For branches** – these cannot be re-associated after creation because git does not allow branches to be renamed.

**For pull/merge requests** – just editing the PR/MR titles to include the Jira issue and then perform reindex will associate the PR/MR to the specified Jira issue. Also, editing their descriptions will associate the PR/MR to the specified Jira issue as well.

