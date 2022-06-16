---

title: Linking git commits to Jira issues
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
To create a link between your Git commit and a Jira issue, developers must include the issue key into the commit comment.

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/7kj43knu4m?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/7kj43knu4m'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

Commits are selected by issue key. Developers should add them to comments every time the commits are made.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <i>For example, the <b>"PROJ-50 fixed issue"</b> comment – this assumes that you have configured a Jira project with the key '<b>PROJ</b>' and someone has created the issue <b>#50</b> within this project.</i>
    </div>
    </div>
</div>
<br>

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398265/gitserver-jira-issue-git-commits-tab-view.png?version=1&modificationDate=1641369478236&cacheVersion=1&api=v2&width=680&height=302)

<div align='center'>
    <i>Example Git commit message: "<b>GIT-4322 - Updated the plugin …</b>".<br>
    In this case, "<b>GIT-4322</b>" is the issue key linking the commit message to the Jira issue.</i>
</div>
<br>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Commits that are part of non-master branches will be included only if the master branch doesn't have them.
    </div>
    </div>
</div>
<br>

As a best practice to work with sub-task — put the parent and sub-task Jira issue keys in the commit message so that the commit shows in both places. This way, the commit for the sub-task does not get lost in the many commits of the parent issue.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398265/gitserver-git-commits-tab-view-subtask.png?version=1&modificationDate=1641369522246&cacheVersion=1&api=v2&width=655&height=253)

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The maximum commit message length is <b>8,000 characters</b>.
    </div>
    </div>
</div>
<br>

The Git Integration for Jira app supports commits that used the old Jira key in the commit message after a project rename to a new key name (Example: `TEST-16` to `PROJ-16`).

There are two scenarios related to the rename/move:

*   The Jira project key was renamed and the commit message contains the old key prior to the installation of the Git Integration for Jira app.

*   The Jira issue was moved from one project to another project and the message contains the old key prior to the installation of the Git Integration for Jira app.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Jira Activity Stream</b>
        Only the commits that are linked to Jira issues will show on the Jira Activity Stream (not all commits in repositories).
    </div>
    </div>
</div>

