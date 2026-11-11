---

title: GitLab.com | GitLab CE/EE JMESPath filter examples
description: "Use example JMESPath expressions to filter GitLab.com and GitLab CE/EE projects by name, topic tags or empty repositories."
product: Git Integration for Jira Data Center
feature: JMESPath Filters
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [gitlab, gitlab-self-managed]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-09
llms_include: true
tags: [jmespath, gitlab, repository filters, project tags, topics]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "how-to-articles-gij-self-managed"
    nav_label: "GitLab.com | GitLab CE/EE JMESPath filter examples"
    nav_order: 30
    nav_parent: "working-with-jmespath-filters-gij-self-managed"
    page_type: "content"
    card_icon: "brand-gitlab"
    card_color: "amber"
    card_description: "Use example JMESPath expressions to filter GitLab.com and GitLab CE/EE projects by name, topic tags or empty repositories"
---

![](/wp-content/uploads/gitlab-mobile-custom1.png)

&nbsp;

An optional JMESPath filter can be configured when adding GitLab integrations.

&nbsp;

### 1\. Contains (include)

`[?contains(name, 'git') || contains(name, 'Slap') || contains(name, 'est')]`

This is a filter based on the text in the repository name. It lists repositories with the names that contain any of the specified word. Do note that the declared string format is case-sensitive.

&nbsp;

### 2\. Contains (exclude)

`[?(!contains(tag_list, 'largemedia'))]`

`[?(!contains(name, 'firstword'))]`

`[?(!contains(name, 'firstword')) && (!contains(name, 'secondword'))]`

**1** – Blacklists a project tag.

**2** – Lists repositories with the names that do not contain the word `'firstword'`.

**3** – Lists repositories with the names that either do not contain the words `'firstword'` OR `'secondword'`.

> **Note:** The <code>!condition</code> must be wrapped in a parenthesis so it won’t invert the whole expression.

&nbsp;

### 3\. Tags

`[?contains(tag_list, 'largemedia')]`

Whitelists a project tag.

> **Note:** GitLab refers to <b><i>project tags</i></b> as tags in the API and in some places in the UI but the actual setting is called <b>Topics</b>.

&nbsp;


### 4\. Starts with or ends with

`[?starts_with(name, 'git') || ends_with(name, 'test')]`

Lists repositories with the names that start with `'git'` or end with `'test'`.

&nbsp;

### 5\. Exclude projects without repositories

`[?!empty_repo]`

Lists only repositories from projects that have existing repositories.

> **Info:** Do note that the declared string format is case-sensitive.

&nbsp;
* * *

### More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

**GitLab.com \| GitLab CE/EE JMESPath filter examples** (this page)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

<!-- FOOTNOTE -->
<br>
<br>
<div style='border-top: 1px solid #456; width: 40%; padding-bottom: 12px'></div>
<div style='font-size: 12px;'>
    <sup>1</sup> <i>Logo owned by <a href='https://gitlab.com/' target='_blank'>GitLab Inc</a> used under <a href='https://creativecommons.org/licenses/by-nc-sa/4.0/' target='_blank'>license</a>.
    <p>&nbsp;&nbsp;All product names, logos, and brands are property of their respective owners.</p></i>
</div>

