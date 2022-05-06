---

title: Adding webhooks for Gerrit
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Adding webhooks for Gerrit

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1509032414/Adding+webhooks+for+Gerrit>

* * *

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1509032414/gerrit-webhook-banner.png?version=1&modificationDate=1618656373661&cacheVersion=1&api=v2&width=510&height=117)

  
**What’s on this page:**

* * *

## Introduction

Webhooks are not configured by default in Gerrit. They are not built into Gerrit just like they are in GitHub, GitLab and etc. Thus, when calling Gerrit webhooks, these won't trigger the reindex of the integration / repositories.

## Installation

To use webhooks with Gerrit, it needs to be configured.

For starters, install Gerrit with the webhook plugin by reading at [https://gerrit.googlesource.com/plugins/webhooks/](https://gerrit.googlesource.com/plugins/webhooks/) and the steps below.

|     |
| --- |
| **Project (repository) list** |
| ```perl<br>curl http(s)://your.org.com:8080/projects/?d<br>``` |

|     |
| --- |
| **Enable webhooks for the repository, for example, MyTestRepo** |
| ```perl<br>curl http(s)://your.org.com:8080/config/server/webhooks~projects/MyTestRepo/remotes<br>``` |

|     |
| --- |
| **Add webhook for the repository** |
| ```perl<br>curl --user username:password -H 'Content-Type: application/json' -X PUT -d @webhook.json http(s)://your.org.com:8080/a/config/server/webhooks~projects/MyTestRepo/remotes/bbb-webhook<br>```<br><br>Where `webhook.json`:  <br>{  <br>"url" : "[https://example.com/webhook/url",](https://example.com/webhook/url%22)  <br>"maxTries" : 3,  <br>"sslVerify": true  <br>} |

## Manually trigger webhooks

Create a webhook that can be triggered for any **individual** repository. It can be used with continuous integration service.

_**Required headers:**_

*   'x-bbb-webhook-type': `PUSH`
    
*   'Content-Type': `application/json`
    

_**Optional headers:**_

*   'x-bbb-webhook-id' -- Can be any string representing the id of the request to be used.
    

|     |
| --- |
| **Usage examples:** |
| ```perl<br>curl -H 'x-bbb-webhook-type: push' -H 'content-type: application/json' -X POST -d @payload.json https://webhook/url<br>``` |
| ```perl<br>curl -H 'x-bbb-webhook-type: push' -H 'x-bbb-webhook-id: id-string' -H 'content-type: application/json' -X POST -d @payload.json https://webhook/url<br>``` |

|     |
| --- |
| **Payload.json** |
| ```java<br>{<br>  "origin": "repository-origin"<br>}<br>``` |

## More Webhook Articles

*   Page:
    
    [Creating reindex triggers for a single repository](/wiki/spaces/GIJDC/pages/171475191/Creating+reindex+triggers+for+a+single+repository) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding Webhooks for GitHub](/wiki/spaces/GIJDC/pages/171377121/Adding+Webhooks+for+GitHub) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding Webhooks for GitLab](/wiki/spaces/GIJDC/pages/171213219/Adding+Webhooks+for+GitLab) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Webhooks GitHub Organization Support](/wiki/spaces/GIJDC/pages/171278716/Webhooks+GitHub+Organization+Support) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding Webhooks for Azure DevOps Repos | VSTS](/wiki/spaces/GIJDC/pages/171999302/Adding+Webhooks+for+Azure+DevOps+Repos+%7C+VSTS) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding Webhooks for Azure DevOps Server | TFS](/wiki/spaces/GIJDC/pages/235274262/Adding+Webhooks+for+Azure+DevOps+Server+%7C+TFS) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding Webhooks for Bitbucket](/wiki/spaces/GIJDC/pages/498663799/Adding+Webhooks+for+Bitbucket) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding webhooks for Gerrit](/wiki/spaces/GIJDC/pages/1509032414/Adding+webhooks+for+Gerrit) (Git Integration for Jira Data Center)