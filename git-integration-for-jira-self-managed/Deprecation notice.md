---

title: Deprecation notice
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
|     |     |     |
| --- | --- | --- |
| **Feature** | **Date** | **Details of ending support, removal or obsolescence** |
| Integrations feature settings: Limit commits | After 1 January 2021 | The 'Limit commits...' setting is deprecated and will be removed. Thenceforth, all commits will be limited by project permissions.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/attachments/2046197780/limit-commit-deprecation-notice.png?version=1&modificationDate=1641384212542&cacheVersion=1&api=v2) |
| Personal access tokens | Dependent on which Git service | Some Git services such as GitLab and GitHub are enforcing authentication access for users to use personal access tokens in accessing git resources and services. |
| `${username}` | Effective 29 April 2019 | The `${username}` is used when logging into Jira and in the branch name template to generate a default name for newly-created branches. This template variable is deprecated as Atlassian is no longer making usernames available. |
| Ignore unmatching webhooks | Starting v3.8+ | We will no longer reindex all repositories by default when a webhook arrives without a matching repository. There will be a setting in the Webhooks setting page where the previous functionality can be restored.<br><br>The advanced options provide a couple of settings for webhook indexing performance improvements.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/attachments/2046197780/gitserver-webhooks-ignore-dups-and-min-ridx-adv.png?version=1&modificationDate=1641384212549&cacheVersion=1&api=v2) |
| _(more to come)_ |     |     |