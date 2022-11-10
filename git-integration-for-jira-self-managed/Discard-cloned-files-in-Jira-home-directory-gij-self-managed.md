---

title: Discard cloned files in Jira home directory
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#FFEBE6; padding:1px 5px; color:#C02909; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>DEPRECATED</b>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This feature is deprecated and will be removed from the product after August 15, 2022.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is part of the <a href='/git-integration-for-jira-data-center/General-settings-gij-self-managed'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 4.0.1+</b> This setting is now moved to the <b>Advanced settings</b> in General settings.
    </div>
    </div>
</div>
<br>

This feature will reduce Jira server storage by deleting files from cloned git repositories after indexing. Discarding files can save disk space but may limit some features such as displaying diffs of files.

<img src='/wp-content/uploads/gij-gitserver-discard-cloned-files-gencfg.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

There are three options to choose from:

*   **Keep all cloned binary files. No storage savings. All features available**  This option will leave all cloned repositories intact.

*   **Discard all files that match the mask below. Some features limited.**  This option will delete all files in the cloned repositories matching the declared file extensions.

*   **Discard all files EXCEPT those that match the mask below. Some features limited.**  This option will delete all other files in the cloned repositories except those files with extensions declared.

<br>

Select any option with the _discard_ label to enable editing of the file mask field.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For full list of features, version history and supported Jira version of the Git for Jira app, see <a href='https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions' target='_blank'><b>Git Integration for Jira app Version History</b></a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Whenever the setting is changed, BigBrassBand recommends to perform a manual reclone of the repositories to ensure an error-free operation.
    </div>
    </div>
</div>
<br>

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

**Discard cloned files in Jira HOME directory setting** (this page)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

