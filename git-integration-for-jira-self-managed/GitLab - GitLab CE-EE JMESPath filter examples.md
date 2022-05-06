---

title: GitLab.com | GitLab CE/EE JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# GitLab.com | GitLab CE/EE JMESPath filter examples

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1352663492>

* * *

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
    

1 _Logo owned by_ [_GitLab Inc_](https://gitlab.com/) _used under_ [_license_](https://creativecommons.org/licenses/by-nc-sa/4.0/)