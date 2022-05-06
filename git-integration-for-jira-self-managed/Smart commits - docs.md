---

title: Smart commits - Documentation
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Smart commits - Documentation

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398395/Smart+commits>

* * *

Smart commits allows your team to perform actions on Jira issues from a single commit. Users can enter the issue key and the desired action such as time tracking or closing an issue.

## Getting started

VERSION 2.6.3+ The smart commit processing is **active by default** and can be enabled/disabled via the git configuration page (![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions ➜ Edit integration/repository settings**):

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398395/smart-commit-setting.png?version=1&modificationDate=1630642887746&cacheVersion=1&api=v2&width=374&height=80)

_In Jira Server, Smart Commits is a setting toggle in the **Connect wizard** or the git_  
_configuration page under **Actions** ➜ **Edit integration/repository settings**._  
_In Jira Cloud, this setting is always enabled._

VERSION 2.13.0+ Smart commits support for project keys that has an underscore "\_" character.  
VERSION 3.2.0+ Smart commits support for all alphabet characters.  
VERSION 3.5.0.2+ Smart commits support for case insensitive smart commits.

  
Smart commits configuration checklist:

*   **The Jira DVCS Connector Plugin is not required.**  
    The Git Integration for Jira app has the functions of the connector plugin plus more integration support and features.
    
*   **Your Jira e-mail address and Git commit e-mail address matches.**  
    The commit author's email should match exactly with a user's email in Jira. If they do not match, the application will add the commit as the app.
    
*   **E-mail address is not shared by other Jira users.**  
    Verify that this email address is used by only one Jira user.
    
*   **Advanced:** Verify that the workflow conditions and validators are able to process successfully.
    

  
The Git Integration app supports smart commit by adding a simple syntax to a commit message.

The basic syntax for a Smart commit message is:

```java
<ISSUE_KEY> <ignored text> #<command> <optional command_params>
```

To know more about syntax, commands and examples on Smart Commits, see [**Processing Jira Software Issues with Smart Commit Messages**](https://confluence.atlassian.com/bitbucket/processing-jira-software-issues-with-smart-commit-messages-298979931.html) at the Atlassian website or proceed to the next page.

[« Linking git commits to Jira issues](/wiki/spaces/GIJDC/pages/1930398265/Linking+git+commits+to+Jira+issues)

[Smart commit: Basic commands »](/wiki/spaces/GIJDC/pages/1930398422/Basic+commands)

### More related topics about smart commits

*   Page:
    
    [Smart commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Basic commands](/wiki/spaces/GIJDC/pages/1930398422/Basic+commands) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Workflow transitions](/wiki/spaces/GIJDC/pages/1930398464/Workflow+transitions) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Advanced examples](/wiki/spaces/GIJDC/pages/1930398446/Advanced+examples) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Viewing workflows](/wiki/spaces/GIJDC/pages/1930398494/Viewing+workflows) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Smart commits helper](/wiki/spaces/GIJDC/pages/1930398529/Smart+commits+helper) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Smart commits General setting](/wiki/spaces/GIJDC/pages/1930398554/Smart+commits+General+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Scripting (Jira git workflow hooks)](/wiki/spaces/GIJDC/pages/1930398579) (Git Integration for Jira Data Center)