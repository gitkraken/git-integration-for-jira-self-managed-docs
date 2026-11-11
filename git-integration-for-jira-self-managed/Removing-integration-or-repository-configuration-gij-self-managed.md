---

title: Removing integration or repository configuration
description: "Delete an integration, repository or tracked folder from the Git Integration for Jira configuration list and optionally its cloned files."
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
last_verified: 2023-08
llms_include: true
tags: [remove integration, remove repository, tracked folder, cloned files, manage repositories]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Removing integration or repository configuration"
    nav_order: 100
    nav_parent: "managing-repository-or-integration-configuration-gij-self-managed"
    page_type: "content"
    card_icon: "database"
    card_color: "blue"
    card_description: "Delete an integration, repository or tracked folder from the Git Integration for Jira configuration list and optionally its cloned files"
---

Delete a repository or integration if it isn't needed or is broken in the Git Integration for Jira app configuration list.

<img src='/wp-content/uploads/gij-gitserver-remove-repo.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

1.  Go to the **Manage Git repositories** page for your Jira instance (_Jira dashboard menu Git ➜ Manage repositories_).

2.  `INTEGRATION` Click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Remove integration** for the selected integration configuration.

    `REPOSITORY` Click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Remove repository** for the selected repository configuration.

    `FOLDER` Click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Remove tracked folder** for the selected tracked folder configuration.

3.  The confirmation screen is displayed.

    Uncheck the **Also remove cloned Git repository files...** option to retain git repository files in the displayed path or leave it checked to also delete the repository files from the displayed path.

4.  Click **Delete** to remove the repository. Click **Cancel** to abort this process.

&nbsp;
* * *

[**Prev:** Viewing indexing logs](/git-integration-for-jira-data-center/viewing-indexing-logs-gij-self-managed)

[**Next:** Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed)

