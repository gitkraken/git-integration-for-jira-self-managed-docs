---

title: Tracked Folders JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Tracked Folders JMESPath filter examples

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1349452162/Tracked+Folders+JMESPath+filter+examples>

* * *

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1349452162/tracked-folder-mobile-custom3.png?version=1&modificationDate=1615471430424&cacheVersion=1&api=v2&width=340&height=76)

An optional JMESPath filter can be configured when adding tracked folders.

|     |
| --- |
| **1\. Contains (include)** |
| ```java<br>[?contains(name, 'git')]<br>``` |
| Lists repositories with names containing `‘git’` |
| ```java<br>[?contains(name, 'git') \| contains(name, 'Slap') \| contains(name, 'est')]<br>``` |
| Lists all the repositories that contain the specified names. |

|     |
| --- |
| **2\. Contains (exclude)** |
| ```java<br>[?(!contains(name, 'firstword'))]<br>[?(!contains(name, 'firstword')) \| (!contains(name, 'secondword'))]<br>``` |
| 1 – Lists repositories with names that either do not contain the word `'firstword'`.  <br>2 – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`. |

The example below ONLY works for tracked folder integration; where it supports the ‘`fullPath`’ field:

|     |
| --- |
| **3\. Starts with (exclude)** |
| ```java<br>[?!starts_with(fullPath, '/home/user/local/store/private-repos')]<br>``` |
| Excludes repositories from the sub-folder. |

## Other examples for supported git services

*   Page:
    
    [GitHub.com | GitHub Enterprise JMESPath filter examples](/wiki/spaces/GIJDC/pages/1353482464/GitHub.com+%7C+GitHub+Enterprise+JMESPath+filter+examples) (Git Integration for Jira Data Center)
    
*   Page:
    
    [GitLab.com | GitLab CE/EE JMESPath filter examples](/wiki/spaces/GIJDC/pages/1352663492) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Microsoft | VSTS | TFS | Azure Repos JMESPath filter examples](/wiki/spaces/GIJDC/pages/1352663519/Microsoft+%7C+VSTS+%7C+TFS+%7C+Azure+Repos+JMESPath+filter+examples) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Tracked Folders JMESPath filter examples](/wiki/spaces/GIJDC/pages/1349452162/Tracked+Folders+JMESPath+filter+examples) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Gerrit JMESPath filter examples](/wiki/spaces/GIJDC/pages/1897431057/Gerrit+JMESPath+filter+examples) (Git Integration for Jira Data Center)