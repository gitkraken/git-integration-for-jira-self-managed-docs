---

title: Reindex and cache
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This page contains related questions about git notes, reindex tracking and control.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([support@gitkraken.com](mailto:support@gitkraken.com?subject=Reindex%20issues%20-)) or visit our [support portal](https://help.gitkraken.com/git-integration-for-jira-cloud/gij-cloud-contact-support/) if you don't see what you're looking for.

- [What does re-index do?](#what-does-re-index-do)
- [Is there any way to control the reindex?](#is-there-any-way-to-control-the-reindex)
- [Commits are not showing right away. Can they show up faster?](#commits-are-not-showing-right-away-can-they-show-up-faster)
- [How do I completely rebuild plugin indexes?](#how-do-i-completely-rebuild-plugin-indexes)
- [How do I clear the Git Integration for Jira app cache manually?](#how-do-i-clear-the-git-integration-for-jira-app-cache-manually)
- [Is it possible to track the specified branches when reindexing?](#is-it-possible-to-track-the-specified-branches-when-reindexing)
- [Is there a URL I can call to trigger fetch and re-index? Would be nice to add as service hook to GitHub/Gitlab.](#is-there-a-url-i-can-call-to-trigger-fetch-and-re-index-would-be-nice-to-add-as-service-hook-to-githubgitlab)
- [The git notes are still not visible in Jira. What should I do?](#the-git-notes-are-still-not-visible-in-jira-what-should-i-do)

<br>
<hr>
<br>

## What does re-index do?

Re-index does 2 operations:

*   Updates local repo from remote

*   Updates local indexes which contain info about every commit

## Is there any way to control the reindex?

In terms of kicking off the indexing based on an event, you have two options:

*   [Reindex API](/git-integration-for-jira-data-center/reindex-api-gij-self-managed)

*   [Webhooks overview](/git-integration-for-jira-data-center/Webhooks-gij-self-managed)

*   [Integration webhooks documentation](/git-integration-for-jira-data-center/Integration-webhooks-gij-self-managed)

What other users have done is set a high interval and then configure one of those options.

## Commits are not showing right away. Can they show up faster?

Commits won't appear immediately since synchronization is implemented as background job _(GitRevisionIndexerJob)_.  You can reduce the job delay down to 1 minute to schedule updates more often.

Navigate to the **General settings** of the Git Integration for Jira app.

Scroll down to the **Scheduled jobs** section and set the **Repository indexing** value or leave it as is (recommended).

![](/wp-cotnent/uploads/gij-gitserver-gencfg-sched-jobs-repo-idx-sel.png)

For near-instantaneous display of commits in your Jira issues, we recommend to [configure webhooks](/git-integration-for-jira-data-center/Integration-webhooks-gij-self-managed).

## How do I completely rebuild plugin indexes?

If you think that the Git indexes are corrupt and needed to be completely rebuilt, please do the following:

1.  Disable the Git Integration for Jira app (_Jira administration_ ➜ _Manage apps_).

2.  Remove the following folders:

    `{JIRA_HOME}/cache/indexes/plugins/jira-git-files`
    `{JIRA_HOME}/cache/indexes/plugins/jira-git-revisions`

3.  Enable Git Integration for Jira app.

<br>

On the next startup, the app will create the above folders again.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you have large Git repositories, please do this after prime time.
    </div>
    </div>
</div>
<br>

## How do I clear the Git Integration for Jira app cache manually?

If you think that the Git caches are corrupt and needed to be removed, please do the following:

1.  Disable the Git Integration for Jira app (_Jira administration_ ➜ _Manage apps_).

2.  Go to `<jira_home>`.

3.  Delete the index:

    **Example:** `rm -rf <jira_home>/caches/indexes/plugins/jira-git-*`

4.  Delete the cache:

    **Example:** `rm <jira_home>/data/git-plugin/indexed-revisions-info-cache`

5.  Enable the Git Integration for Jira app.

6.  Reindex all integration repositories by performing the next two steps.

7.  Go to Jira administration ➜ **Applications**. On the sidebar under _Git Integration for Jira_, click **Git Repositories**.

8.  Click **Reindex All**.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>The above solution also applies to:</b><br>
        Commit information that are not shown for commits having issue key(s) in its message that were already indexed.
    </div>
    </div>
</div>
<br>

## Is it possible to track the specified branches when reindexing?

No. The Git Integration for Jira app is designed to do a full index.

## Is there a URL I can call to trigger fetch and re-index? Would be nice to add as service hook to GitHub/Gitlab.

Yes  –  the following url can be used:

```powershell
http://<server url>/secure/StartReindexGitRepositories.jspa?reindex=true
```

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The reindex process won't start if reindex is already running.
    </div>
    </div>
</div>
<br>

## The git notes are still not visible in Jira. What should I do?

Perform a **Reset** + **Reindex** of the selected repository via Git Repositories of the Git add-on. If the issue still persist, see article, [How do I clear the Git Integration app for Jira cache manually?](#how-do-i-clear-the-git-integration-for-jira-app-cache-manually)

