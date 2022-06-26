---

title: Workspace
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This page contains related questions on Git Integration for Jira add-on user experience in Jira.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([support@bigbrassband.com](mailto:support@bigbrassband.com?subject=Commits%20display%20issues%20-)) if you don't see what you're looking for.

- [How do I see if work has really started on an issue?](#how-do-i-see-if-work-has-really-started-on-an-issue)
- [How do I see who has worked on an issue?](#how-do-i-see-who-has-worked-on-an-issue)
- [How do I see how long ago since someone worked on an issue?](#how-do-i-see-how-long-ago-since-someone-worked-on-an-issue)
- [How do I see what is being changed in this ticket?](#how-do-i-see-what-is-being-changed-in-this-ticket)
- [How do I see what is getting attention in this release and previous releases?](#how-do-i-see-what-is-getting-attention-in-this-release-and-previous-releases)
- [The git commits are not showing on the Jira Activity Stream. Why?](#the-git-commits-are-not-showing-on-the-jira-activity-stream-why)

* * *

## How do I see if work has really started on an issue?

Open an issue in your browser and click on the **Git Commits** tab.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2053079047/gitserver-jira-issue-activity-workspace-faq.png?version=1&modificationDate=1642160312236&cacheVersion=1&api=v2&width=680&height=643)

If the tab says that no Git log entries have been found, then work has not yet started on the ticket.

## How do I see who has worked on an issue?

Open an issue in your browser and click on the **Git Commits** tab.

Everyone listed in the "Author/Committer" column has worked on the issue.

## How do I see how long ago since someone worked on an issue?

Open an issue in your browser and click on the **Git Commits** tab.

All changes to the source code are listed from newest to oldest. The date/time in the first line is the last time the changes to the issue have been submitted into Git.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2052915274/gitserver-jira-issue-workspace-submitted-time.png?version=1&modificationDate=1642160976910&cacheVersion=1&api=v2&width=680&height=265)

## How do I see what is being changed in this ticket?

Open an issue in your browser and click on the **Git Commits** tab.

When a developer submits a change to Git, they can type a brief message that summarizes the changes.  These messages show up under the Committer/Author's name.

The files that were changed by the developer appear as clickable links. Click on the file links to view the actual source code that was changed.

## How do I see what is getting attention in this release and previous releases?

Open the project summary in your browser and click on the **Git Commits** tab.

All changes in all issues will be present. If you use the "Version" tagging feature of Jira, you can filter the changes by version.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2052784140/gitserver-proj-git-commits-all-versions.png?version=1&modificationDate=1642162374533&cacheVersion=1&api=v2)

## The git commits are not showing on the Jira Activity Stream. Why?

Only the commits that are [linked to Jira issues](/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed) will show on the Jira Activity Stream (not all commits in repositories).

