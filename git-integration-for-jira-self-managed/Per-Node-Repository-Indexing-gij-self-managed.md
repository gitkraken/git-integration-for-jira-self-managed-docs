---

title: Per Node Repository Indexing - General setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>NEW FEATURE</b>
<b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>DATA CENTER ONLY</b>

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

&nbsp;

### New General setting: Per Node Repository Indexing

<img src='/wp-content/uploads/gij-gitserver-gencfg-indexing-dc-nodes.png' style='display:block;margin:25px auto;max-width:100%' />


Set specific dedicated Jira Data Center (DC) nodes to perform Git Integration for Jira indexing jobs. The default setting is set to allow repository reindexing tasks to be performed on all Jira DC nodes.

&nbsp;

### Setting specific nodes for repository reindexing

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

![](/wp-content/uploads/gij-gitdc-gencfg-indexing-allow-all-nodes-specific.png)

The repository reindexing tasks will be performed only on the specified nodes. This mode will reduce the background processing load on the non-selected DC nodes.

### Sample Jira Data Center nodes configuration

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

<br>

&nbsp;

## More on general settings

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

[Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-Code-Diff-Viewing-general-setting-gij-self-managed)

[Require User PAT general setting](/git-integration-for-jira-data-center/require-User-PAT-general-setting-gij-self-managed)

[Enforce Git service permissions setting](/git-integration-for-jira-data-center/enforce-Git-service-permissions-gij-self-managed)

[Git roll up issue tab setting](/git-integration-for-jira-data-center/git-roll-up-tab-setting-gij-self-managed)

[Git commits issue and project tabs setting](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

[Git integration features settings](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

[Enable Automation for Jira general setting](/git-integration-for-jira-data-center/enable-Automation-for-Jira-general-setting-gij-self-managed)

[Audit log settings](/git-integration-for-jira-data-center/audit-log-settings-gij-self-managed)

[Branch and pull request settings (formerly Git Integration Options)](/git-integration-for-jira-data-center/branch-and-pull-request-settings-(formerly-Git-Integration-Options)-gij-self-managed)

[Email settings](/git-integration-for-jira-data-center/email-settings-gij-self-managed)

[Scheduled jobs settings](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

**Per node repository indexing setting** (this page)

[Repositories garbage collection checker settings](/git-integration-for-jira-data-center/Repositories-garbage-collection-checker-gij-self-managed)

[Diff settings](/git-integration-for-jira-data-center/Diff-Settings-gij-self-managed)

[Discard cloned files in Jira HOME directory setting](/git-integration-for-jira-data-center/Discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

