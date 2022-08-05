---

title: ScriptRunner - Javadocs
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

# Class IntegrationType

* Package [com.bigbrassband.jira.git.services.integration](#)
* [IntegrationType](#)

Integration types supported.


## Summary
#### Enum values

| Enum Values | Description | Integration properties required to connect to the git server |
| --- | --- | --- |
| GITLAB | [Gitlab.com](http://gitlab.com) | type, PAT |
| GITLAB_SERVER | GitLab CE/EE (APIv4) | type, origin, PAT |
| GITLAB_SERVER_LEGACY | GitLab CE/EE Legacy (APIv3) | type, origin, username, password |
| FILESPACE | Tracked folder | type, origin, folderDepth |
| GITHUB | [Github.com](http://github.com) and GitHub Enterprise Cloud | (type, username, password) or (type, PAT) |
| GITHUB_SERVER | GitHub Enterprise Server | type, origin, PAT |
| TFS_SERVER | Team Foundation Server (TFS) | (type, origin, username, password) or (type, origin, username="all", PAT) |
| AZURE_DEVOPS | Azure DevOps Repos | (type, origin, username, password) or (type, origin, PAT)|
| VSTS | [Visual Studio Team Services (VSTS)](https://visualstudio.com) | type, PAT |
| AZURE | [Azure DevOps Repos](https://dev.azure.com) | type, PAT |
| AWS | AWS CodeCommit | type, username, password, awsRegion |
| GERRIT | Gerrit | type, origin, username, password |

