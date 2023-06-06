---

title: Tracked Folders JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/tracked-folder-mobile-custom3.png)

&nbsp;

An optional JMESPath filter can be configured when adding tracked folders.

&nbsp;

### 1\. Contains (include)

`[?contains(name, 'git')]`

This is a filter based on the text in the repository name. It lists repositories with the names that contain the word `'git'`. Do note that the declared string format is case-sensitive.

&nbsp;

`[?contains(name, 'git') || contains(name, 'Slap') || contains(name, 'est')]`

Lists repositories with the names that contain any of the specified word.

### 2\. Contains (exclude)

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

&nbsp;

### 3\. Starts with (exclude)

The example below ONLY works for tracked folder integrations; where it supports the `'fullPath'` field:

`[?!starts_with(fullPath, '/home/user/local/store/private-repos')]`

Excludes repositories from the sub-folder.

&nbsp;

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

## More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

**Tracked Folders JMESPath filter examples** (this page)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

