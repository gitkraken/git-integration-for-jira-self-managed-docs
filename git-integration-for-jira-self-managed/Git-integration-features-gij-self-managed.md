---

title: Git integration features
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
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>
<br>

These group of settings affect how new commits are updated; how tags are displayed on Jira issues; and give administrators control -- if commit information in JQL searches and Git activity stream is shown or not.

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 3.9+</b> GitKraken deep linking integration is implemented.

<img src='/wp-content/uploads/gij-gitserver-gencfg-git-integration-options.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

**Settings index:**
- [GitKraken integration](#gitkraken-integration)
- [Jira issue updates](#jira-issue-updates)
- [Issue git integration panel](#issue-git-integration-panel)
- [JQL searching](#jql-searching)
- [Git activity stream](#git-activity-stream)
- [More on general settings](#more-on-general-settings)

<br>
<br>
<hr>
<br>
<br>

## GitKraken integration

Enable/disable GitKraken deep linking feature on Jira issue development panel and Git Commit tab. Clicking the deep links opens the respective commit, branches and repositories with GitKraken git client. For more information on this feature, see [Deep linking to the GitKraken client](/git-integration-for-jira-data-center/deep-linking-to-the-gitkraken-git-client-gij-self-managed).

## Jira issue updates

Enable/disable the setting to allow new commits to change the _Last Updated_ field.  Default is _**enabled**_.  For more information about this setting, see section [Reindexing – Reindex and updatedDate Filter](/git-integration-for-jira-data-center/reindexing-gij-self-managed).

Disabling this setting will improve Jira performance.

## Issue git integration panel

**Show Git integration panel on issue pages**  –  Enable/disable this setting to have Git Integration for Jira app show/hide the _Git Integration_ section on the Jira issue developer panel.

<img src='/wp-content/uploads/gij-jira-issue-dev-panel.png' style='display:block;margin:25px auto;max-width:100%' />

For more information, see [Jira git integration development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed).

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Disabling this setting will improve Jira performance.
    </div>
    </div>
</div>
<br>

**Calculate and show Git tags in the Git integration panel**  –  Enable/disable the setting to have Git Integration for Jira app calculate and show the Git tags in the Git Integration panel.

For more information, see [Git Tags](/git-integration-for-jira-data-center/git-tags-gij-self-managed).

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Disabling this setting will improve Jira performance.
    </div>
    </div>
</div>
<br>

## JQL searching

Enables/disables the ability to use the JQL functions within the Git Integration for Jira app.

The default state for new Git for Jira app installation is **Enabled**. This setting will be automatically enabled when doing an upgrade from previous versions of the Git Integration for Jira app.

For more information, see [JQL searching](/git-integration-for-jira-data-center/jql-searching-gij-self-managed).

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Disabling this setting will improve Jira performance.
    </div>
    </div>
</div>
<br>

## Git activity stream

Enable/disable the setting whether to show git commits in the Jira activity stream (Issue page or dashboard widget) or not.

For in-place upgrade of the Git Integration for Jira app, this setting is turned _off_ by default.  For new installation, the default state is enabled.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only the commits that are <a href='/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed'>linked to Jira issues</a> will show on the Jira Activity Stream (not all commits in repositories).
    </div>
    </div>
</div>
<br>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Disabling this setting will improve Jira performance.
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

**Git integration features settings** (this page)

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

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

