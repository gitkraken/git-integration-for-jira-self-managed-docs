---

title: Link git commits to Jira issues (Basics)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Link git commits to Jira issues (Basics)

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2045149189>

* * *

_Right click_ [_**here**_](https://bigbrassband.wistia.net/medias/7kj43knu4m) _to open this video in a new tab/window for more viewing options._

  
Open a Jira issue then go to the Git Commits tab.  In this tab, you will see commits, files changed, links to external repository, commit author and more.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/2045149189/gitserver-git-commits-tab-view(dec2021a).png%3Fversion=1&modificationDate=1640705375869&cacheVersion=1&api=v2?version=1&modificationDate=1640865989201&cacheVersion=1&api=v2)

In the above example, the issue key **GIT-4322** text is inserted into a git commit message to link the commit to this issue.

The git commit will get associated with the Jira issue if the commit message includes the exact issue ID. The Git Integration for Jira add-on will automatically index new commits and associate the referenced issue. For better readability, place the issue key text at the start of the commit message.

Only the commits that are **linked to Jira issues** will show on the Jira Activity Stream (not all commits in repositories).

#### Git administrator »

If you want to enforce the commit with a hook, please install this Git commit hook script - [**Commit-msg Hook »**](http://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/92177150/Commit-msg+Hook).

* * *

### More related articles on integration guides

*   Page:
    
    [Connecting to a git host account via Add new integration panel](/wiki/spaces/GIJDC/pages/2044035170/Connecting+to+a+git+host+account+via+Add+new+integration+panel) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Connecting to a single git repository (HTTPS | SSH)](/wiki/spaces/GIJDC/pages/2044035207) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setting up web links](/wiki/spaces/GIJDC/pages/2045181986/Setting+up+web+links) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Link git commits to Jira issues (Basics)](/wiki/spaces/GIJDC/pages/2045149189) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Using smart commits](/wiki/spaces/GIJDC/pages/2045149209/Using+smart+commits) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Using the Repository Browser](/wiki/spaces/GIJDC/pages/2045214758/Using+the+Repository+Browser) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Creating branches and pull | merge requests (Basics)](/wiki/spaces/GIJDC/pages/2045149234) (Git Integration for Jira Data Center)