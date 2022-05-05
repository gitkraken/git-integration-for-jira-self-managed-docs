---

title: Repository settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# Repository settings

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1207795977/Repository+settings>

* * *

This setting is part of the [**General Settings**](/wiki/spaces/GIJDC/pages/966852655/General+Settings) configuration page.

VERSION 4.0.1+ This setting is now moved to the **Advanced settings** in General settings.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207795977/gitserver-gencfg-repo-max-open-pack-files.png?version=1&modificationDate=1647774893084&cacheVersion=1&api=v2&width=680&height=97)

## Max open pack files count

Set the maximum number of open files the Git Integration for Jira app uses. For new Git Integration for Jira app install or upgrade, the default value is **16**. This is the **recommended** value.

You may set this value higher but NOT EXCEEDING the maximum number of open files allowed in the system.

  
The maximum number of open files vary for each operating system you are working with. The same units for each OS is used.

For systems that has a lot of connected repositories, increasing this value to a higher setting may improve the performance of the Git Integration for Jira app -- such as during repository browsing. This is also applicable to very busy systems that has large repository connections. Configure the maximum open files allowed by the system accordingly.

* * *

### More on advanced general settings

*   Page:
    
    [Repository settings](/wiki/spaces/GIJDC/pages/1207795977/Repository+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Repositories garbage collection checker](/wiki/spaces/GIJDC/pages/1207828777/Repositories+garbage+collection+checker) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Diff settings](/wiki/spaces/GIJDC/pages/1207795993/Diff+settings) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Discard cloned files in Jira home directory](/wiki/spaces/GIJDC/pages/1207828796/Discard+cloned+files+in+Jira+home+directory) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git operations timeout](/wiki/spaces/GIJDC/pages/1207828815/Git+operations+timeout) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Smart commits setting](/wiki/spaces/GIJDC/pages/1207828834/Smart+commits+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Cache sizes settings](/wiki/spaces/GIJDC/pages/1207828850/Cache+sizes+settings) (Git Integration for Jira Data Center)