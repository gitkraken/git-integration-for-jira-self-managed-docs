---

title:  - Link git commits to Jira issues - Integration basics
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/7kj43knu4m?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/7kj43knu4m'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

Open a Jira issue then go to the Git Commits tab.  In this tab, you will see commits, files changed, links to external repository, commit author and more.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2045149189/gitserver-git-commits-tab-view(dec2021a).png%3Fversion=1&modificationDate=1640705375869&cacheVersion=1&api=v2?version=1&modificationDate=1640865989201&cacheVersion=1&api=v2)

In the above example, the issue key **GIT-4322** text is inserted into a git commit message to link the commit to this issue.

The git commit will get associated with the Jira issue if the commit message includes the exact issue ID. The Git Integration for Jira add-on will automatically index new commits and associate the referenced issue. For better readability, place the issue key text at the start of the commit message.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only the commits that are <b>linked to Jira issues</b> will show on the Jira Activity Stream (not all commits in repositories).
    </div>
    </div>
</div>
<br>

**Git administrator »**

If you want to enforce the commit with a hook, please install this Git commit hook script - [Commit-msg Hook](/git-integration-for-jira-data-center/commit-msg-Hook-gij-self-managed/).

