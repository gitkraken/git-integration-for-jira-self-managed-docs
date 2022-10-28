---

title: Scripting (Jira git workflow hooks)
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
        <b style='background-color:#EAE5FE; padding:1px 5px; color:#412C92; border-radius:3px; margin: 0 5px; font-size: small;'>ADVANCED</b> <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>DEVELOPERS</b><br>
        Requires Git Integration for JIra <b>v2.20+</b> or newer.
    </div>
    </div>
</div>
<br>


Use JavaScript as another workflow to operate Jira aside from Smart Commits with Git Integration for Jira app.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 3.8.0.4+</b><br>
        Debug logging is added to all places, from the initial point down to the script execution.
    </div>
    </div>
</div>
<br>

## Git Data Processing Age Limit (General settings)

The scripting feature now uses the global setting instead of hardcoded value (1 week).

![](/wp-content/uploads/gij-serverdc-global-settings-scripting-maxage.png?version=1&width=529&height=306)


Set the value according to your organization’s requirements. The default value for this setting is **14** days.

The commits or pull/merge requests are processed by Git Integration for Jira app if they are within the maximum age value (in days) relative to the time of reindexing. In other words. the age of commits/PRs is counted down from the moment when Git Integration for Jira app has started to process them for the first time. Otherwise, they are skipped from processing.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The commits are also compared against <code>on-commit.js</code> script file creation timestamp and if they are found to be older than the time of reindexing minus the maximum age value, they are skipped from processing.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The pull/merge requests are also compared against the creation timestamp of the following script files:
        <ul>
            <li><code>on-merge-req-created.js</code></li>
            <li><code>on-merge-req-updated.js</code></li>
        </ul>
        If they are found to be older than the time of reindexing minus the maximum age value, they are skipped from processing.
        <p>The Git Integration for Jira app checks for their timestamps, takes the lowest one of them (the earlier one), and then uses it for comparison.</p>
    </div>
    </div>
</div>
<br>

For more information about this feature, commands and debugging, see external page <a href='https://github.com/BigBrassBand/jira-git-workflow-hooks' target='_blank'><b>Git Integration for Jira: Git Workflow Hooks</b></a>.

<p>&nbsp;</p>

<br>
<br>

[**Prev:** Smart commits General setting](/git-integration-for-jira-data-center/smart-commits-general-setting-gij-self-managed)

[**Next:** Repository browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed)


