---

title: Creating reindex triggers for a single repository
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

To create a webhook that triggers the reindex of a single repository, the following requirements are required::

*   The `git_http_url` matches the **Repository Origin** URL from the Jira git configuration page (Jira dashboard menu Git ➜ Manage repositories ➜ ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit integration settings**).

*   The **Content-Type** request header is set to `application/json`.

*   Use the webhook secret key from the git configuration page ➜ **Webhooks**.



The webhook is a POST request with the following JSON body:

```diff
{
  "repository":
    { "git_http_url": "https://gitlab.com/bbb-dev/bbb-testrepo.git" }
}
```

|     |
| --- |
| **For example:** |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/171475191/webhook-reindex-post-api-json.png?version=1&modificationDate=1640704081955&cacheVersion=1&api=v2) |
| **Result:**  <br>The repository is placed in the indexing queue via the git repositories configuration page (_Jira dashboard menu Git ➜ **Manage repositories**_). |