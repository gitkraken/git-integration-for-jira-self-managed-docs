---

title: Tracked Folders JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/tracked-folder-mobile-custom3.png)

An optional JMESPath filter can be configured when adding tracked folders.

## 1\. Contains (include)

```
[?contains(name, 'git')]
```

Lists repositories with names containing `‘git’`

<br>

```
[?contains(name, 'git') || contains(name, 'Slap') || contains(name, 'est')]
```

Lists all the repositories that contain the specified names.

## 2\. Contains (exclude)

```
[?(!contains(name, 'firstword'))]

[?(!contains(name, 'firstword')) || (!contains(name, 'secondword'))]
```

**1** – Lists repositories with names that either do not contain the word `'firstword'`.

**2** – Lists repositories with names that either do not contain the words `'firstword'` OR `'secondword'`.

## 3\. Starts with (exclude)

The example below ONLY works for tracked folder integration; where it supports the `'fullPath'` field:

```
[?!starts_with(fullPath, '/home/user/local/store/private-repos')]
```

Excludes repositories from the sub-folder.

<hr>

## More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

[GitLab.com \| GitLab CE/EE JMESPath filter examples](/git-integration-for-jira-data-center/GitLab-GitLab-CE-EE-JMESPath-filter-examples-gij-self-managed)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

**Tracked Folders JMESPath filter examples** (this page)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

