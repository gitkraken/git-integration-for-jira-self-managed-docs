---

title: Disabling Source and Commits tabs
description: Hide the FishEye Source tab and the Jira DVCS Connector Commits tab from Jira issue pages by disabling their plugins in Manage apps.
product: Git Integration for Jira Data Center
feature: Git Commits Tab
content_type: how-to
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [source tab, commits tab, fisheye plugin, jira dvcs connector, manage apps]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Disabling Source and Commits tabs"
    nav_order: 110
    nav_parent: "documentation-gij-self-managed"
    page_type: "content"
    card_icon: "git-commit"
    card_color: "blue"
    card_description: "Hide the FishEye Source tab and the Jira DVCS Connector Commits tab from Jira issue pages by disabling their plugins in Manage apps"
---

The **Source** tab is part of the FishEye Plugin and is used for integration with SVN.  The **Commits** tab is part of the Jira DVCS Connector Plugin and is used for integration with gits _(Git, Mercurial, BitBucket etc.)_.

Atlassian enables these tabs by default.

> **Info:** If either <b>FishEye</b> or <b>Jira DVCS Connector</b> plugin is not installed, the <b>Source</b> or <b>Commits</b> tab will not be visible on the <b>Issues</b> page.

&nbsp;

## Hiding the Source tab

To hide the **Source** tab from the **Issues** page, disable the **FishEye Plugin**:

1.  On your Jira dashboard, go to ![](/wp-content/uploads/actions-icon.png) Jira Administration ➜ **Manage Apps**.

2.  Find and click **FishEye Plugin** under the installed add-ons to expand its options.

3.  Click **Disable**.

&nbsp;

## Hiding the Commits tab

To hide the **Commits** tab from the **Issues** page, disable the **Jira DVCS Connector Plugin**:

1.  On your Jira dashboard, go to ![](/wp-content/uploads/actions-icon.png) Jira Administration ➜ **Manage Apps**.

2.  Find and click **Jira DVCS Connector Plugin** under the installed add-ons to expand its options.

3.  Click **Disable**.

&nbsp;
* * *

[**Prev:** Web linking](/git-integration-for-jira-data-center/web-linking-gij-self-managed)

[**Next:** Linking git commits to Jira issues](/git-integration-for-jira-data-center/linking-git-commits-to-jira-issues-gij-self-managed)

