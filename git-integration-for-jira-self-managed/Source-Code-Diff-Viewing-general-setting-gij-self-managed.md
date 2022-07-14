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
        <b>VERSION 3.8.1</b><br>
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

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1947140173/gitserver-gencfg-code-diff.png?version=1&modificationDate=1631802604022&cacheVersion=1&api=v2&width=442&height=90)

[Source Code Diff Viewing](/git-integration-for-jira-data-center/source-code-diff-viewing-general-setting-gij-self-managed) allows users to view source code commit diffs inside Jira:

*   Jira issues ➜ Git Commits tab

*   Jira issues ➜ Git Roll Up tab

*   Repository Browser ➜ file source code diff

*   Repository Browser ➜ Compare tab

<br>

The default setting is `Enabled` for new and existing Git Integration for Jira app installations. This setting is retained on restore/upgrade of the app.

If this setting is disabled (_unchecked_) in General settings, the above locations will not show the code diff or is not accessible to view to users. This also overrides repository and integration settings, by changing them to `Disabled`.

