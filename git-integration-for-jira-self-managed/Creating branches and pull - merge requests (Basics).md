---

title: Creating branches and pull | merge requests (Basics)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Git Integration for Jira app adds two features on the Jira issue developer panel – **Create Branch**, and **Create Pull/Merge Request**. For more information about the developer panel, see the [Jira Git Integration Developer Panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel) documentation.

## Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex. Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level. For the case with Gerrit, the default main branch is always “master”.

Main branch for repositories within an integration can only be changed on the git server.

## Creating branches

Open a Jira issue then on the developer panel, click **Create Branch** label to create a branch for the selected repository.

For detailed information on this feature, see [Creating branches from Jira](/git-integration-for-jira-self-managed/Creating-branches).

## Creating pull/merge requests

Open a Jira issue then on the developer panel, click **Create pull/merge request** label to create a pull/merge request for the selected repository.

For detailed information on this feature, see [Creating pull/merge requests from Jira](/wiki/spaces/GIJDC/pages/1932460359).

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