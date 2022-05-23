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

