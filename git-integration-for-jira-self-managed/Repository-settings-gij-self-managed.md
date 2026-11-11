---

title: Repository settings (General setting)
description: "Set the maximum number of open pack files Git Integration for Jira uses, within your operating system limit, to tune performance."
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
last_verified: 2023-08
llms_include: true
tags: [max open pack files, repository settings, performance, advanced settings]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "administration-gij-self-managed"
    nav_label: "Repository settings (General setting)"
    nav_order: 140
    nav_parent: "general-settings-gij-self-managed"
    page_type: "content"
    card_icon: "settings"
    card_color: "amber"
    card_description: "Set the maximum number of open pack files Git Integration for Jira uses, within your operating system limit, to tune performance"
---

> **Info:** This setting is part of the <a href='/git-integration-for-jira-data-center/general-settings-gij-self-managed'><b>General Settings</b></a> configuration page.

> **Tip:** <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.0.1+</b><br>
> This setting is now moved to the <b>Advanced settings</b> in General settings.

<br>

<img src='/wp-content/uploads/gij-gitserver-gencfg-repo-max-open-pack-files.png' style='display:block;max-width:100%;margin:25px auto' />

&nbsp;

### Max open pack files count

Set the maximum number of open files the Git Integration for Jira app uses. For new Git Integration for Jira app install or upgrade, the default value is **16**. This is the **recommended** value.

You may set this value higher but NOT EXCEEDING the maximum number of open files allowed in the system.


The maximum number of open files vary for each operating system you are working with. The same units for each OS is used.

For systems that has a lot of connected repositories, increasing this value to a higher setting may improve the performance of the Git Integration for Jira app -- such as during repository browsing. This is also applicable to very busy systems that has large repository connections. Configure the maximum open files allowed by the system accordingly.

