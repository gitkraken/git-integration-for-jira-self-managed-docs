---

title: Bulk Change API
description: Automate import and export of repository configuration with the Bulk Change REST API using Python scripts and Jira admin credentials.
product: Git Integration for Jira Data Center
feature: REST API
content_type: overview
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-12
llms_include: true
tags: [rest api, bulk change, bulk export, bulk import, python scripts]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Bulk Change API"
    nav_order: 10
    nav_parent: "rest-api-gij-self-managed"
    page_type: "content"
---

The bulk change API extends the possibility of importing and exporting repository configuration by automating the process via scripts.

To use the API, users must:

*   install the <a href='http://docs.python-requests.org/en/latest/user/install/#install' target='_blank'><b>Requests »</b></a> Python package.

*   declare `JIRA_BASE`, `JIRA_USER`, and `JIRA_PASSWORD` in the `configuration_conf.py` file.  The `JIRA_USER` defined in this file must have Jira Admin global permissions.  _(Download by right-clicking the file then save_ <a href='/wp-content/uploads/configuration_conf.zip'>sample file ↓</b></a> _as a zip file.)_


HTTP Status code response:

*   **200**  –  success

*   **401**  –  user is unauthorized

*   **403**  –  lack of privileges _(The user doesn't have Jira Admin global permission)_

&nbsp;

## Bulk Change REST APIs

*   [Bulk Export](/git-integration-for-jira-data-center/bulk-export-gij-self-managed/) (Git Integration for Jira Data Center)

*   [Bulk Import](/git-integration-for-jira-data-center/bulk-import-gij-self-managed/) (Git Integration for Jira Data Center)

*   [Get Bulk Import Information](/git-integration-for-jira-data-center/get-bulk-import-information-gij-self-managed/) 
(Git Integration for Jira Data Center)

