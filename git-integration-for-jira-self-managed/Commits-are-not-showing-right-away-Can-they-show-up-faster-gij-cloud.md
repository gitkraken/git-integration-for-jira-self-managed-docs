---

title: Commits are not showing right away. Can they show up faster?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Commits won't appear immediately since synchronization is implemented as background job _(GitRevisionIndexerJob)_.  You can reduce the job delay down to 1 minute to schedule updates more often.

Navigate to the **General settings** of the Git Integration for Jira app.

Scroll down to the **Scheduled jobs** section and set the **Repository indexing** value or leave it as is (recommended).

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2053570566/gitserver-gencfg-sched-jobs-repo-idx-sel.png?version=1&modificationDate=1642419212374&cacheVersion=1&api=v2&width=680&height=300)

For near-instantaneous display of commits in your Jira issues, we recommend to [configure webhooks](/git-integration-for-jira-self-managed/Integration-webhooks).

