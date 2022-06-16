---

title: Require User PAT general setting
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
        For detailed information on this feature, see [Documentation: Require user personal access tokens for branch and PR/MR creation](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 3.8.1</b><br>
        Git Integration for Jira adds three new settings in the General settings configuration page:
        <ul>
            <li>Repository Browser</li>
            <li>Source Code Diff Viewing</li>
            <li>Require user personal access tokens for branch and PR/MR creation (this page)</li>
        </ul>
    </div>
    </div>
</div>
<br>

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1947107395/gitserver-gencfg-req-pat-tokens.png?version=1&modificationDate=1647773429777&cacheVersion=1&api=v2&width=680&height=120)

When enabled, this setting requires Jira users to configure personal access tokens to allow them to create branches or pull requests from Jira.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1947107395/gitserver-create-branch-req-user-pat-enabled-aws.png?version=1&modificationDate=1631802924630&cacheVersion=1&api=v2)


The default setting is `Disabled` for new and existing Git Integration for Jira app installations. This setting is retained on restore/upgrade of the app.

If this setting is enabled (_checked_) in General settings, the users are required to setup personal access tokens for the connected repository and to be able to create branches and PR/MR from Jira. This general setting will override the repository and integration settings, regardless if they were set to `OFF`.

