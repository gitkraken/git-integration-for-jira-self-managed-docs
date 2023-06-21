---

title: Audit log settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 3.8+</b>&nbsp; <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b>
    </div>
    </div>
</div>

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

These settings affect which audit logs are displayed on the Jira system administration audit log page.

<img src='/wp-content/uploads/gij-gitserver-gencfg-audit-log.png' width=627 height=122 style='display:block;margin:25px auto;max-width:100%' />

With auditing feature, key activities are tracked on the Jira instance. This provides administrators insight on how the way the instance is being used.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The new audit log will help administrators:
        <ul>
            <li>manage their log more effectively;</li>
            <li>decide which of the coverage areas to audit; and</li>
            <li>select how detailed they want their log to be.</li>
        </ul>
    </div>
    </div>
</div>

The audit log functionality is also extended to Jira Data Center instances as it will have more coverage areas, various event volume levels and an option to integrate the audit log file with external tools.

For more information on the audit log and it’s new functions, see [**this article**](https://confluence.atlassian.com/jiracore/audit-log-improvements-989762528.html).

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Performance</b><br>
        Using this feature affects database performance. Administrators can select only needed log events to audit to improve performance.
    </div>
    </div>
</div>

&nbsp;

### Enable audit logging

This setting enables/disables audit logging for the Git Integration for Jira app. This setting is set to ON for new app installations and is set to OFF on app upgrades by default.

&nbsp;

### Audit log events

<img src='/wp-content/uploads/gij-jira-server-gencfg-audit-log-advanced.png' width=272 height=528 style='display:block;margin:25px auto;max-width:100%;' />

Click **Advanced** to expand the audit log events. Enable/disable event items to turn tracking ON/OFF for specific events.

&nbsp;

### View Jira audit log

Click this label link to take you to the Jira administrator system Audit log page. Alternatively, go to Jira administration ➜ System ➜ **Audit log**.

![](/wpcontent/uploads/gij-jira-server-audit-log-navigation.png)

Below is an example of the logs audited of the selected events from the **Audit logs - General settings**:

![](/wp-content/uploads/gij-jira-audit-log-example.png)

&nbsp;

### More on general settings

[Git roll up issue tab](/git-integration-for-jira-data-center/git-roll-up-tab-setting-gij-self-managed)

[Git commits issue and project tabs](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

[Git integration features](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

[Branch and pull request settings (formerly Git Integration Options)](/git-integration-for-jira-data-center/branch-and-pull-request-settings-(formerly-Git-Integration-Options)-gij-self-managed)

[Email settings](/git-integration-for-jira-data-center/email-settings-gij-self-managed)

[Scheduled jobs](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

**Audit log settings** (this page)

[General settings](/git-integration-for-jira-data-center/general-Settings-gij-self-managed)

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

[Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-Code-Diff-Viewing-general-setting-gij-self-managed)

[Enforce Git service permissions](/git-integration-for-jira-data-center/enforce-Git-service-permissions-gij-self-managed)

[Enable Automation for Jira general setting](/git-integration-for-jira-data-center/enable-Automation-for-Jira-general-setting-gij-self-managed)

[Require User PAT general setting](/git-integration-for-jira-data-center/require-User-PAT-general-setting-gij-self-managed)

