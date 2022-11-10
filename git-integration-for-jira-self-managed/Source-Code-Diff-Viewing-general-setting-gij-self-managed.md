---

title: Source Code Diff Viewing general setting
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
        For detailed information on this feature, see <a href='/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed'>Documentation: Viewing commit code diffs</a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 3.8.1</b><br>
        Git Integration for Jira adds three new settings in the General settings configuration page:
        <ul>
            <li>Repository Browser</li>
            <li>Source Code Diff Viewing (this page)</li>
            <li>Require user personal access tokens for branch and PR/MR creation</li>
        </ul>
    </div>
    </div>
</div>
<br>

<img src='/wp-content/uploads/gij-gitserver-gencfg-code-diff.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

This setting allows users to view source code commit diffs inside Jira:

*   Jira issues ➜ Git Commits tab

*   Jira issues ➜ Git Roll Up tab

*   Repository Browser ➜ file source code diff

*   Repository Browser ➜ Compare tab

<br>

The default setting is `Enabled` for new and existing Git Integration for Jira app installations. This setting is retained on restore/upgrade of the app.

If this setting is disabled (_unchecked_) in General settings, the above locations will not show the code diff or is not accessible to view to users. This also overrides repository and integration settings, by changing them to `Disabled`.

<br>

<p>&nbsp;</p>

## More on general settings

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

**Source Code Diff Viewing general setting** (this page)

[Require User PAT general setting](/git-integration-for-jira-data-center/require-User-PAT-general-setting-gij-self-managed)

[Enforce Git service permissions setting](/git-integration-for-jira-data-center/enforce-Git-service-permissions-gij-self-managed)

[Git roll up issue tab setting](/git-integration-for-jira-data-center/git-roll-up-tab-setting-gij-self-managed)

[Git commits issue and project tabs setting](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

[Git integration features settings](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

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

