---

title: Commit email notifications
description: "See the permissions needed to receive commit email notifications and where to configure them in General settings, repository settings and your user profile."
product: Git Integration for Jira Data Center
feature: Commit Email Notifications
content_type: overview
audience: all
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [commit email notifications, permissions, general settings, user profile, repository settings]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Commit email notifications"
    nav_order: 80
    nav_parent: "documentation-gij-self-managed"
    page_type: "content"
---

This setting allows an individual user to receive or to stop receiving any of the notification emails.

&nbsp;

## Permissions

The user must have the following permissions to get notifications:

*   developer access to the project

*   developer access to at least one project which is mapped to the repository

*   developer access to at least one project and the repository is mapped to all projects.

&nbsp;

### Settings

Access the settings for this feature via:

1. Git for Jira app **General Settings.**

    ![](/wp-content/uploads/gij-general-cfg-commit-notification.png)

2. Connect to Git Repository ➜ **Advanced Setup** and Git Repositories (sidebar) ➜ **Edit Repository** screens.

    ![](/wp-content/uploads/gij-commit-email-notification-cfg.png)

3. Jira User Profile ➜ Git Integration for Jira preferences ➜ **Git Commit Emails**.

    ![](/wp-content/uploads/gij-user-profile-git-commit-emails.png)

&nbsp;
* * *

[**Prev:** Bulk change](/git-integration-for-jira-data-center/bulk-change-gij-self-managed)

[**Next:** Watching email notifications](/git-integration-for-jira-data-center/watching-email-notifications-gij-self-managed)

