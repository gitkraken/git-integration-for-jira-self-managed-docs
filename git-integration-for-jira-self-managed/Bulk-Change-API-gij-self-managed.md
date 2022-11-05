---

title: Bulk Change API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The bulk change API extends the possibility of importing and exporting repository configuration by automating the process via scripts.

To use the API, users must:

*   install the <a href='http://docs.python-requests.org/en/latest/user/install/#install' target='_blank'><b>Requests »</b></a> Python package.

*   declare `JIRA_BASE`, `JIRA_USER`, and `JIRA_PASSWORD` in the `configuration_conf.py` file.  The `JIRA_USER` defined in this file must have Jira Admin global permissions.  _(Download_ <a href='https://bigbrassband.com/files/configuration_conf.zip'>sample file ↓</b></a> _as a zip file.)_


HTTP Status code response:

*   **200**  –  success

*   **401**  –  user is unauthorized

*   **403**  –  lack of privileges _(The user doesn't have Jira Admin global permission)_

<br>
<br>

## Bulk Change REST APIs

*   [Bulk Export](/git-integration-for-jira-data-center/bulk-export-gij-self-managed/) (Git Integration for Jira Server/Data Center)

*   [Bulk Import](/git-integration-for-jira-data-center/bulk-import-gij-self-managed/) (Git Integration for Jira Server/Data Center)

*   [Get Bulk Import Information](/git-integration-for-jira-data-center/get-bulk-import-information-gij-self-managed/) 
(Git Integration for Jira Server/Data Center)
