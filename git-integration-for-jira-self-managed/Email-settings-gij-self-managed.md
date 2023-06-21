---

title: Email settings
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
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed/'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

The settings in this group controls email notifications and recipient filters.

<img src='/wp-content/uploads/gij-gitserver-gencfg-email-settings.png' style='display:block;margin:25px auto;max-width:100%;' />

&nbsp;

### Send commit notification emails

Enable/disable the setting to allow sending of email notifications when a commit is made. This setting defaults to OFF for our app upgrades and ON for new installations of the Git Integration for Jira app. This setting also enables/disables email notifications related to smart commits.

In the provided box, enter a regular expression to send e-mail only to addresses that matches this pattern. Leave this field blank to disable this filter.

No notifications are sent when this setting is off, if the provided regex box is blank, or regular expression doesn't have a match.

For more information, see [**Commit Email Notifications**](/git-integration-for-jira-data-center/commit-email-notifications-gij-self-managed).

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        To avoid the possibility to set invalid regular expressions in the provided regex box, the <b>To address</b> must match the regex pattern.
    </div>
    </div>
</div>

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

**Email settings** (this page)

[Scheduled jobs settings](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

[Per node repository indexing setting](/git-integration-for-jira-data-center/Per-Node-Repository-Indexing-gij-self-managed)

[Repositories garbage collection checker settings](/git-integration-for-jira-data-center/Repositories-garbage-collection-checker-gij-self-managed)

[Diff settings](/git-integration-for-jira-data-center/Diff-Settings-gij-self-managed)

[Discard cloned files in Jira HOME directory setting](/git-integration-for-jira-data-center/Discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

