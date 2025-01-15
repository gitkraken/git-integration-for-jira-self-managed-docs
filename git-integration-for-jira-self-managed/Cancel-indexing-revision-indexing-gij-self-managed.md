---

title: Cancel indexing
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.23+</b> <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b>

### Introduction

Reindexing may take a very long time to complete due to some reasons such as handling very large repositories, indexing issues, or very low system resources. This feature is introduced to allow Jira administrators to interrupt an indexing process once it has been queued or has already started.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note:</b>
        The index data remains as is at the moment of cancellation of the reindex task.
    </div>
    </div>
</div>

The Cancel action interrupts:

*   a revision indexing phase of a repository reindex
*   a scanning phase of an integration reindex
*   a tags topology calculation

It does not cover the following cases, such as a cancellation of:

*   Garbage Collection task
*   Remove repository task
*   Garbage Collection All task
*   Pull/merge requests indexing phase

&nbsp;

### Highlights

There are three (3) ways a reindex can be interrupted by performing the following methods:

1.	Indexing queue viewer ➜ **...** (Actions) ➜ **Cancel** reindex context-menu <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.23</b>

	This marks the reindexing task as **CANCELED**. It's like a suspended task and it can be resumed later on with a manual reindex.

2.	Manage repositories ➜ ![](/wp-content/uploads/actions-icon.png) Actions ➜ disable a repository/integration.

    **This does not interrupt a reindex thread but skip it instead.** Subsequent reindex will resume the indexing process.

    Starting v4.23+, disabling a repository/integration behaves in the same way as the Cancel action from the Indexing queue viewer page.

3.	Disable the Git Integration for Jira app in the Jira **Manage apps** page. This will absolutely interrupt the reindex thread.

&nbsp;

### Access location

The **Cancel** indexing task can be only accessed at the following location:

*   Indexing queue viewer ➜ **...** (actions) ➜ **Cancel** (context menu)

    ![](/wp-content/uploads/gij-gitserverdc-indexing-queue-cancel-reindex-action.png)

&nbsp;

### CANCELED status

A new CANCELED status is available to the indexing queue task state. Additionally, the **Cancel** function is implemented to the Actions (...) menu on the Indexing queue viewer page. The indexed data remains as is at the moment of cancellation of the reindex task. Likely, subsequent reindex will just fix them along the way.

![](/wp-content/uploads/gij-gitserverdc-indexing-queue-cancel-status.png)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        On the Indexing queue viewer page, tasks with CANCELED status are displayed when Filter: INDEXING or Filter: CANCELED is selected. You can resume this indexing task at a later time from the Manage repositories page ➜ Actions ➜ Reindex repository/integration.
    </div>
    </div>
</div>

The CANCELED status is also implemented in the Manage repositories configuration list.

![](/wp-content/uploads/gij-gitserverdc-gitmgr-cancel-status.png)

Jira administrators can resume the CANCELED status via ![](/wp-content/uploads/actions-icon.png) Actions ➜ Reindex repository/integration.

&nbsp;

### How does canceling affect the initial reindex?

![](/wp-content/uploads/gij-gitserverdc-queue-initial-indexing.png)

The initial reindex happens after a repository/integration is connected and when it is the very first reindex of a repository/integration, where:

*   Smart commits processing is skipped on initial reindex
*   Automation for Jira triggers are not triggered
*   Any script execution due to initial indexing are ignored
*   The `lastUpdated` field on the initial reindex is not updated.

If the initial reindex is canceled, the Git Integration for Jira indexing engine will remember that the initial reindex hasn't been finished yet. You'll also notice that **Git Commits tab**, **Git Roll Up tab** and **Git Integration developer panel** on the Jira Issue page does not contain git data because the git connection is in an 'unfinished' state. We recommend that the initial reindex is not interrupted.

&nbsp;

### How long does reindex take?

Reindex usually completes in several seconds to a couple of hours or maybe more depending on the factors stated below.

*   how powerful is the host hardware

*   how large is the repository, based on:

    *   the average number of commits in a branch ([see below](#how-to-know-the-average-number-of-commits-in-a-branch))

    *   the number of branches

    *   the number of pull/merge requests

    *   the number of tags

    *   the amount of large files

*   the amount of remaining system resources

*   (Gerrit) how many nested repositories are there

*   (Tracked folders) how many nested folders (repositories) are there

*   (Data Centers) how many nodes are there

&nbsp;

### How does canceling reindex affect queued Data Center nodes?

A reindex of the task is canceled on all Jira nodes.

&nbsp;

### How to know the average number of commits in a branch?

If your main branch is "master", then the next command call from the root of your repository clone will return the average number:

```powershell
git branch -r | xargs -i git rev-list --count {} ^master | grep -v 0 | awk 'BEGIN{s=0;}{s+=$1;}END{print s/NR;}'
```

If the value is greater than 1000, it will impact the indexing performance.

The following command will return number of commits , which will be reindexed on an initial reindex:

```powershell
git branch -r | xargs -i git rev-list --count {} ^master | grep -v 0 | awk 'BEGIN{s=0;}{s+=$1;}END{print s;}'
```

&nbsp;

### Can I cancel delete operations?

The cancel action is not supported on delete operations.

&nbsp;

### See more Git Integration for Jira app features

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

**Cancel indexing** (this page)

[Pull request filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Tag filters](/git-integration-for-jira-data-center/tag-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Indexing queue viewer](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/) (Git Integration for Jira Data Center)

[Deep linking feature](/git-integration-for-jira-data-center/deeplinking-feature-gij-self-managed/) (Git Integration for Jira Data Center)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + ScriptRunner](/git-integration-for-jira-data-center/gij-plus-scriptrunner-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + Jira Automation](/git-integration-for-jira-data-center/git-integration-plus-jira-automation-gij-self-managed/) (Git Integration for Jira Data Center)

[Enforced git permissions for Jira users – Features](/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed/) (Git Integration for Jira Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/shared-reindex-queue-between-dc-nodes-gij-self-managed/) (Git Integration for Jira Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed/) (Git Integration for Jira Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/) (Git Integration for Jira Data Center)

[Issue Git integration panel – Features](/git-integration-for-jira-data-center/issue-git-integration-panel-gij-self-managed/) (Git Integration for Jira Data Center)

