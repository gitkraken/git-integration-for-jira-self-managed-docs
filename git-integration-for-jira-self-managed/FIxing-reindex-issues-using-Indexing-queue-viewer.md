---

title: Fixing reindex issues using Indexing Queue Viewer
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Use the Indexing Queue Viewer to check and look for reindex related issues.

**What's on this page:**

- [How to see when some indexing tasks has stuck?](#how-to-see-when-some-indexing-tasks-has-stuck)
- [How to make sure only the dedicated node is reindexing?](#how-to-make-sure-only-the-dedicated-node-is-reindexing)
- [How to see the progress of an integration index?](#how-to-see-the-progress-of-an-integration-index)
- [Why my repository hasn’t been removed yet?](#why-my-repository-hasnt-been-removed-yet)
- [How to find a nested repository in ERROR state?](#how-to-find-a-nested-repository-in-error-state)


## How to see when some indexing tasks has stuck?

Sometimes the indexing process takes longer for some tasks. To see which tasks are in this state, start from the Manage integrations page and check the integration with the <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>SCANNING</b> or <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>INDEXING</b> status.

<ol>
    <li>
        Go to <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Show integration repositories</b>. You may see some <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>QUEUED</b> or <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>FETCHING</b> status in the list and is somewhat taking a bit longer to process.
    </li>
    <li>
        Open <img src='/wp-content/uploads/actions-icon.png' /> Jira System administration then click <b>Logging and profiling</b> on the left sidebar.
    </li>
    <li>
        Under the <b>Default loggers section</b>, click <b>Configure...</b>.
    </li>
    <li>
        Set the <b>Package name</b> to <code>com.bigbrassband.jira.git.services.indexer</code>.
    </li>
    <li>
        Set <b>Logging Level</b> to <b>DEBUG</b>.<br>
        <div class="bbb-callout bbb--alert">
            <div class="irow">
            <div class="ilogobox">
                <span class="logoimg"></span>
            </div>
            <div class="imsgbox">
                Setting the Logging to DEBUG level for the above package name will intruct Jira to do verbose logging on the plugin. Make sure to turn this setting off once it is confirmed that indexing is working on the said tasks. For example, the reindex is in progress if you see logs constantly adding to your <b><i>atlassian-jira.log</i></b> below:
                <pre><code>Branch: {}
Last index revision: {}
Adding document for repository = {}; branch = {}; revision = {}.</code></pre>
            </div>
            </div>
        </div>
    </li>
    <li>
        Click <b>Add</b> to proceed.
    </li>
</ol>

Take a look at Atlassian logs in dynamic. The better way is to use "Last Log for Jira" plugin ([Last Log for Jira \| Atlassian Marketplace](https://marketplace.atlassian.com/apps/1211604/last-log-for-jira?hosting=server&tab=overview)). If the Git Integration for Jira app is doing something, then your logs are being flooded by a lot of messages like:

```java
”2023-02-17 16:58:26,436+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 INFO      [c.b.j.g.s.indexer.revisions.RevisionsIndexManagerImpl] Latest indexed revision is: null
2023-02-17 16:58:26,436+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 INFO      [c.b.j.g.s.indexer.revisions.RevisionsIndexManagerImpl] Updating to: dac6a2304402a62f6410e666fa1510d129b1af93
2023-02-17 16:58:26,443+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.RevisionsIndexManagerImpl] Adding document for repository = 4; branch = master; revision = commit dac6a2304402a62f6410e666fa1510d129b1af93 1627632962 -----sp
2023-02-17 16:58:26,443+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.CommitIssueCollector] Processing commit dac6a2304402a62f6410e666fa1510d129b1af93, branch master, repo: TestGitPluginRepo
2023-02-17 16:58:26,443+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.CommitIssueCollector] Init Date: 2023-02-17 16:58:22
2023-02-17 16:58:26,444+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.CommitIssueCollector] Processing commit 3478d5dc85e5e45ddeac49ac11744b79a5fd035f, branch master, repo: TestGitPluginRepo
2023-02-17 16:58:26,444+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.CommitIssueCollector] Init Date: 2023-02-17 16:58:22
2023-02-17 16:58:26,445+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.CommitIssueCollector] Processing commit 8f6591d81b3c2d2d6e3ca5e077c897f2f7d33b98, branch master, repo: TestGitPluginRepo
2023-02-17 16:58:26,445+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.CommitIssueCollector] Init Date: 2023-02-17 16:58:22
2023-02-17 16:58:26,446+0600 bigbrassband-gitplugin-RevisionIndexerImpl:thread - 1 DEBUG      [c.b.j.g.s.indexer.revisions.RevisionsIndexManagerImpl] Adding document for repository = 4; branch = master; revision = commit cfc0cedf48b59980169daa8eccf0f6bc340447cc 1544338819 -----sp”
```

## How to make sure only the dedicated node is reindexing?

1.  Switch to the Indexing Queue Viewer.

2.  Filter the tasks using _**Status: Indexing**_ to see only the integration being indexed in the current node.

3.  Use the Indexing queue ![](/wp-content/uploads/gij-refresh-icon.png) **Refresh** icon (bottom-left of the list) to reload the list while tasks in the queue is still being processed.

4.  Filter by different nodes to ensure that only the specific dedicated node(s) is indexing repositories. Dedicated node(s) can be setup via General settings ➜ _**Indexing: Allow all nodes to perform the repository indexing**_ option.

## How to see the progress of an integration index?

When an integration has pending indexing tasks, it becomes inconvenient to monitor its progress in the Manage integrations page using ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Show integration repositories**.

If you have an integration in <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>INDEXING</b> progress, then we recommend to use Indexing Queue Viewer instead:

1.  Switch to the Indexing Queue Viewer page then click the ![](/wp-content/uploads/gij-refresh-icon.png) **Refresh** icon at the bottom-left portion of the task list.

2.  Use the _**Status: Indexing**_ filter to see only the integration being indexed in the current node.

3.  Click <img src='/wp-content/uploads/gij-right-angle-bracket.png' /> to view the details for the indexing task that has the <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>INDEXING</b> status then copy the **Parent ID** value. The Parent ID for processed tasks are displayed on the filtered list. Since your integration is in <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>INDEXING</b> progress then the parent ID is the id you are interested in.

4.  Use this value into the Search bar on the filters panel then press Enter to do a filter search. The index queue will show results based on the set filters and search criteria.

5.  Click the ![](/wp-content/uploads/gij-refresh-icon.png) **Refresh** icon to reload the task list during the indexing process.

Here are some suggestions for _**Status**_ filter and search combination to control the displayed results:

*   Set **Status** to **Queued** and enter the value of the **Parent ID** into the Search bar to see the rest of the indexing tasks to be processed relating to the reindex of the integration.

*   Set **Status** to **Indexing** and enter the value of the **Parent ID** into the Search bar to see reindex tasks in progress relating to the reindex of the integration.

*   Set **Status** to **All** and enter the value of the **Parent ID** into the Search bar to see the full scope of tasks relating to the reindex of the integration.

## Why my repository hasn’t been removed yet?

You have removed a repository or integration and can still see it among repositories on Manage integrations page in <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>DISABLED</b> status for long time. This issue happens because the deletion task in still queued for processing. For instance, this could happen if General Settings ➜ **Scheduled jobs** ➜ **Repository reindexing** <u>interval</u> is lower than **Indexing Queue Viewer** ➜ **Last run duration** for scheduled indexing.

To resolve this issue:

1.  Go to the Indexing Queue Viewer.

2.  You should see a queue task with _**Remove repository**_ state in the last page. This is because deletion tasks have one of the lowest priorities in the indexing queue.

3.  Move this item to the top of the list via **...** Actions ➜ **Move to top**.

    a.  Do a couple of indexing list page refreshes (using the ![](/wp-content/uploads/gij-refresh-icon.png) **Refresh** icon) and see if the integration of repository is successfully removed.

    b.  In addition, the proper way is to set the value of _**Repository reindexing interval**_ to greater than the _**Last run duration**_ of the task in question for scheduled indexing. Otherwise, this issue may appear again.

## How to find a nested repository in ERROR state?

If you’re suspecting a indexing issue from a certain repository in an integration:

1.  Switch to Indexing Queue Viewer and set the filter to **Status: Error**. This will narrow down the list for queued index items with the <b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px; font-size: small;'>ERROR</b> status.

2.  View the logs of the error via **...** Actions ➜ **View log**. You may send the logs with errors or issues to us at [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com) for analysis.

