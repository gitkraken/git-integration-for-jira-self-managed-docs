---

title: Gerrit JMESPath filter examples
description: Use example JMESPath expressions to include or exclude Gerrit repositories by name when adding a Gerrit integration.
product: Git Integration for Jira Data Center
feature: JMESPath Filters
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [gerrit]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-09
llms_include: true
tags: [jmespath, gerrit, repository filters, contains, starts with]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "how-to-articles-gij-self-managed"
    nav_label: "Gerrit JMESPath filter examples"
    nav_order: 60
    nav_parent: "working-with-jmespath-filters-gij-self-managed"
    page_type: "content"
---

![](/wp-content/uploads/gerrit-banner-logo.png)

&nbsp;

An optional JMESPath filter can be configured when adding Gerrit integrations.

&nbsp;

### 1\. Contains (include)

`[?contains(name, 'git')]`

This is a filter based on the text in the repository name. It lists repositories with the names that contain the word `'git'`. Do note that the declared string format is case-sensitive.

### 2\. Starts with or ends with

`[?starts_with(name, 'git') || ends_with(name, 'test')]`

Lists repositories with the names that start with `'git'` or end with `'test'`.

### 3\. Contains (exclude)

`[?(!contains(name, 'firstword'))]`

`[?(!contains(name, 'firstword')) && (!contains(name, 'secondword'))]`

**1** – Lists repositories with the names that do not contain the word `'firstword'`.

**2** – Lists repositories with the names that either do not contain the words `'firstword'` OR `'secondword'`.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <code>!condition</code> must be wrapped in a parenthesis so it won’t invert the whole expression.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Do note that the declared string format is case-sensitive.
    </div>
    </div>
</div>

&nbsp;
* * *
&nbsp;

### More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

**Gerrit JMESPath filter examples** (this page)

