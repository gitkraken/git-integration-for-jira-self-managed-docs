---

title: Edit integration feature settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Edit integration feature settings

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397576/Edit+integration+feature+settings>

* * *

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitcfg-actions-edit-feature-conn-cfg.png?version=1&modificationDate=1630642846599&cacheVersion=1&api=v2&width=680&height=213)

Clicking ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit integration feature settings** opens the configuration page for integration features settings.

Utilize the following options to configure the selected integration:

|     |
| --- |
| ### Repository Browser |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-repocfg-repovw.png?version=1&modificationDate=1630642846839&cacheVersion=1&api=v2&width=680&height=65) |
| When `Enabled`, it allows users to view Git repositories of configured projects. For more information, see [Repository Browser](/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser). |

|     |
| --- |
| ### Tags |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-tags.png?version=1&modificationDate=1630642847074&cacheVersion=1&api=v2&width=680&height=150) |
| Set whether to show all tags or show on tags with matching regex pattern. For more information on git tags, see [Git Tags](/wiki/spaces/GIJDC/pages/1930399204/Git+tags). |

|     |
| --- |
| ### Personal Access Token: Require User PAT |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-pat-reqpat.png?version=1&modificationDate=1630642847309&cacheVersion=1&api=v2&width=680&height=61) |
| Enable this option to require users to provide PAT which will be used for branch and merge/pull request creation/deletion (via the developer panel on the Jira issue page). This is a security feature of Git Integration for Jira app for git hosts that support two-factor authentication.<br><br>This option requires the [Repository Browser](/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser) feature enabled.<br><br>This setting is only available for auto-connected git hosts in Jira Server and Data Center. |

|     |
| --- |
| ### Project Permissions |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-feature-cfg-proj-acls.png?version=1&modificationDate=1639568670798&cacheVersion=1&api=v2&width=680&height=155) |
| The default setting is **Associate with all projects**. You can restrict access to the Repository Browser and Git Commits tabs for the selected repository by setting the project associations.<br><br>To restrict to specific projects, uncheck the **Associate with all projects** _option_ and set/select one or more projects from the list. |

|     |
| --- |
| ### Source Code Diff Viewing |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-src-code-diffvw.png?version=1&modificationDate=1630642847773&cacheVersion=1&api=v2&width=680&height=64) |
| Allows or denies users to view the diff by commit and file. |

|     |
| --- |
| ### Smart Commits |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-smartcommits.png?version=1&modificationDate=1630642848019&cacheVersion=1&api=v2&width=680&height=82) |
| Allows or denies the users to use the smart commits feature. |

|     |
| --- |
| ### Commit Notification Emails |
| ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397576/gitserver-edit-features-commit-notif-emails.png?version=1&modificationDate=1630642848253&cacheVersion=1&api=v2&width=680&height=116) |
| Enable/disable this setting to allow/deny sending of commit notification emails.<br><br>Set the **Max commit age (in minutes)** as to when commit notifications will be sent. Commit notifications will be e-mailed if the age of the commit is less than or equal to this value. |

[« Edit integration connection settings](/wiki/spaces/GIJDC/pages/1930397536/Edit+integration+connection+settings)

[SSL verify »](/wiki/spaces/GIJDC/pages/1930397639/SSL+verify)

### More related topics about managing repository/integration configuration

*   Page:
    
    [Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Managing integration via Actions](/wiki/spaces/GIJDC/pages/1930397476/Managing+integration+via+Actions) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Show tracked or integration repositories](/wiki/spaces/GIJDC/pages/1930397507/Show+tracked+or+integration+repositories) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Edit integration connection settings](/wiki/spaces/GIJDC/pages/1930397536/Edit+integration+connection+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Edit integration feature settings](/wiki/spaces/GIJDC/pages/1930397576/Edit+integration+feature+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [SSL verify](/wiki/spaces/GIJDC/pages/1930397639/SSL+verify) (Git Integration for Jira Data Center)
    
*   Page:
    
    [View integration or repository properties](/wiki/spaces/GIJDC/pages/1930397673/View+integration+or+repository+properties) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Viewing indexing logs](/wiki/spaces/GIJDC/pages/1930397702/Viewing+indexing+logs) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Removing integration or repository configuration](/wiki/spaces/GIJDC/pages/1930397738/Removing+integration+or+repository+configuration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Edit repository settings](/wiki/spaces/GIJDC/pages/1947107348/Edit+repository+settings) (Git Integration for Jira Data Center)