---

title: Show tracked or integration repositories
description: "Open the list of repositories inside a tracked folder or integration, filter it, and enable or disable individual repositories."
product: Git Integration for Jira Data Center
feature: Repository Setup
content_type: how-to
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2024-09
llms_include: true
tags: [tracked repositories, integration repositories, enable repository, disable repository, filter]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Show tracked or integration repositories"
    nav_order: 20
    nav_parent: "managing-repository-or-integration-configuration-gij-self-managed"
    page_type: "content"
---

On the <b>Manage Git Repositories</b> page, click the <img src='/wp-content/uploads/actions-icon.png' /> icon under the <b>Actions</b> column then select:

*   For tracked folders  –  **Show tracked repositories**.

*   For auto-connect integrations  –  **Show integration repositories**.


This action will open the **Integration** or **Tracked Folder** dialog showing the integration/tracked repositories:

<img src='/wp-content/uploads/gij-show-integration-repositories-dlg-n.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

Browse the tracked repositories/folder by clicking the page controls (if more than 10 repositories are connected).

In the filter field at the top right, enter a character or a name to display repositories that contains the search text.

> **Tip:** Enable/disable the state of the connected repositories under the <b>Enabled</b> column of the repository list.

> **Note:** The Repository Browser will not display the repository if it is disabled in the Git Repositories configuration. The commits and code diffs in the Issue ➜ <b>Git Commits</b>, <b>Git Roll Up</b> and <b>Project</b> tabs will also be unavailable due to this.

&nbsp;
* * *

[**Prev:** Managing integrations via Actions](/git-integration-for-jira-data-center/managing-integration-via-Actions-gij-self-managed)

[**Next:** Edit integration connection settings](/git-integration-for-jira-data-center/edit-integration-connection-settings-gij-self-managed)


