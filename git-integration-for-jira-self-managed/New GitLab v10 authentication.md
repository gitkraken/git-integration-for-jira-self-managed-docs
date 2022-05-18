---

title: New GitLab v10+ authentication
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
GitLab v10+ stopped accepting username/password credentials for API access and will only recognize Personal Access Tokens (PAT) and OAuth authentications. Service users are strongly advised to switch from using username/password for GitLab.com and newer versions of GitLab Server (CE/EE) to using Personal Access Tokens.

For GitLab Server service users, they won't see the issue until they upgrade their GitLab Servers to version 10 and higher. Git Integration for Jira app offers pre-v10 GitLab Server users as a Legacy connection option.

To access a Git repository over HTTP, use the username as the _username_ and the PAT for the _password_.

To pass the private access token (for example: `XpigzF1JxMnAZ7mn9qgN`) to an API call with GitLab.com:

```java
curl --header "Private-Token: XpigzF1JxMnAZ7mn9qgN" https://gitlab.com/api/v4/projects?membership=true
```


For more information on GitLab personal access token, see [**GitLab: Personal Access Token**](https://docs.gitlab.com/ce/user/profile/personal_access_tokens.html).

[« Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls)

[General settings: Improving Jira performance »](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance)

### More related topics about getting started for Jira admins

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