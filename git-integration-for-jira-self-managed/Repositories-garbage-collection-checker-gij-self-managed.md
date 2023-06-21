---

title: Repositories garbage collection checker
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- GENERAL SETTINGS -->

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        These settings are part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed/'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 4.0.1+</b><br>
        This setting group is now moved to the <b>Advanced settings</b> in General settings.
    </div>
    </div>
</div>

<img src='/wp-content/uploads/gij-gitserver-gencfg-adv-repo-gcc.png' style='margin:25px auto;max-width:100%;display:block;' />

These group of settings control Git repositories garbage collection. Garbage collection process will prune all loose objects, pack loose references and repack all reachable objects into new pack files and remove the old ones.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The higher the change rate of the repository, the more often it would benefit from garbage collection.
    </div>
    </div>
</div>

This is a block of parameters that determine when the garbage collection task is triggered for the clones of your repositories. The garbage collection task is invoked whenever the number of loose objects or packed files exceeds the set limit.

&nbsp;

### Max loose objects count

Set the maximum number of loose objects that will be checked before the garbage collection task is triggered. The garbage collection is activated if the number of loose objects exceeds this setting. Loose objects are individual items that are not compressed into a Git pack file. The recommended default value is _**2000**_.

&nbsp;

### Max packed files count

Set the maximum number of packed files that will be checked before the garbage collection is triggered. If the number of packed files count exceeds this setting, the garbage collection is activated. The recommended default value is _**30**_.

&nbsp;

### More on general settings

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

**Repositories garbage collection checker settings** (this page)

[Diff settings](/git-integration-for-jira-data-center/Diff-Settings-gij-self-managed)

[Discard cloned files in Jira HOME directory setting](/git-integration-for-jira-data-center/Discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

