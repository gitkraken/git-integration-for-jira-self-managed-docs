---

title: Class IntegrationType
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.services.integration](README.html)
* [IntegrationType](IntegrationType-gij-self-managed)

Integration types supported.


## Summary
#### Enum values

| Enum Values | Description | Integration properties required to connect to the git server |
| --- | --- | --- |
| GITLAB | [gitlab.com](http://gitlab.com) | type, PAT |
| GITLAB_SERVER | GitLab CE/EE (APIv4) | type, origin, PAT |
| GITLAB_SERVER_LEGACY | GitLab CE/EE Legacy (APIv3) | type, origin, username, password |
| FILESPACE | Tracked folder | type, origin, folderDepth |
| GITHUB | [githab.com](http://githab.com) and GitHub Enterprise Cloud | (type, username, password) or (type, PAT) |
| GITHUB_SERVER | GitHub Enterprise Server | type, origin, PAT |
| TFS_SERVER | Team Foundation Server (TFS) | (type, origin, username, password) or (type, origin, username="all", PAT) |
| AZURE_DEVOPS | Azure DevOps Repos | (type, origin, username, password) or (type, origin, PAT)|
| VSTS | [Visual Studio Team Services (VSTS)](https://visualstudio.com) | type, PAT |
| AZURE | [Azure DevOps Repos](https://dev.azure.com) | type, PAT |
| AWS | AWS CodeCommit | type, username, password, awsRegion |
| GERRIT | Gerrit | type, origin, username, password |
