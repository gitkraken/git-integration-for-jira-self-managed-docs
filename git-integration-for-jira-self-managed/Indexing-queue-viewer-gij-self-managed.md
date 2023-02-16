---

title: Indexing queue viewer
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b>

![](/wp-content/uploads/gij-gitserver-gitmgr-indexing-queue-viewer.png)

## Introduction

Indexing is a very large part of Git Integration for Jira app. This indexing feature displays various task entries, allowing you to easily view upcoming and ongoing tasks such as repository indexing and garbage collection.

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-show-indexer-data.png)

The Indexing queue viewer displays detailed information such as:

*   when was the indexing started
*   when was the indexing finished
*   how much time it took the indexing to complete
*   ID of the task
*   on which node the indexing was processed <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>DATA CENTER</b>

## Highlights

Offering ease of use and scope of features, the Indexing queue viewer:

*   provides users greater visibility into what's happening with your repositories and system resources.

*   shows detailed information about the tasks - which node it was processed on, start time, finish time, processing time, task id, and more (mentioned above).

*   allows users to see which tasks are in the queue, find specific tasks by history, and filter tasks by specific parameters.

## Access location

This feature can be accessed via the Jira dashboard menu Git ➜ Indexing queue.

![](/wp-content/uploads/gij-gitserver-indexing-queue-mgr-loc-01.png)

## Indexing queue dashboard

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-dashboard.png)

The dashboard displays the current number of processing tasks and tasks in the queue.

Click **Clear queue** to free up the current queue of all tasks with <b style='background-color:#DEE0E5; padding:1px 5px; color:#44516C; border-radius:3px; margin: 0 5px; font-size: small;'>QUEUED</b> status.

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-gencfg-dashboard.png)

To the right of the dashboard is the settings view panel. which shows information related to the general settings for scheduled indexing, garbage collection, etc.

Click **Edit** to go directly to the General settings page.

## Filters and search

Just below the dashboard are controls for view filters. This section allow users to control which information is displayed on the screen.

![](/wp-content/uploads/gij-gitserver-dc-indexing-queue-group-of-data-filters.png)

These includes:

*   filter by _**status**_
*   filter by _**trigger**_
*   filter by _**type of operation**_
*   filter by _**node**_
*   filter by _**repository ID**_
*   filter by _**task ID**_
*   filter by _**parent task ID**_
*   filter by _**name**_ – case-sensitive:
    *   For ‘_**repository: Name**_’ -- this is a name comprising a group and a repository name.
    *   For '_**integration: Name**_' -- this is the name of the connected integration.

### Filter: Status

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-status-all.png)

Filter the task list by clicking on the **Status** dropdown and selecting a category:

*   **All** – The filter is not applied. Displays the data for every Status category.

*   **Queued** -- This filters the tasks by queued status. This indicates that the indexing tasks are still waiting in line to be processed or are still unfinished.

*   **Indexing** -- This filters the tasks by Indexing status. This indicates that the indexing task is already running.

*   **Indexed** -- This filters the tasks by Indexed status. This indicates that the indexing task has finished.

*   **Error** -- This filters the tasks by Error status. This indicates that the indexing task has encountered an error. Go to **...** Actions ➜ **View log** to see the error(s).

### Filter: Trigger

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-trigger-all.png)

Filters the task list by clicking on the **Trigger** dropdown and selecting a category:

*   **All** – The filter is not applied. Displays the data for every Trigger category.

*   **Manual** -- This filters the tasks by manual triggers. This includes user-triggered events such as:

    *   reindex repositories/integrations/reindex all

    *   reset all/reset repository

    *   reindex triggered by bulk import

    *   reindex triggered by Reindex REST API

    *   reindex triggered by an update of repository

*   **Webhook** -- This filters the tasks by webhook triggers. Indexing triggered by webhooks fall on this category. For related information, see [Webhook indexing explainer](Webhook-indexing-explainer-gij-self-managed).

*   **Scheduled** -- This filters the tasks by scheduled jobs. For more information, see [Scheduler jobs](Scheduler-jobs-gij-self-managed).

    *   App activity -- This filters the tasks by a reindex triggered by: 

    *   a branch creation/deletion

    *   a manipulation with pull request

    *   a change of commit issue association

    *   a repository update, e.g. by a change of main branch

*   **Initial indexing** -- This filters the tasks by initial indexing triggers. Initial indexing is performed by the app on the first connection of the git service integration.

### Filter: Type of operation

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-reindex-type-ops.png)

Filters the view by clicking on the **Type of operation** dropdown and selecting a category:

*   **All** – The filter is not applied. Displays the data for every Type of operation category.

