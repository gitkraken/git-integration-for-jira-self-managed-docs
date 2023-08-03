---

title: Workspace FAQ
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

This page contains related questions on Git Integration for Jira add-on user experience in Jira.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com?subject=Commits%20display%20issues%20-)) or visit our [GIJ Support portal](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support) if you don't see what you're looking for.

- [How do I see if work has really started on an issue?](#how-do-i-see-if-work-has-really-started-on-an-issue)
- [How do I see who has worked on an issue?](#how-do-i-see-who-has-worked-on-an-issue)
- [How do I see how long ago since someone worked on an issue?](#how-do-i-see-how-long-ago-since-someone-worked-on-an-issue)
- [How do I see what is being changed in this ticket?](#how-do-i-see-what-is-being-changed-in-this-ticket)
- [How do I see what is getting attention in this release and previous releases?](#how-do-i-see-what-is-getting-attention-in-this-release-and-previous-releases)
- [The git commits are not showing on the Jira Activity Stream. Why?](#the-git-commits-are-not-showing-on-the-jira-activity-stream-why)

&nbsp;
* * *
&nbsp;

#### How do I see if work has really started on an issue?

Open an issue in your browser and click on the **Git Commits** tab.

![](/wp-content/uploads/gij-gitserver-jira-issue-activity-workspace-faq.png)

<div align=center style='margin-top:12px;margin-bottom:30px;'><i>See all Git commits associated with an issue in Jira</i></div>

If the tab says that no Git log entries have been found, then work has not yet started on the ticket.

#### How do I see who has worked on an issue?

Open an issue in your browser and click on the **Git Commits** tab.

Everyone listed in the "Author/Committer" column has worked on the issue.

#### How do I see how long ago since someone worked on an issue?

Open an issue in your browser and click on the **Git Commits** tab.

All changes to the source code are listed from newest to oldest. The date/time in the first line is the last time the changes to the issue have been submitted into Git.

![](/wp-content/uploads/gij-gitserver-jira-issue-workspace-submitted-time.png)

#### How do I see what is being changed in this ticket?

Open an issue in your browser and click on the **Git Commits** tab.

When a developer submits a change to Git, they can type a brief message that summarizes the changes.  These messages show up under the Committer/Author's name.

The files that were changed by the developer appear as clickable links. Click on the file links to view the actual source code that was changed.

#### How do I see what is getting attention in this release and previous releases?

Open the project summary in your browser and click on the **Git Commits** tab.

All changes in all issues will be present. If you use the "Version" tagging feature of Jira, you can filter the changes by version.

![](/wp-content/uploads/gij-gitserver-proj-git-commits-all-versions.png)

<div align=center style='margin-top:12px;margin-bottom:30px;'><i>See all Git commits associated with a version tag in Jira.</i></div>

#### The git commits are not showing on the Jira Activity Stream. Why?

Only the commits that are [linked to Jira issues](/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed) will show on the Jira Activity Stream (not all commits in repositories).

