---

title: Discard cloned files in Jira home directory
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
<div style-'color: red;'><b>DEPRECATED</b></div>

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
        This setting is part of the <a href='/git-integration-for-jira-self-managed/General-Settings'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 4.0.1+</b> This setting is now moved to the <b>Advanced settings</b> in General settings.
    </div>
    </div>
</div>

This feature will reduce Jira server storage by deleting files from cloned git repositories after indexing. Discarding files can save disk space but may limit some features such as displaying diffs of files.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1207828796/gencfg-discard-cloned-files.png?version=1&modificationDate=1613125343032&cacheVersion=1&api=v2)

There are three options to choose from:

*   **Keep all cloned binary files. No storage savings. All features available**  This option will leave all cloned repositories intact.

*   **Discard all files that match the mask below. Some features limited.**  This option will delete all files in the cloned repositories matching the declared file extensions.

*   **Discard all files EXCEPT those that match the mask below. Some features limited.**  This option will delete all other files in the cloned repositories except those files with extensions declared.


Select any option with the _discard_ label to enable editing of the file mask field.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For full list of features, version history and supported Jira version of the Git for Jira app, see <a href='https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions' target='_blank'>Git Integration for Jira app Version History</a>.
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

