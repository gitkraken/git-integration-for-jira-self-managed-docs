---

title: Adding webhooks for Gerrit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1509032414/gerrit-webhook-banner.png?version=1&modificationDate=1618656373661&cacheVersion=1&api=v2&width=510&height=117)

<br>

## Introduction

Webhooks are not configured by default in Gerrit. They are not built into Gerrit just like they are in GitHub, GitLab and etc. Thus, when calling Gerrit webhooks, these won't trigger the reindex of the integration / repositories.

## Installation

To use webhooks with Gerrit, it needs to be configured.

For starters, install Gerrit with the webhook plugin by reading at [https://gerrit.googlesource.com/plugins/webhooks/](https://gerrit.googlesource.com/plugins/webhooks/) and the steps below.

**Project (repository) list**

```powershell
curl http(s)://your.org.com:8080/projects/?d
```

**Enabled webhooks for the repository, for example, MyTestRepo**

```powershell
curl http(s)://your.org.com:8080/config/server/webhooks~projects/MyTestRepo/remotes
```

**Add webhook for the repository**

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

<br>

## Manually Trigger Webhooks

Create a webhook that can be triggered for any **individual** repository. It can be used with continuous integration service

_**Required headers:**_

*   'x-bbb-webhook-type': `PUSH`

*   'Content-Type': `application/json`


_**Optional headers:**_

*   'x-bbb-webhook-id' -- Can be any string representing the id of the request to be used.

<br>

**Usage examples:**

```java
curl -H 'x-bbb-webhook-type: push' -H 'content-type: application/json' -X POST -d @payload.json https://webhook/url
```

```java
curl -H 'x-bbb-webhook-type: push' -H 'x-bbb-webhook-id: id-string' -H 'content-type: application/json' -X POST -d @payload.json https://webhook/url
```

<br>

**Payload.json**

```json
{  
    "origin": "repository-origin"
}
```

