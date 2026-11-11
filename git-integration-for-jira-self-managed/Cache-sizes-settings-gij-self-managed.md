---

title: Cache sizes settings
description: "Tune the revision, branch, and tag cache sizes Git Integration for Jira keeps in memory and estimate a good value for your instance."
product: Git Integration for Jira Data Center
feature: General Settings
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [cache sizes, revision cache, branch cache, tags cache, memory, advanced settings]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "administration-gij-self-managed"
    nav_label: "Cache sizes settings"
    nav_order: 200
    nav_parent: "general-settings-gij-self-managed"
    page_type: "content"
    card_icon: "settings"
    card_color: "amber"
    card_description: "Tune the revision, branch, and tag cache sizes Git Integration for Jira keeps in memory and estimate a good value for your instance"
---

> **Info:** These settings are part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.

> **Tip:** <b>VERSION 4.0.1+</b><br>
> This setting group is now moved to the <b>Advanced settings</b> in General settings.

&nbsp;

### What is revision cache size?

It displays how many commits/revisions are stored in the memory. The cache size is measured per piece where the approximate revision size is 256 bytes. For instance, there are 4000 revisions per 1 Mb. Set the revision cache size value to 4000 to allocate 1Mb of heap for the cache.

<img src='/wp-content/uploads/gij-gitserver-gencfg-cache-sizes-new.png' style='margin:25px auto;max-width:100%;display:block;' />

The above settings are the sizes of their respective memory cache. Higher values can affect the performance of the retrieved revisions from Git.

&nbsp;

### Revision cache size

_Required._  This is the number of revisions that will be kept as cache in memory for quick retrieval – per piece is 256 bytes. The default value for this setting is **180,000**. (approx. ~44Mb)

&nbsp;

### Branch cache size

_Required._  This is the number of branches that will be kept as cache in memory for quick retrieval --per piece is 500 bytes. The default value for this setting is **28,000**. (approx. ~13Mb+)

&nbsp;

### Tags cache size

_Required._  This is the number of tags that will be kept in cache memory for quick retrieval – per piece is 1000Kb.  The default value for this setting is **500**. (approx. ~488Mb+)

&nbsp;
* * *

### Where do I start on how to get the best value setting?

Calculating for the most desirable value depends on the following factors such as how many issues are currently active; and how many commits are associated with the active issues on average. For example, if you have 100 active issues and multiply it by 10 commits per issue, you’ll get around 1000 commits. This is considered a minimal amount.

```perl
100 active issues x 10 (average commits per issue) ≈ 1000 commits
```

> **Info:** When the Git Integration for Jira app can’t find a commit in the internal cache, it will start reading for commits from the disk. Read operations finish much quicker when performed from the memory compared to when reading from the disk.

&nbsp;

### More on General settings

[Git roll up issue tab](/git-integration-for-jira-data-center/git-roll-up-tab-setting-gij-self-managed)

[Git commits issue and project tabs](/git-integration-for-jira-data-center/git-commits-issue-and-project-tabs-gij-self-managed)

[Git integration features](/git-integration-for-jira-data-center/git-integration-features-gij-self-managed)

[Branch and pull request settings (formerly Git Integration Options)](/git-integration-for-jira-data-center/branch-and-pull-request-settings-(formerly-Git-Integration-Options)-gij-self-managed)

[Email settings](/git-integration-for-jira-data-center/email-settings-gij-self-managed)

[Scheduled jobs](/git-integration-for-jira-data-center/scheduled-jobs-gij-self-managed)

[Audit log settings](/git-integration-for-jira-data-center/audit-log-settings-gij-self-managed)

[General settings](/git-integration-for-jira-data-center/general-Settings-gij-self-managed)

[Repository Browser general setting](/git-integration-for-jira-data-center/repository-Browser-general-setting-gij-self-managed)

[Source Code Diff Viewing general setting](/git-integration-for-jira-data-center/source-Code-Diff-Viewing-general-setting-gij-self-managed)

[Enforce Git service permissions](/git-integration-for-jira-data-center/enforce-Git-service-permissions-gij-self-managed)

[Enable Automation for Jira general setting](/git-integration-for-jira-data-center/enable-Automation-for-Jira-general-setting-gij-self-managed)

[Require User PAT general setting](/git-integration-for-jira-data-center/require-User-PAT-general-setting-gij-self-managed)

**Cache sizes settings** (this page)