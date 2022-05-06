---

title: Setting up webhooks
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Setting up webhooks

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks>

* * *

Before you can use webhooks, it needs to be enabled in the Git Integration for Jira webhook settings.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396415/jira-server-git-webhooks-new(c).png?version=1&modificationDate=1630642793039&cacheVersion=1&api=v2)

Access the Git Integration for Jira app webhook configuration page:

1.  Go to Jira dashboard menu Git ➜ **Manage repositories**.
    
2.  On the sidebar under _Git Integration for Jira_, click **Webhooks**.
    
3.  Enable the webhook feature by setting it to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Enabled**.
    

On this page, you can also find the **Webhook URL** and the **Secret key** for use with your git host webhook configuration.

## Secret key

The secret key is a secure random-generated alphanumeric string at the time of the Git Integration for Jira app installation.

Disabling, reinstalling or even installing another version of the Git Integration for Jira app does not change the value of the key (for security purposes and unique identity). Administrators can manually change this key to a different value by generating another secret token according to your Git host and organization policies. For instance:

```java
ruby -rsecurerandom -e 'puts SecureRandom.hex(32)'
```

The secret key also has the same restrictions on the valid set of characters as a regular URL. Invalid characters such as spaces, slashes, colon, etc. are not allowed. The default recommended length for the secret key is 32 chars and the maximum length is 255 chars.

## More information on webhooks configuration

For detailed information on setting up webhooks for supported git hosts, see [Git Integration for Jira: Integration webhooks](/wiki/spaces/GIJDC/pages/1930399378/Integration+webhooks).  

The Git Integration for Jira app supports GitHub and GitLab push events to define individual repository to index. For more information, see [Creating reindex triggers manually](/wiki/spaces/GIJDC/pages/171475191).

[« Setting up web linking](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking)

[Increasing timeout threshold for large repositories while doing a Git pull »](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull)

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