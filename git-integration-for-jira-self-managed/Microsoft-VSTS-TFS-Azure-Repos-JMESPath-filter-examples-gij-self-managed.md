---

title: Microsoft | VSTS | TFS | Azure Repos JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/azure2-logo.png)

<br>

An optional JMESPath filter can be configured when adding Azure Repos integrations.

<br>

## 1\. Contains (include)

`value[?contains(name, 'example')] | {value:@}`

This is a filter based on the text in the repository name. It lists repositories with the names that contain the word `'example'`. Do note that the declared string format is case-sensitive.

## 2\. Contains (exclude)

`value[?(!contains(name, 'test'))] | {value:@}`

Lists repositories with the names that do not contain the word `'test'`.

<br>

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
<br>

## 3\. Starts with or ends with

`value[?starts_with(name, 'git') || ends_with(name, 'test')] | {value:@}`

Lists repositories with the names that start with `'git'` or end with `'test'`.

## Other examples

`value[?contains(project.state, 'wellFormed')] | {value:@}`

`value[?contains(project.name, 'test2')] | {value:@}`

`value[?contains(project.visibility, 'private')] | {value:@}`

`value[?contains(project.visibility, 'public')] | {value:@}`

1.  Lists repositories from projects where their state is _completely created and ready to use_.

2.  Lists all repositories from the project named "_**test2**_".

3.  Lists all private repositories.

4.  Lists all public repositories.

<P>&nbsp;</p>

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
<br>

<hr>

## More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

**Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples** (this page)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

