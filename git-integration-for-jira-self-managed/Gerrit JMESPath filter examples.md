---

title: Gerrit JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1897431057/gerrit-banner-logo.png?version=1&modificationDate=1628757509971&cacheVersion=1&api=v2&width=226&height=93)

An optional JMESPath filter can be configured when adding GitHub integration or repositories.

|     |
| --- |
| ### 1\. Contains (include) |
| ```java<br>[?contains(name, 'git')]<br>``` |
| This is a filter based on the text in the repository name. It will list repositories with names that contain the word `'git'`. Do note that the declared string format is case-sensitive. |

|     |
| --- |
| ### 2\. Starts with or ends with |
| ```java<br>[?starts_with(name, 'git') \| ends_with(name, 'test')]<br>``` |
| Lists repositories with names that starts with `'git'` or ends with `'test'`. |

|     |
| --- |
| ### 3\. Contains (exclude) |
| ```java<br>[?(!contains(name, 'firstword'))]<br>[?(!contains(name, 'firstword')) \| (!contains(name, 'secondword'))]<br>``` |
| 1 – Lists repositories with names that either do not contain the word `'firstword'`.  <br>2 – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`. |
| The `!condition` must be wrapped in a parenthesis so it won’t invert the whole expression. |

