---

title: Microsoft | VSTS | TFS | Azure Repos JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1352663519/azure2.png?version=1&modificationDate=1615471241670&cacheVersion=1&api=v2&width=340&height=57)

An optional JMESPath filter can be configured when adding Azure Repos integration or repositories.

## 1\. Contains (include)

```java
value[?contains(name, 'example')]\| {value:@}
```

This is a filter based on the text in the repository name. It will list repositories with names containing `'example'`. Do note that the declared string format is case-sensitive.

## 2\. Contains (exclude)

```java
value[?(!contains(name, 'Test'))]\| {value:@}
```

The '**!**' expression removes all repositories with `'test'` in the repository name.

## 3\. Starts with or ends with

```java
value[?starts_with(name, 'git') \| ends_with(name, 'test')]\| {value:@}
```

Lists repositories with names that starts with `'git'` or ends with `'test'`.

## Other examples

```java
value[?contains(project.state, 'wellFormed')] | {value:@}

value[?contains(project.name, 'test2')] | {value:@}

value[?contains(project.visibility, 'private')] | {value:@}

value[?contains(project.visibility, 'public')] | {value:@}
```

1.  Displays repositories from projects where its state is _completely created and ready to use_.

2.  List all repositories from project named "_**test2**_".

3.  Displays all private repositories.

4.  Displays all public repositories.

