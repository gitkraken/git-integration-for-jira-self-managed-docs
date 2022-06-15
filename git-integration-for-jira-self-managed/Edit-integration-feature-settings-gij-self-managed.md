---

title: Edit integration feature settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitcfg-actions-edit-feature-conn-cfg.png?version=1&modificationDate=1630642846599&cacheVersion=1&api=v2&width=680&height=213)

Clicking <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration feature settings** opens the configuration page for integration features settings.

Utilize the following options to configure the selected integration:

- [Repository Browser](#repository-browser)
- [Tags](#tags)
- [Personal Access Token: Require User PAT](#personal-access-token-require-user-pat)
- [Project Permissions](#project-permissions)
- [Source Code Diff Viewing](#source-code-diff-viewing)
- [Smart Commits](#smart-commits)
- [Commit Notification Emails](#commit-notification-emails)

* * *

## Repository Browser

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-repocfg-repovw.png?version=1&modificationDate=1630642846839&cacheVersion=1&api=v2&width=680&height=65)

When `Enabled`, it allows users to view Git repositories of configured projects. For more information, see [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed/).

## Tags

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-tags.png?version=1&modificationDate=1630642847074&cacheVersion=1&api=v2&width=680&height=150)

Set whether to show all tags or show on tags with matching regex pattern. For more information on git tags, see [Git Tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed/).

## Personal Access Token: Require User PAT

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-pat-reqpat.png?version=1&modificationDate=1630642847309&cacheVersion=1&api=v2&width=680&height=61)

Enable this option to require users to provide PAT which will be used for branch and merge/pull request creation/deletion (via the developer panel on the Jira issue page). This is a security feature of Git Integration for Jira app for git hosts that support two-factor authentication.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This option requires the <a href='/git-integration-for-jira-data-center/Repository-Browser/'>Repository Browser</a> feature enabled.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is only available for auto-connected git hosts in Jira Server and Jira Data Center.
    </div>
    </div>
</div>

## Project Permissions

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-feature-cfg-proj-acls.png?version=1&modificationDate=1639568670798&cacheVersion=1&api=v2&width=680&height=155)

The default setting is **Associate with all projects**. You can restrict access to the Repository Browser and Git Commits tabs for the selected repository by setting the project associations.

To restrict to specific projects, uncheck the **Associate with all projects** _option_ and set/select one or more projects from the list.

## Source Code Diff Viewing

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-src-code-diffvw.png?version=1&modificationDate=1630642847773&cacheVersion=1&api=v2&width=680&height=64)

Allows or denies users to view the diff by commit and file.

## Smart Commits

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-smartcommits.png?version=1&modificationDate=1630642848019&cacheVersion=1&api=v2&width=680&height=82)

Allows or denies the users to use the smart commits feature.

## Commit Notification Emails

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-commit-notif-emails.png?version=1&modificationDate=1630642848253&cacheVersion=1&api=v2&width=680&height=116)

Enable/disable this setting to allow/deny sending of commit notification emails.

Set the **Max commit age (in minutes)** as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value.

