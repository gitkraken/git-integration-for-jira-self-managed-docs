---

title: How to see if some reindex has stuck?
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

There is a situation where the indexing process has stuck for some tasks.

Start from the Manage integrations page and check the integration with the <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>SCANNING</b> status.

<ol>
    <li>
        Go to <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Show integration repositories</b>. You may see some <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>QUEUED</b> or <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>FETCHING</b> status in the list and is somewhat taking a bit longer to process.
    </li>
    <li>
        Go to the Indexing queue viewer and you may see the same status for some indexing tasks.
    </li>
    <li>
        Open <img src='/wp-content/uploads/actions-icon.png' /> Jira System administration then click Logging and profiling on the left sidebar.
    </li>
    <li>
        Under the <b>Default loggers section</b>, click <b>Configure</b>.

Set Package name to com.bigbrassband.jira.git.services.indexer.

Set Logging Level to DEBUG.

Click Add to proceed.

Go back to the Indexing queue viewer page and click Refresh at the bottom of the list view to reload the list.

To view the logs for analysis:

Click Actions ➜ View log to view the indexing logs. You may send the logs with errors or issues to us at gijsupport@gitkraken.com for analysis.