---

title: Reindexing
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Permissions</b>
        You must be a member of the <b>jira-developers</b> <i>group</i> to start reindex.
    </div>
    </div>
</div>


Synchronization between the repository and app will start automatically. However, reindexing may be required to manually start the synchronization process.

## Getting started

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399289/gitserver-gitmgr-reindex-all-reindex-actions.png?version=1&modificationDate=1630642930639&cacheVersion=1&api=v2)

There are two ways to do this:

1.  To start update of all repositories, go to the **Git Integration for Jira** app git configuration page then click **Reindex All** button. Once synchronization is started, the progress will be displayed on this tab.

2.  If a specific repository or integration needs to be synchronized, click the <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> **Actions** icon then **Reindex**.

<div class="bbb-callout bbb--basic">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Click the view <img src='/wp-content/uploads/eye-icon.png' width=14 height=12 /> icon to see the reindex progress of the selected repository.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Initial Synchronization</b><br>
        Git log entries may not immediately appear when you open <b><i>Git Commits</i></b> tab right after the app installation. You need to wait until the revision indexer job completes the initial synchronization.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Reindex API</b><br>
        For advanced administrators who want to have more control on reindex, see the <a href='/git-integration-for-jira-self-managed/Reindex-API'>Git Integration for Jira Reindex API</a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Scheduler</b><br>
        As of Jira 6.3.10+, Atlassian added the <b>Scheduler Administration</b> (<i>Administration</i> ➜ <i>System</i> ➜ <i>Scheduler Details</i>) page. This page displays the properties of the Jira internal scheduler, the scheduled jobs and their triggers.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Repository Reindex (<b><i>GitRevisionIndexerJob</i></b>) can be configured in the <a href='/git-integration-for-jira-self-managed/General-settings'>General settings</a> page of the Git Integration for Jira app.
    </div>
    </div>
</div>
<br>

## Last indexed revision

The Git Integration for Jira app stores the ID of the last indexed commit for each branch. This ID is used to limit the processed data upon reindex or update. This way, only new commits will be indexed on the next synchronization.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399289/gitserver-gitmgr-actions-reset-index.png?version=1&modificationDate=1630642930870&cacheVersion=1&api=v2)

On the Manage git repositories page, click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> **Actions** then **Reset index** to reset the _**Last**_ _**Indexed**_ date. Perform this process whenever the Git Integration for Jira app is updated or re-installed.

## Reindex and updatedDate filter

The Git Integration for Jira app automatically changes the **updatedDate** of an issue when a Git commit is added to an issue upon reindex. When the reindex encounters a commit previously modified by the user relating to an issue, that issue will be updated.

You can enable or disable this setting in the [Git Integration for Jira app - General Settings](/git-integration-for-jira-self-managed/General-settings) page ➜ **Jira Issue Updates**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399289/gitserver-gencfg-last-updated-field.png?version=1&modificationDate=1630642931102&cacheVersion=1&api=v2&width=557&height=386)

 <div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app updates the "<b>updatedDate</b>" field whenever a commit is made.
    </div>
    </div>
</div>

## Indexing errors

Starting v3.6+ of the Git Integration for Jira app, indexer will show an error message on the Jira issue ➜ Git Commits tab.

### Jira Server

<img src='https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399289/git-server-indexing-error-sample.png?version=1&modificationDate=1630642930175&cacheVersion=1&api=v2&width=442&height=131' class='center img-responsive img-bordered' />

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Cancelling indexing from the Git Integration admin interface is not currently possible. See <a href='/git-integration-for-jira-self-managed/Known-issues#fully-cancelling-an-ongoing-indexing-is-not-possible'>workaround in the Known issues page</a>.
    </div>
    </div>
</div>

