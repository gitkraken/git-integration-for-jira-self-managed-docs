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
<br>

The settings in this group controls email notifications and recipient filters.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795941/gitserver-gencfg-email-settings.png?version=1&modificationDate=1647774129291&cacheVersion=1&api=v2&width=678&height=181)

## Send commit notification emails

Enable/disable the setting to allow sending of email notifications when a commit is made.  This setting defaults to OFF for our app upgrades and ON for new installations of the Git Integration for Jira app.  This setting also enables/disables email notifications related to smart commits.

In the provided box, enter a regular expression to send e-mail only to addresses that matches this pattern.  Leave this field blank to disable this filter.

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

