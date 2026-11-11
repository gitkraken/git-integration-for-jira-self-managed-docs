---

title: GitHub.com | GitHub Enterprise JMESPath filter examples
description: Use example JMESPath expressions to include or exclude GitHub.com and GitHub Enterprise repositories by name when adding an integration.
product: Git Integration for Jira Data Center
feature: JMESPath Filters
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [github, github-enterprise]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [jmespath, github, github enterprise, repository filters]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "how-to-articles-gij-self-managed"
    nav_label: "GitHub.com | GitHub Enterprise JMESPath filter examples"
    nav_order: 10
    nav_parent: "working-with-jmespath-filters-gij-self-managed"
    page_type: "content"
    card_icon: "brand-github"
    card_color: "amber"
    card_description: "Use example JMESPath expressions to include or exclude GitHub.com and GitHub Enterprise repositories by name when adding an integration"
---

![](/wp-content/uploads/gij-github-mobile-logo-dark.png)

&nbsp;

An optional JMESPath filter can be configured when adding GitHub integrations.

&nbsp;

### 1\. Contains (include)

`[?contains(name, 'git')]`

This is a filter based on the text in the repository name. It lists repositories with the names that contain the word `'git'`. Do note that the declared string format is case-sensitive.

&nbsp;

### 2\. Starts with or ends with

`[?starts_with(name, 'git') || ends_with(name, 'test')]`

Lists repositories with the names that start with `'git'` or end with `'test'`.

&nbsp;

### 3\. Contains (exclude)

`[?(!contains(name, 'firstword'))]`

`[?(!contains(name, 'firstword')) && (!contains(name, 'secondword'))]`

**1** – Lists repositories with the names that do not contain the word `'firstword'`.

**2** – Lists repositories with the names that either do not contain the words `'firstword'` OR `'secondword'`.

&nbsp;

> **Note:** The <code>!condition</code> must be wrapped in a parenthesis so it won’t invert the whole expression.

> **Info:** Do note that the declared string format is case-sensitive.

&nbsp;
<hr>
&nbsp;

## More articles on JMESPath filter examples

**GitHub.com \| GitHub Enterprise JMESPath filter examples** (this page)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

