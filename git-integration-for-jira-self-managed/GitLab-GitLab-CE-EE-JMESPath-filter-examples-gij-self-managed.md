---

title: GitLab.com | GitLab CE/EE JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1352663492/gitlab-mobile-custom1.png?version=1&modificationDate=1615471065906&cacheVersion=1&api=v2&width=170&height=53)

An optional JMESPath filter can be configured when adding GitLab integration or repositories.

|     |
| --- |
| **1\. Contains (include)** |
| ```java<br>[?contains(name, 'git') \| contains(name, 'Slap') \| contains(name, 'est')]<br>``` |
| This is a filter based on the text in the repository name. It will list repositories that contains the specified names. Do note that the declared string format is case-sensitive. |

|     |
| --- |
| **2\. Contains (exclude)** |
| ```java<br>[?(!contains(tag_list, 'largemedia'))]<br>[?(!contains(name, 'firstword'))]<br>[?(!contains(name, 'firstword')) \| (!contains(name, 'secondword'))]<br>``` |
| 1 – Blacklists project tag.  <br>2 – Lists repositories with names that either do not contain the word `'firstword'`.  <br>3 – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`. |

|     |
| --- |
| **3\. Tags** |
| ```java<br>[?contains(tag_list, 'largemedia')]<br>``` |
| Whitelists project tag.<br><br>**Note**  <br>GitLab refers to _**project tags**_ as tags in the API and in some places in the UI but the actual setting is called **Topics**. |

|     |
| --- |
| **4\. Starts with or ends with** |
| ```java<br>[?starts_with(name, 'git') \| ends_with(name, 'test')]<br>``` |
| Lists repositories with names that starts with `'git'` or ends with `'test'`. |

|     |
| --- |
| **5\. Exclude projects without repositories** |
| ```java<br>[?!empty_repo]<br>``` |
| Lists only repositories from projects that have existing repositories. |

