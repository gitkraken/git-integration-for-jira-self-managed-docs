---

title: General Settings
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The General Settings page is only accessible to Jira Administrators.
    </div>
    </div>
</div>
<br>

The Git Integration for Jira app introduces the General Settings page which contains configuration options for performance and features.

## Getting started

Open the **General settings** page in the Jira Apps Management (**Applications** _page in Jira 8 and up_) to enable/disable features of the Git Integration for Jira Server/Data Center app.

The **General settings** configuration page can be accessed thru the following locations:

1.  Jira dashboard menu **Git** ➜ Manage repositories ➜ Git Integration for Jira (sidebar) ➜ **General settings**.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/966852655/jira-serverdc-gen-cfg-entry-point-(c).png?version=3&modificationDate=1613118421121&cacheVersion=1&api=v2)


2.  Jira dashboard menu➜ **General settings**.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/966852655/jira-serverdc-gen-cfg-entry-point-two-(c).png?version=3&modificationDate=1613118421140&cacheVersion=1&api=v2)

<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you're using Jira Cloud, <a href='/git-integration-for-jira-cloud/general-settings-gij-cloud/'><b>view this page instead</b></a>.
    </div>
    </div>
</div>
<br>

## Settings index

*   [Git roll up issue tab](/git-integration-for-jira-data-center/git-roll-up-issue-tab-gij-self-managed)

*   [Git commits issue and project tabs](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

*   [Git integration features](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

*   [Branch and pull request settings (formerly Git Integration Options)](/git-integration-for-jira-data-center/branch-and-pull-request-settings-formerly-git-integration-options-gij-self-managed)

*   [Email settings](/git-integration-for-jira-data-center/email-settings-gij-self-managed)

*   [Scheduled jobs](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

*   [Audit log settings](/git-integration-for-jira-data-center/audit-log-settings-gij-self-managed)

*   [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

*   [Repository Browser general setting](/git-integration-for-jira-data-center/repository-browser-general-setting-gij-self-managed)

*   [Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-code-diff-viewing-general-setting-gij-self-managed)

*   [Require User PAT general setting](/git-integration-for-jira-data-center/require-user-pat-general-setting-gij-self-managed)

*   [Enable Automation for Jira general setting](/git-integration-for-jira-data-center/Enable-automation-for-jira-general-setting)

*   [Enforce Git service permissions](/git-integration-for-jira-data-center/enforce-git-service-permissions-gij-self-managed)

*   [Per Node Repository Indexing](/git-integration-for-jira-data-center/per-node-repository-indexing-gij-self-managed)

* * *

After making changes to the configuration settings, click **Save** to apply the changes.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Every git installation has global config file and .git/config file in every git repository. All settings at the global level can be overridden at the repository level. Therefore, different email addresses can be set for every git repository.
    </div>
    </div>
</div>
<br>

For more details on git configuration, see [**Customizing Git: Git Configuration**](http://git-scm.com/book/en/Customizing-Git-Git-Configuration).

## Advanced settings

These settings have optimal recommended default values and works out of the box -- unless further performance tweaks are needed:

*   [Repository settings](/git-integration-for-jira-data-center/repository-settings-gij-self-managed)

*   [Repositories garbage collection checker](/git-integration-for-jira-data-center/repositories-garbage-collection-checker-gij-self-managed)

*   [Diff settings](/git-integration-for-jira-data-center/diff-settings-gij-self-managed)

*   [Discard cloned files in Jira home directory](/git-integration-for-jira-data-center/discard-cloned-files-in-jira-home-directory-gij-self-managed)

*   [Git operations timeout](/git-integration-for-jira-data-center/git-operations-timeout-gij-self-managed)

*   [Smart commits setting](/git-integration-for-jira-data-center/smart-commits-setting-gij-self-managed)

*   [Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

