---

title: Gerrit JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](/wp-content/uploads/gerrit-banner-logo.png)

<br>

An optional JMESPath filter can be configured when adding GitHub integration or repositories.

<br>

## 1. Contains (include)

```java
[?contains(name, 'git')]
```

This is a filter based on the text in the repository name. It will list repositories with names that contain the word `'git'`. Do note that the declared string format is case-sensitive.

## 2. Starts with or ends with

```java
[?starts_with(name, 'git') | ends_with(name, 'test')]
```

Lists repositories with names that starts with `'git'` or ends with `'test'`.

## 3. Contains (exclude)

```java
[?(!contains(name, 'firstword'))]

[?(!contains(name, 'firstword')) | (!contains(name, 'secondword'))]
```

**1** – Lists repositories with names that either do not contain the word `'firstword'`.

**2** – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`.

The `!condition` must be wrapped in a parenthesis so it won’t invert the whole expression.

