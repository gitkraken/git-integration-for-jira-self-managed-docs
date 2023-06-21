---

title: Adding webhooks for Gerrit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
<img src='/wp-content/uploads/gij-gerrit-webhook-banner.png' width=510 height=117 style='display:block;margin:25px auto;max-width:!00%' />

&nbsp;

### Introduction

Webhooks are not configured by default in Gerrit. They are not built into Gerrit just like they are in GitHub, GitLab and etc. Thus, when calling Gerrit webhooks, these won't trigger the reindex of the integration / repositories.

&nbsp;

### Installation

To use webhooks with Gerrit, it needs to be configured.

For starters, install Gerrit with the webhook plugin by reading at [https://gerrit.googlesource.com/plugins/webhooks/](https://gerrit.googlesource.com/plugins/webhooks/) and the steps below.

**Project (repository) list:**

```powershell
curl http(s)://your.org.com:8080/projects/?d
```

**Enabled webhooks for the repository, for example, MyTestRepo:**

```powershell
curl http(s)://your.org.com:8080/config/server/webhooks~projects/MyTestRepo/remotes
```

**Add webhook for the repository:**

```powershell
curl --user username:password -H 'Content-Type: application/json' -X PUT -d @webhook.json http(s)://your.org.com:8080/a/config/server/webhooks~projects/MyTestRepo/remotes/bbb-webhook
```

Where `webhook.json`:
```json
{
   "url" : "https://example.com/webhook/url",
   "maxTries" : 3,
   "sslVerify": true
}
```

&nbsp;

### Manually Trigger Webhooks

Create a webhook that can be triggered for any **individual** repository. It can be used with continuous integration service

_**Required headers:**_

*   'x-bbb-webhook-type': `PUSH`

*   'Content-Type': `application/json`


_**Optional headers:**_

*   'x-bbb-webhook-id' -- Can be any string representing the id of the request to be used.

<br>

**Usage examples:**

```powershell
curl -H 'x-bbb-webhook-type: push' -H 'content-type: application/json' -X POST -d @payload.json https://webhook/url
```

```powershell
curl -H 'x-bbb-webhook-type: push' -H 'x-bbb-webhook-id: id-string' -H 'content-type: application/json' -X POST -d @payload.json https://webhook/url
```

<br>

**Payload.json**

```json
{  
    "origin": "repository-origin"
}
```

&nbsp;

### More related articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

**Adding webhooks for Gerrit** (this page)

