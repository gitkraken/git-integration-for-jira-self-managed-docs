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
        <b style='color: #672C92; background-color: #EAE5FE; padding: 0 3px'>VERSION 3.8+</b>&nbsp; <b style='color: #192862; background-color: #FFF1B6; padding: 0 3px'>NEW FEATURE</b>
    </div>
    </div>
</div>

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
<br>

These settings affect which audit logs are displayed on the Jira system administration audit log page.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207828866/gitserver-gencfg-audit-log.png?version=1&modificationDate=1647771827039&cacheVersion=1&api=v2&width=557&height=108)

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
<br>

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
<br>

## Enable audit logging

This setting enables/disables audit logging for the Git Integration for Jira app. This setting is set to ON for new app installations and is set to OFF on app upgrades by default.

## Audit log events

Click **Advanced** to expand the audit log events. Enable/disable event items to turn tracking ON/OFF for specific events.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828866/jira-server-gencfg-audit-log-advanced.png?version=1&modificationDate=1613126222038&cacheVersion=1&api=v2)

## View Jira audit log

Click this label link to take you to the Jira administrator system Audit log page. Alternatively, go to Jira administration ➜ System ➜ **Audit log**.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828866/jira-server-audit-log-navigation.png?version=1&modificationDate=1613126221574&cacheVersion=1&api=v2)

Below is an example of the logs audited of the selected events from the **Audit logs - General settings**:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828866/jira-audit-log-example.png?version=1&modificationDate=1613126221815&cacheVersion=1&api=v2)

