---

title: Discard cloned files in Jira Home directory (General setting)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Discard cloned files in Jira Home directory (General setting)

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930396547>

* * *

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396547/gitserver-discard-cloned-files-gencfg.png?version=1&modificationDate=1630642798827&cacheVersion=1&api=v2)

This feature will reduce Jira server storage by deleting files from cloned git repositories after indexing.  Discarding files can save disk space but may limit some features such as displaying diffs of files.

Access this feature via Jira dashboard menu Git ➜ Manage repositories ➜ **General settings** (sidebar). Alternatively, go to Jira dashboard menu – ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ Applications ➜ **General settings** (sidebar).

There are three options to choose from:

*   **Keep all cloned binary files. No storage savings. All features available.** This option will leave all cloned repositories intact.
    
*   **Discard all files that match the mask below. Some features limited.** This option will delete all files in the cloned repositories matching the declared file extensions.
    
*   **Discard all files EXCEPT those that match the mask below. Some features limited.** This option will delete all other files in the cloned repositories except those files with extensions declared.
    

Select any option with the _discard_ label to enable editing of the file mask field.  

For full list of features, version history and supported Jira version of the Git for Jira app, see [**Git Integration for Jira app Version History**](https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions).

Whenever the setting is changed, BigBrassBand recommends to perform a manual re-clone of the repositories to ensure an error-free operation.

[« Recommended upgrade method for Git Integration for Jira app](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira)

[Working with SSH keys »](/wiki/spaces/GIJDC/pages/1930396577/Working+with+SSH+keys)

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