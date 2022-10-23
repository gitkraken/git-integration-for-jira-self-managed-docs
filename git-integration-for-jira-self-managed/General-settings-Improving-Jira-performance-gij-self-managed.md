---

title: General settings - Improving Jira performance
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

**What's on this page:**
- [Improving Git tags performance](#improving-git-tags-performance)
- [Improving diff load performance](#improving-diff-load-performance)
- [Enable/disable JQL search feature](#enabledisable-jql-search-feature)
- [Smart commits setting](#smart-commits-setting)
- [Commit Notification Emails](#commit-notification-emails)
- [Git Activity Stream](#git-activity-stream)
- [More related articles on Git for Jira administrators](#more-related-articles-on-git-for-jira-administrators)

<br>
<hr>
<br>

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
<br>

## Improving Git tags performance

Git tags and branches are cached for the most recently viewed 1000 Jira issues (across all Jira projects). The cache is reset each time a new change in any repository is detected. The cache is built the first time an issue with a tag and/or branch is loaded by a user. Subsequent loading of Jira issues with tag or branch information will utilize cached values.

Enabling the display of Git tags in commits for large repositories can affect the performance of Jira. This setting can be disabled by doing the following steps:

![](/wp-content/uploads/gij-gitserver-gencfg-git-tags-calc-cfg.png)

1.  Go to Jira dashboard menu Git ➜ **Manage repositories**.

2.  On your sidebar under Git Integration for Jira, select **General settings**.

3.  Under Issue Git integration panel options, uncheck the **Calculate and show Git tags in the Git Integration panel on issue pages** setting.

4.  Click **Save** to save and apply the setting.


## Improving diff load performance

There's a default limit to the size of files that the diff'er supports which is **16MB**. This is to keep a massive file from impacting the Jira server performance too much.

Jira administrators can control over the size of diffs allowed to be displayed in the code diff dialog:

1.  Go Jira dashboard menu Git ➜ **Manage repositories**. 
2.  On the sidebar under Git Integration for Jira, select **General settings**. 
3.  Scroll down to **Diff** then set the **Max Diff Line Count** value as desired.  Maximum supported value is 20000.

<img src='/wp-content/uploads/gij-docs-admin-general-cfg-diff-code-setting.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>NOTE!</b><br>
        Setting this value higher than the default value will impact the performance when loading the code diff of the selected file in the Git Commits tab. The code diff dialog will truncate the view for each 1500 lines code. To see the rest of the code, manually expand the view.
    </div>
    </div>
</div>

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
<br>

## Enable/disable JQL search feature

On your dashboard menu, go to Git ➜ Manage repositories ➜ **General settings** (sidebar). (Alternatively, go to Jira Administration ➜ Applications ➜ **General settings**).

![](/wp-content/uploads/gij-gitserver-gencfg-jql-search-loc2.png)

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
<br>

## Smart commits setting

<img src='/wp-content/uploads/gij-gitserver-edit-repocfg-smartcommits.png' style='display:block;margin:25px auto;max-width:100%' />

To improve performance, turn off smart commits on initial indexing then turn it back on after initial reindexing.

## Commit Notification Emails

![](/wp-content/uploads/gij-gitserver-gencfg-email-settings.png)

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
<br>

## Git Activity Stream

<img src='/wp-content/uploads/gij-gitserver-gencfg-git-activity-stream.png' style='display:block;margin:25px auto;max-width:100%' />

Enable/disable the setting whether to show git commits in the Jira activity stream (Issue page or dashboard widget) or not. For in-place upgrade of the Git Integration for Jira app, this setting is turned off by default. For new installation, the default setting is enabled.

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

<br>
<br>

[**Prev:** New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[**Next:** Adding a repository hosted on Windows Servers or Windows Network share \(Admins\)](/git-integration-for-jira-data-center/Adding-a-repository-hosted-on-Windows-Servers-or-Windows-Network-Share-(Admins)-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

**General settings: Improving Jira performance** (this page)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[Setting up webhooks](/git-integration-for-jira-data-center/setting-up-webhooks-gij-self-managed)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)

