---

title: General settings - Improving Jira performance
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Access these settings via Jira dashboard menu <b>Git</b> ➜ Manage repositories ➜ (sidebar) <b>General settings</b>.
    </div>
    </div>
</div>

## Improving Git tags performance

Git tags and branches are cached for the most recently viewed 1000 Jira issues (across all Jira projects). The cache is reset each time a new change in any repository is detected. The cache is built the first time an issue with a tag and/or branch is loaded by a user. Subsequent loading of Jira issues with tag or branch information will utilize cached values.

Enabling the display of Git tags in commits for large repositories can affect the performance of Jira. This setting can be disabled by doing the following steps:

![](/wp-content/uploads/gij-docs-admin-gitserver-gencfg-git-tags-calc-cfg.png)

1.  Go to Jira dashboard menu Git ➜ **Manage repositories**.

2.  On your sidebar under Git Integration for Jira, select **General settings**.

3.  Under Issue Git integration panel options, uncheck the **Calculate and show Git tags in the Git Integration panel on issue pages** setting.

4.  Click **Save** to save and apply the setting.


## Improving diff load performance

There's a default limit to the size of files that the diff'er supports which is **16MB**. This is to keep a massive file from impacting the Jira server performance too much.

As of **v2.8.5+** of the Git Integration for Jira app, Jira administrators can control over the size of diffs allowed to be displayed in the code diff dialog:

1.  Go Jira dashboard menu Git ➜ **Manage repositories**. 
2.  On the sidebar under Git Integration for Jira, select **General settings**. 
3.  Scroll down to **Diff** then set the **Max Diff Line Count** value as desired.  Maximum supported value is 20000.

    ![](/wp-content/uploads/gij-docs-admin-general-cfg-diff-code-setting.png)

**NOTE:** Setting this value higher than the default value will impact the performance when loading the code diff of the selected file in the Git Commits tab. The code diff dialog will truncate the view for each 1500 lines code. To see the rest of the code, manually expand the view.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting prevents the display of huge diffs. Thus, improving Jira performance.
    </div>
    </div>
</div>

## Enable/disable JQL search feature

INTRODUCED VERSION 2.12.0+

On your dashboard menu, go to Git ➜ Manage repositories ➜ **General settings** (sidebar). (Alternatively, go to Jira Administration ➜ Applications ➜ **General settings**).

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396229/gitserver-gencfg-jql-search-loc2.png?version=1&modificationDate=1630642785286&cacheVersion=1&api=v2)

Enable/disable the JQL searching setting.

This general setting allows administrators to enable/disable the JQL functions within the Git Integration for Jira app.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Turn off this setting to improve Jira performance.
    </div>
    </div>
</div>

## Smart commits setting

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396229/gitserver-edit-repocfg-smartcommits.png?version=1&modificationDate=1630642785514&cacheVersion=1&api=v2&width=442&height=91)

To improve performance, turn off smart commits on initial indexing then turn it back on after initial reindexing.

## Commit Notification Emails

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396229/gitserver-gencfg-email-settings.png?version=1&modificationDate=1630642785995&cacheVersion=1&api=v2&width=680&height=151)

Enable/disable the setting to allow sending of email notifications when a commit is made. This setting defaults to OFF for upgrades and ON for new installation of the Git Integration for Jira app.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Turn off this setting to improve Jira performance.
    </div>
    </div>
</div>

## Git Activity Stream

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396229/gitserver-gencfg-git-activity-stream.png?version=1&modificationDate=1630642786223&cacheVersion=1&api=v2&width=544&height=290)

Enable/disable the setting whether to show git commits in the Jira activity stream (Issue page or dashboard widget) or not. For in-place upgrade of the Git Integration for Jira app, this setting is turned off by default.  For new installation, the default setting is enabled.

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

