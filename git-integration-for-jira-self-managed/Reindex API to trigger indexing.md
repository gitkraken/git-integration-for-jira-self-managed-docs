---
 
title: Reindex API to trigger indexing
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Reindex API to trigger indexing

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing>

* * *

Call the [Reindex REST API](/wiki/spaces/GIJDC/pages/380699270) to have more control on indexing.

|     |
| --- |
| **Reindex POST API** |
| Use this method to start the reindex process in a separate thread. |
| Example:<br><br>```java<br>http://jira.yourorg.com/rest/gitplugin/1.0/index.json<br>``` |

|     |
| --- |
| **Reindex GET API** |
| Use this method to track messages for a particular thread. |
| Example:<br><br>```java<br>http://jira.yourorg.com/rest/gitplugin/1.0/index.json?threadId=eafe58fc-d8de-42ff-8815-6fe5860b38d2<br>``` |

  

[« Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317)

[Recommended reindex interval setting »](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting)

### More related topics about getting started for git admins

*   Page:
    
    [Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls) (Git Integration for Jira Data Center)
    
*   Page:
    
    [New GitLab v10+ authentication](/wiki/spaces/GIJDC/pages/1930396211) (Git Integration for Jira Data Center)
    
*   Page:
    
    [General settings: Improving Jira performance](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/wiki/spaces/GIJDC/pages/1930396287) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Recommended reindex interval setting](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Reindex API to trigger indexing](/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setting up web linking](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setting up webhooks](/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Increasing timeout threshold for large repositories while doing a Git pull](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Working with Tracked folders](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Recommended upgrade method for Git Integration for Jira](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Discard cloned files in Jira Home directory (General setting)](/wiki/spaces/GIJDC/pages/1930396547) (Git Integration for Jira Data Center)