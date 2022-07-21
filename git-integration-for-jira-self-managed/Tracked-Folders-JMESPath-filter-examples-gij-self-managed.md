---

title: Tracked Folders JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](/wp-content/uploads/tracked-folder-mobile-custom3.png)

An optional JMESPath filter can be configured when adding tracked folders.

## 1\. Contains (include)

```java
[?contains(name, 'git')]
```

Lists repositories with names containing `‘git’`

<br>

```java
[?contains(name, 'git') | contains(name, 'Slap') | contains(name, 'est')]
```

Lists all the repositories that contain the specified names. |

## 2\. Contains (exclude)

```java
[?(!contains(name, 'firstword'))]

[?(!contains(name, 'firstword')) | (!contains(name, 'secondword'))]
```

**1** – Lists repositories with names that either do not contain the word `'firstword'`.

**2** – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`.

## 3\. Starts with (exclude)

The example below ONLY works for tracked folder integration; where it supports the ‘`fullPath`’ field:

```java
[?!starts_with(fullPath, '/home/user/local/store/private-repos')]
```

Excludes repositories from the sub-folder.

