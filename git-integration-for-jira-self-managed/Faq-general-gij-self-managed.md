---

title: FAQ - General
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

This page contains frequently asked questions by users in general.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([support@bigbrassband.com](mailto:support@bigbrassband.com?subject=General%20question%20-)) if you don't see what you're looking for.

- [What is git?](#what-is-git)
- [What is Git Integration for Jira app?](#what-is-git-integration-for-jira-app)
- [Why would I want to see Git in my Jira?](#why-would-i-want-to-see-git-in-my-jira)
- [How do Git and Jira work together?](#how-do-git-and-jira-work-together)
- [Is this safe? Will it cause trouble?](#is-this-safe-will-it-cause-trouble)
- [Which version of Jira is compatible with Git Integration for Jira app?](#which-version-of-jira-is-compatible-with-git-integration-for-jira-app)
- [How to obtain the correct Jira user name?](#how-to-obtain-the-correct-jira-user-name)

* * *

## What is git?

Git is a source code repository. Developers keep track of their source code using Git.

Git relies heavily on branching and merging. Branching is making a temporary copy of source code for a single purpose like adding a particular feature or fixing a bug. Merging is safely moving the changes from one branch back to another.

## What is Git Integration for Jira app?

This is an app for Jira that mashes together data from a Git server with your Jira instance. It let's people see code in Git in context with Jira issues.

As time goes on, a lot interesting features are added to improve your git experience:

*   instant integration

*   view commits in Jira

*   view branches in Jira

*   view pull/merge requests in Jira

*   view tags in Jira

*   create branches and pull/merge requests inside Jira

*   compare code inside Jira

*   smart commits

*   project permissions

*   webhook support

*   git roll up commit and issues summary tab

*   JQL searching

*   Repository browser

*   _and more…_


For more information on each feature, see [**Git Integration for Jira: Product Features**](https://bigbrassband.com/git-for-jira-features.html).

## Why would I want to see Git in my Jira?

Git can be complicated and daunting – especially for non-developers. Jira users want this app so they can work with Git in the familiar Jira interface.

## How do Git and Jira work together?

In organizations with Git and Jira, it is common to have a branch for each Jira issue and branches for every version.

When developers put their work in Git, they can include a Jira issue ID in the comments. With the Git Integration for Jira app installed, Jira will then show the changes in the issue.

## Is this safe? Will it cause trouble?

It is a safe and well-tested plugin.

We test this on huge Git repositories in large Jira instances. Over 5000 organizations in 70 countries use the Git Integration for Jira app.

## Which version of Jira is compatible with Git Integration for Jira app?

Some versions of the Git Integration for Jira app are compatible with specific versions of Jira. For example, VERSION 3.8.1 is compatible with Jira Server versions 7.13.0 to 8.19.1.

As of **v4.0+**, support for Jira 7+ is dropped.

For a more comprehensive view, see [**Git Integration for Jira app: Version History »**](https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions).

In the Version History page, you can try or buy the Git Integration for Jira app or download it for use with [**manual installation**](/git-integration-for-jira-self-managed/manual-installation-gij-self-managed/).

## How to obtain the correct Jira user name?

1.  From your Jira dashboard menu, go to **JIRA Administration** ➜ **System**.

2.  On the sidebar, click **System Info**.

3.  Look for the **User Name** row in the table.


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2047901940/gitserver-jira-admin-system-username-info.png?version=1&modificationDate=1641742011156&cacheVersion=1&api=v2&width=680&height=401)

