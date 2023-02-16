---

title: Microsoft | VSTS | TFS | Azure Repos JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/azure2-logo.png)

<br>

An optional JMESPath filter can be configured when adding Azure Repos integration or repositories.

<br>

## 1\. Contains (include)

`value[?contains(name, 'example')] | {value:@}`

This is a filter based on the text in the repository name. It will list repositories with names containing `'example'`. Do note that the declared string format is case-sensitive.

## 2\. Contains (exclude)

`value[?(!contains(name, 'Test'))] | {value:@}`

The '**!**' expression removes all repositories with `'test'` in the repository name.

## 3\. Starts with or ends with

`value[?starts_with(name, 'git') || ends_with(name, 'test')] | {value:@}`

Lists repositories with names that starts with `'git'` or ends with `'test'`.

## Other examples

```
value[?contains(project.state, 'wellFormed')] | {value:@}

value[?contains(project.name, 'test2')] | {value:@}

value[?contains(project.visibility, 'private')] | {value:@}

value[?contains(project.visibility, 'public')] | {value:@}
```

1.  Displays repositories from projects where its state is _completely created and ready to use_.

2.  List all repositories from project named "_**test2**_".

3.  Displays all private repositories.

4.  Displays all public repositories.

<hr>

## More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

**Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples** (this page)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

