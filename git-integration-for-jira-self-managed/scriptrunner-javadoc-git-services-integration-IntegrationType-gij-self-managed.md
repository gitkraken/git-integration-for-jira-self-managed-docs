---

title: ScriptRunner - Javadocs - Class IntegrationType
description: "IntegrationType, the ScriptRunner API enumeration of the integration types Git Integration for Jira supports."
product: Git Integration for Jira Data Center
feature: ScriptRunner
content_type: api-reference
audience: developer
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2022-08
llms_include: true
tags: [scriptrunner, javadoc, api, integrationtype, integrations, enum]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "features-gij-self-managed"
    nav_label: "Class IntegrationType"
    nav_order: 120
    nav_parent: "scriptrunner-javadoc-git-services-gijfacade-gij-self-managed"
    page_type: "content"
    card_icon: "code"
    card_color: "purple"
    card_description: "IntegrationType, the ScriptRunner API enumeration of the integration types Git Integration for Jira supports"
---

* Package [com.bigbrassband.jira.git.services.integration](#)
* [IntegrationType](#) (this page)

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