*   **Reindex** – This filters the tasks related to indexing.

*   **Garbage Collection** – This filters the tasks related to Garbage Collection.

*   **Remove repository** – This filters the tasks related to removal of a repository.

### Filter: Node

![](/wp-content/uploads/gij-gitdc-indexing-queue-filter-nodes.png)

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>DATA CENTER</b>

Filters the view by clicking on the **Node** dropdown and selecting a category:

*   **All** – The filter is not applied. Displays the tasks for every Node in the cluster.

*   **Node\[1…\] - Node\[n\]** – This filters the tasks and displays data only for the specified node in the cluster.

### Using search to filter specific items to view

To the right of the view filter options, users can use the search bar to inquire for specific tasks and the list view will be updated accordingly. Note that filtering by name is case-sensitive.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Users may combine search text by repository ID, task ID, parent task ID and name – in one field.
    </div>
    </div>
</div>
<br>

## Sorting

Sorting allows users to arrange tasks by categories such as status, trigger, and type of operation. 

The default sort order applies the following rule:

1.  INDEXING – **first**

2.  QUEUED tasks (*see details below*):

    a.  raised to the top manually

    b.  reindex triggered manually:

        *   ![](/wp-content/uploads/actions-icon.png) Actions ➜ reindex repositories/integrations/reindex all

        *   ![](/wp-content/uploads/actions-icon.png) Actions ➜ reset all/reset repository

        *   via bulk import

        *   via Reindex REST API

        *   via an update from changes in the repository

    c.  triggered by webhooks

    d.  triggered by scheduled job

    e.  ![](/wp-content/uploads/actions-icon.png) Actions ➜ Remove repository/integration

    f.  Garbage Collection tasks

3.  FINISHED – **last**

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Summary of the sorting order</b><br>
        <ol style='margin-bottom:0px !important'>
            <li>The first few rows are tasks being currently processed and sorted by <b>Start time</b> in <u>ascending</u> order.</li>
            <li>Then, the queued tasks which are sorted in the order –  they will be processed from the queue.</li>
            <li>And the last rows – are completed tasks sorted by <b>Finish time</b> in <u>descending</u> order.</li>
        </ol>
    </div>
    </div>
</div>
<br>

## Viewing logs

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-actions-menu.png)

The ‘indexing status’ is displayed in the indexing log dialog that appears during manual reindex. The View log information from the **Indexing queue viewer** is similar to the logs that can be viewed in the Manage integration screen.

![](/wp-content/uploads/gij-gitserver-reindex-log-error.png)

For encountered errors when indexing, open the logs via Actions ➜ View log. Copy the message log and submit this to us thru [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com) for analysis. For the above example error, there are several factors that caused this error – the Git service is down, no internet connection, the webhook has changed or the personal access token has expired.

## Indexing queue list

On the next indexing run, the finished tasks for some repository are removed from the queue. This is regardless of the reindex trigger whether scheduled, webhook or manual. The max age for old finished tasks is 1 hour (see below).

The indexing queue does not remove the task from the queue when any of the following conditions is true:

*   this task is the last one of this type for this integration/repository

*   this task is not older than 1 hour from now

For removed integrations/repositories., the pending queued tasks related to removal are deleted from the indexing queue list.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px 5px 0; font-size: small;'>DATA CENTER</b><br>
        The indexing queue can spread the indexing work across several nodes. Thus, the most volume of the indexing tasks will be performed on a multi-node Jira. We recommend using a 4-node configuration.
    </div>
    </div>
</div>
<br>

### View indexing details

![](/wp-content/uploads/gij-gitserver-indexing-queue-viewer-show-indexer-data.png)

On the left of the first column, click the **\>** symbol to expand the detailed view of the index task in the queue.

### Finish time

In this column, the amount of time from when the task has finished indexing is shown.

### Integration name

This column displays the name of the integrations where indexing tasks has been performed.

### Repository name

This column displays the name of the repositories where indexing tasks has been performed. Also displayed is the organization (GitHub) or group (GitLab) name before the repository name indicating it’s under that org or group.

### Type of operation

The type of operation states what kind of indexing was triggered:

*   Reindex
*   Webhook
*   Scheduled
*   Manual
*   Garbage collection
*   Remove

### Delay

This column shows _**No delay**_ for indexed items that were processed immediately after the previous one.

### Trigger

This column shows what kind of operation triggered the reindex for this task.

### Status

This column shows the indexing status of the task in the list.

### Refresh function

At the bottom-left portion of the indexing queue viewer, click the **Refresh** icon to refresh the queue list view.

### Pagination

At the bottom-right portion of the indexing queue viewer, use the page controls to navigate across the task page list.

