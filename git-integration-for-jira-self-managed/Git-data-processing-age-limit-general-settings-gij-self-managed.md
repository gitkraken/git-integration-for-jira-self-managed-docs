---

title: Git data processing age limit
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
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'>General Settings</a> configuration page.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting resides in the <b>Advanced settings</b> in General settings.
    </div>
    </div>
</div>
<br>

The scripting feature now uses the global setting instead of hardcoded value (1 week).

<img src='/wp-content/uploads/gij-gitserverdc-git-data-proc-age-limit.png' style='display:block;max-width:100%;margin:30px auto' />

Set the value according to your organization’s requirements. The default value for this setting is **14 days**.

The commits or pull/merge requests are processed by Git Integration for Jira app if they are within the maximum age value (in days). Otherwise, they are skipped from processing.

_The commits are also compared against `on-commit.js` script file creation timestamp and if they are found to be older than the age limit value, they are skipped from processing._

_The pull/merge requests are also compared against `on-merge-req-ZZZ.js` script file creation timestamp and if they are found to be older than the age limit value, they are skipped from processing._

For more information about this feature, commands and debugging, see external page <a href='https://github.com/BigBrassBand/jira-git-workflow-hooks' target='_blank'>Git Integration for Jira: Git Workflow Hooks</a>.

## More on General settings (Advanced)

[Repository settings](/git-integration-for-jira-data-center/repository-settings-gij-self-managed)

[Repositories garbage collection checker](/git-integration-for-jira-data-center/repositories-garbage-collection-checker-gij-self-managed)

[Diff settings](/git-integration-for-jira-data-center/Diff-settings-gij-self-managed)

[Discard cloned files in Jira home directory](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-for-jira-data-center/git-operations-timeout-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

**Git data processing age** limit (this page)

