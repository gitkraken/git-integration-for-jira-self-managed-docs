---

title: Recommended reindex interval setting
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The configuration of the scheduler jobs are no longer accessible in the Jira administration page. For this case, the Git Integration for Jira app offers Jira administrators this capability via the [General settings](/wiki/spaces/GIJDC/pages/1930398111/General+settings) page.

VERSION 3.7+ The ​_**Repository reindexing**_ and _**Garbage collection and revision validation checkers**_ settings are now moved into the **Scheduled Jobs** settings group.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396353/gitserver-gencfg-scheduled-jobs-repo-ridx-cfg.png?version=1&modificationDate=1630642790933&cacheVersion=1&api=v2&width=680&height=269)

Set the automatic reindex interval frequency value in minutes as required. The default value is **5** minutes.  Min = **1**, Max = **76,861,433,640,456**.

Regardless of the time to index, the reindex interval is the amount of time between the currently completed reindex task until the next reindex.

Improving Jira performance depends on the duration value of the _RevisionIndexJob_. To see the `Last run duration` value, do the following steps:

1.  Go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ **System**.

2.  On the sidebar, select **Scheduler details**.

3.  Scroll to `com.xiplink.jira.git.revisions.RevisionIndexJob`.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396353/ira-system-sched-details-revidxjob-item(c).png?version=1&modificationDate=1630642790449&cacheVersion=1&api=v2&width=646&height=163)
4.  Click **Show more** under the Actions column.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396353/jira-system-sched-details-revisionindexjob(c).png?version=1&modificationDate=1630642790693&cacheVersion=1&api=v2&width=646&height=202)

If the `Last run duration` value shows `3 minutes` _or greater_, we recommend to increase the reindex interval.

The reindex interval must be greater or equal to the `Last run duration` value of _RevisionIndexJob_ to improve Jira performance. For example, if the `Last run duration` value is **20 minutes**, set the Reindex interval value to **20 minutes or more** in the General settings page.

[« Reindex API to trigger indexing](/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing)

[Setting up web linking »](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking)

### More related topics about getting started for git admins

*   Page:

    [Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls) (Git Integration for Jira Data Center)

*   Page:

    [New GitLab v10+ authentication](/wiki/spaces/GIJDC/pages/1930396211) (Git Integration for Jira Data Center)

*   Page:

    [General settings: Improving Jira performance](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance) (Git Integration for Jira Data Center)

*   Page:

    [Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/wiki/spaces/GIJDC/pages/1930396287) (Git Integration for Jira Data Center)

*   Page:

    [Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317) (Git Integration for Jira Data Center)

*   Page:

    [Recommended reindex interval setting](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting) (Git Integration for Jira Data Center)

*   Page:

    [Reindex API to trigger indexing](/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing) (Git Integration for Jira Data Center)

*   Page:

    [Setting up web linking](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking) (Git Integration for Jira Data Center)

*   Page:

    [Setting up webhooks](/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks) (Git Integration for Jira Data Center)

*   Page:

    [Increasing timeout threshold for large repositories while doing a Git pull](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull) (Git Integration for Jira Data Center)

*   Page:

    [Working with Tracked folders](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders) (Git Integration for Jira Data Center)

*   Page:

    [Recommended upgrade method for Git Integration for Jira](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira) (Git Integration for Jira Data Center)

*   Page:

    [Discard cloned files in Jira Home directory (General setting)](/wiki/spaces/GIJDC/pages/1930396547) (Git Integration for Jira Data Center)