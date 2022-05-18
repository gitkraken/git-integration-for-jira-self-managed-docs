---

title: Adding a repository hosted on Windows Servers or Windows Network Share (Admins)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Add a new network share or Windows server hosted repository via the Connect to Git Repository wizard.

The wizard will continue without errors if the following conditions are met:

*   The network credentials accessing the git repository must be the same as the user running Jira.

*   The network path is not longer than 255 characters.

*   The user under which Jira is running should have **read** access to network path.


In the Manage git repositories page, edit the repository via ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit repository settings**.

Under **Repository Settings**, set _**Enable Fetches**_ option to `Git repository hosted on the same server as Jira`.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396287/gitserver-edit-repocfg-fetches-sel2.png?version=1&modificationDate=1630642787827&cacheVersion=1&api=v2&width=442&height=81)

Considering the above conditions, verify if the repository can be cloned successfully using the network path.  With the server which hosts Jira, start the command-line session under the same user which Jira is running on.

For example:

```powershell
$ git clone file:////Ws148/Photo/repo
Cloning into ‘network-repo’...
```


If the path is invalid, does not exist or has permission issues, an error similar to the following will be displayed:

```java
fatal: '//Ws148/Photo/repo' does not appear to be a git repository
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
and the repository exists.
```


For more information, see [Setting up repositories – Adding a Repository Hosted on Windows Servers or Windows Network Share](/wiki/spaces/GIJDC/pages/1930397287/Adding+a+repository+hosted+on+Windows+Server+or+Windows+Network+share).

[« General settings: Improving Jira performance](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance)

[Setting up repository root not located in Jira Home directory (Admins) »](/wiki/spaces/GIJDC/pages/1930396317)

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