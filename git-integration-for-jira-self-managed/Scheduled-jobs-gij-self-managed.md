---

title: Scheduled jobs general setting
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- GENERAL SETTINGS -->

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.
    </div>
    </div>
</div>

This setting allows administrators to configure duration of jobs and the GC checkers.

<img src='/wp-content/uploads/gij-gitserver-gencfg-scheduler-jobs.png' style='margin:25px auto;max-width:100%;display:block;' />

Scheduling jobs gives administrators control over when jobs run. These jobs can be scheduled in two ways:

*   **Scanning interval** – where jobs are scheduled on regular interval in minutes.

*   **Cron expression** – where jobs are scheduled via cron expression to run at specific timetables.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We recommend that scheduled jobs be given sufficient time to run completely on a regular basis.<br><br>
        Look at the Git Integration app job names in Jira Administration ➜ System ➜ <b>Scheduler details</b>:
        <ul>
            <li><code>com.bigbrassband.jira.git.jiraservices.jobs.GarbageCollectionJob</code></li>
            <li><code>com.bigbrassband.jira.git.jiraservices.jobs.RevisionIndexJob</code></li>
        </ul>
        <p style='margin-bottom:-10px;'>Expand them to observe schedule, duration, last run, duration, and next run.</p>
    </div>
    </div>
</div>

&nbsp;

### Scheduled Jobs

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px 0 0; font-size: small;'>VERSION 3.7+</b><br>
        <b>Repository reindexing</b> and <b>Garbage collection and revision validation checkers</b> settings are now moved into the <i>Scheduled Jobs</i> settings group.
    </div>
    </div>
</div>

&nbsp;

#### Repository reindexing

**Reindex interval**  –  Set the automatic reindex interval frequency value in minutes as required. Default value is _**5 minutes**_.

Configuration of the scheduler jobs are no longer accessible in the Jira administration page. For this case, the Git for Jira app offers Jira administrators this capability via the **General** screen. Minimum value is **1**. Maximum value is **76,861,433,640,456**. Only whole numbers are allowed.

&nbsp;

#### Garbage collection and revision validation checkers

**Job interval**  –  Set the number of minutes that will elapse before a repository is checked to see if it should be garbage collected.  The default value is _**1440 minutes**_.

For detailed information, see introductory article on [Scheduling Jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed).

&nbsp;

### More on general settings

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

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

**Scheduled jobs settings** (this page)

[Per node repository indexing setting](/git-integration-for-jira-data-center/Per-Node-Repository-Indexing-gij-self-managed)

[Repositories garbage collection checker settings](/git-integration-for-jira-data-center/Repositories-garbage-collection-checker-gij-self-managed)

[Diff settings](/git-integration-for-jira-data-center/Diff-Settings-gij-self-managed)

[Discard cloned files in Jira HOME directory setting](/git-integration-for-jira-data-center/Discard-cloned-files-in-Jira-home-directory-gij-self-managed)

[Git operations timeout](/git-integration-fpr-jira-data-center/git-operations-timeout-gij-self-managed)

[Git data processing age limit general setting](/git-integration-for-jira-data-center/Git-data-processing-age-limit-general-settings-gij-self-managed)

[Cache sizes settings](/git-integration-for-jira-data-center/cache-sizes-settings-gij-self-managed)

