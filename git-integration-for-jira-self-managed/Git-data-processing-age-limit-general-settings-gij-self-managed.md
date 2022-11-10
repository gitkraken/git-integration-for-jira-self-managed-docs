---

title: Git data processing age limit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'>General Settings</a> configuration page.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting resides in the <b>Advanced settings</b> in General settings.
    </div>
    </div>
</div>
<br>

**NOTE:** This setting replaces the Smart commit max age setting.

The scripting feature now uses the global setting instead of hardcoded value (1 week).

<img src='/wp-content/uploads/gij-gitserverdc-git-data-proc-age-limit.png' style='display:block;max-width:100%;margin:30px auto' />

Set the value according to your organization’s requirements. The default value for this setting is **14 days**.

The commits or pull/merge requests are processed by Git Integration for Jira app if they are within the maximum age value (in days). Otherwise, they are skipped from processing.

_The commits are also compared against `on-commit.js` script file creation timestamp and if they are found to be older than the age limit value, they are skipped from processing._

_The pull/merge requests are also compared against `on-merge-req-ZZZ.js` script file creation timestamp and if they are found to be older than the age limit value, they are skipped from processing._

For more information about this feature, commands and debugging, see external page <a href='https://github.com/BigBrassBand/jira-git-workflow-hooks' target='_blank'>Git Integration for Jira: Git Workflow Hooks</a>.

<p>&nbsp;</p>

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

[Per node repository indexing setting](/git-integration-for-jira-data-center/Per-Node-Repository-Indexing-gij-self-managed)

[Repositories garbage collection checker settings](/git-integration-for-jira-data-center/Repositories-garbage-collection-checker-gij-self-managed)

[Diff settings](/git-integration-for-jira-data-center/Diff-Settings-gij-self-managed)

[Discard cloned files in Jira HOME directory setting](/git-integration-for-jira-data-center/Discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

**Git data processing age limit general setting** (this page)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

