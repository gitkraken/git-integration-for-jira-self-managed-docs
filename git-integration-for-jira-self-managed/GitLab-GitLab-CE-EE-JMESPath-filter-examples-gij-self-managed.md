---

title: GitLab.com | GitLab CE/EE JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](/wp-content/uploads/gitlab-mobile-custom1.png)

<br>

An optional JMESPath filter can be configured when adding GitLab integration or repositories.

<br>

## 1\. Contains (include)

```java
[?contains(name, 'git') | contains(name, 'Slap') | contains(name, 'est')]
```

This is a filter based on the text in the repository name. It will list repositories that contains the specified names. Do note that the declared string format is case-sensitive.

## 2\. Contains (exclude)

```java
[?(!contains(tag_list, 'largemedia'))]

[?(!contains(name, 'firstword'))]

[?(!contains(name, 'firstword')) | (!contains(name, 'secondword'))]
```

**1** – Blacklists project tag.

**2** – Lists repositories with names that either do not contain the word `'firstword'`.

**3** – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`.

## 3\. Tags

```java
[?contains(tag_list, 'largemedia')]
```

Whitelists project tag.

**Note**<br>
GitLab refers to _**project tags**_ as tags in the API and in some places in the UI but the actual setting is called **Topics**.

## 4\. Starts with or ends with

```java
[?starts_with(name, 'git') | ends_with(name, 'test')]
```

Lists repositories with names that starts with `'git'` or ends with `'test'`.

## 5\. Exclude projects without repositories

```java
[?!empty_repo]
```

Lists only repositories from projects that have existing repositories.

<br>
<hr>

_1 Logo owned by_ [_GitLab Inc_](https://gitlab.com/) _used under_ [_license_](https://creativecommons.org/licenses/by-nc-sa/4.0/)

