---

title: GitHub.com | GitHub Enterprise JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

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
<hr>
&nbsp;

## More articles on JMESPath filter examples

**GitHub.com \| GitHub Enterprise JMESPath filter examples** (this page)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

