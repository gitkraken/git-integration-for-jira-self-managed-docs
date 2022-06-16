---

title: Per Node Repository Indexing - General setting
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
<div style='color: yellow'><b>NEW FEATURE</b></div>
<div style='color: magenta'><b>DATA CENTER ONLY</b></div>
<br>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Available in version Git Integration for Jira Data Center <b>v4.2+</b>.
    </div>
    </div>
</div>


Large Jira Data Center deployments can be designed to have specific Jira Data Center nodes focusing exclusively on responding to user activity while other nodes focus on other activities (example: responding to API requests). As of version 4.2+, Git Integration for Jira Data Center allows the Jira administrator to designate some or all DC nodes to perform Git indexing.

## New General setting: Per Node Repository Indexing

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2095775749/gitdc-gencfg-indexing-allow-all-nodes.png?version=1&modificationDate=1648123707980&cacheVersion=1&api=v2&width=680&height=107)

Set specific dedicated Jira Data Center (DC) nodes to perform Git Integration for Jira indexing jobs. The default setting is set to allow repository reindexing tasks to be performed on all Jira DC nodes.

## Setting specific nodes for repository reindexing

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is ideal for large Jira Data Center instances.
    </div>
    </div>
</div>

Uncheck the **Allow all nodes…** setting to access the drop down list and assign one or more dedicated nodes for repository reindexing tasks.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2095775749/gitdc-gencfg-indexing-allow-all-nodes-specific.png?version=1&modificationDate=1648124669581&cacheVersion=1&api=v2)

The repository reindexing tasks will be performed only on the specified nodes. This mode will reduce the background processing load on the non-selected DC nodes.

## Sample Jira Data Center nodes configuration

**Example 1:**

Jira API activity and GIJ indexing combined

*   Node 1: User activity

*   Node 2: User activity

*   Node 3: API activity + GIJ indexing

*   Node 4: API activity + GIJ indexing

<br>

**Example 2:**

Jira API activity and GIJ indexing on specific nodes

*   Node 1: User activity

*   Node 2: User activity

*   Node 3: API activity

*   Node 4: API activity

*   Node 5: GIJ indexing

*   Node 6: GIJ indexing

