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

The Git Integration for Jira app introduces the General Settings page which contains configuration options for performance and features.

&nbsp;

## Getting started

Open the **General settings** page in the Jira Apps Management (**Applications** _page in Jira 8 and up_) to enable/disable features of the Git Integration for Jira Server/Data Center app.

The **General settings** configuration page can be accessed thru the following locations:

1.  Jira dashboard menu **Git** ➜ Manage repositories ➜ Git Integration for Jira (sidebar) ➜ **General settings**.

    ![](/wp-content/uploads/gij-jira-serverdc-gen-cfg-entry-point-one-c.png)

2.  Jira dashboard menu➜ **General settings**.

    ![](/wp=content/uploads/gij-jira-serverdc-gen-cfg-entry-point-two-c.png)

<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you're using Jira Cloud, <a href='/git-integration-for-jira-cloud/general-settings-gij-cloud'><b>view this page instead</b></a>.
    </div>
    </div>
</div>

&nbsp;

## Settings index

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-browser-general-setting-gij-self-managed)

[Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-Code-Diff-Viewing-general-setting-gij-self-managed)

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

&nbsp;
* * *
&nbsp;

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


For more details on git configuration, see [**Customizing Git: Git Configuration**](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration).

&nbsp;

## Advanced settings

These settings have optimal recommended default values and works out of the box -- unless further performance tweaks are needed:

*   [Repository settings](/git-integration-for-jira-data-center/repository-settings-gij-self-managed)

*   [Repositories garbage collection checker](/git-integration-for-jira-data-center/repositories-garbage-collection-checker-gij-self-managed)

*   [Diff settings](/git-integration-for-jira-data-center/diff-settings-gij-self-managed)

*   [Discard cloned files in Jira home directory](/git-integration-for-jira-data-center/discard-cloned-files-in-jira-home-directory-gij-self-managed)

*   [Git operations timeout](/git-integration-for-jira-data-center/git-operations-timeout-gij-self-managed)

*   [Git data processing age limit general setting](/git-integration-for-jira-data-center/Git-data-processing-age-limit-general-settings-gij-self-managed)

*   [Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

