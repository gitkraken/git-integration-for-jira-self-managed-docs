---

title: Creating reindex triggers for a single repository
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

To create a webhook that triggers the reindex of a single repository, the following requirements are required::

*   The `git_http_url` matches the **Repository Origin** URL from the Jira git configuration page (Jira dashboard menu Git ➜ Manage repositories ➜Actions ➜ **Edit integration settings**).

*   The **Content-Type** request header is set to `application/json`.

*   Use the webhook secret key from the git configuration page ➜ **Webhooks**.

<br>

The webhook is a POST request with the following JSON body:

```json
{
  "repository": { "git_http_url": "https://gitlab.com/bbb-dev/bbb-testrepo.git" 
  }
}
```

**For example:**

![](https://bigbrassband.atlassian.net/wiki/download/attachments/171475191/webhook-reindex-post-api-json.png?version=1&modificationDate=1640704081955&cacheVersion=1&api=v2)

<br>

**Result:**

The repository is placed in the indexing queue via the git repositories configuration page (_Jira dashboard menu Git ➜ **Manage repositories**_).

