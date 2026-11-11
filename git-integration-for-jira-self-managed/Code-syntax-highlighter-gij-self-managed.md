---

title: Jira issue page - Code syntax highlighter
description: See which file extensions get syntax highlighting in the code diff dialog and which browsers are supported for the feature.
product: Git Integration for Jira Data Center
feature: Code Diff Viewing
content_type: reference
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [syntax highlighting, code diff, file extensions, languages, supported browsers]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Jira issue page – Code syntax highlighter"
    nav_order: 30
    nav_parent: "jira-issue-page-gij-self-managed"
    page_type: "content"
---

The code diff dialog view has been improved. The Git Integration for Jira app uses the correct syntax highlighting when viewing the code diff of the file based on its file extension:

| File Extension | Language ID |
| :--- | :--- |
| **css** | CSS |
| **js** | Javascript |
| **cpp** | C++ |
| **cs** | C#  |
| **sh** | Bash |
| **java** | Java |
| **sql** | SQL |
| **py** | Phyton |
| **rb** | Ruby |
| **php, phtml, php3, php4, php5** | PHP |
| **html, html, xhtml, xml** | Markup |
| **c, h, m, mm, pl, pm** | CLike |

> **Info:** There is no language auto-detection in the diff dialog. The detection is based on file extension.

<br>

> **Warning:** This feature will only display properly on browsers supported by Atlassian for specific versions of Jira:
> <ul style='margin-bottom:0px'>
> <li><a href="https://confluence.atlassian.com/adminjiraserver0900/supported-platforms-1142254604.html" target="_blank">Jira 9.x supported platforms</a></li>
> <li><a href="https://confluence.atlassian.com/adminjiraserver080/supported-platforms-967896891.html" target="_blank">Jira 8.x supported platforms</a></li>
> </ul>

&nbsp;
* * *

[**Prev:** Git Commits tab](/git-integration-for-jira-data-center/git-commits-tab-gij-self-managed)

[**Next:** Jira Git integration development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed)


