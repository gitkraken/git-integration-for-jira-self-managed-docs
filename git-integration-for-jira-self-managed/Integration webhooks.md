---

title: Integration webhooks
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Trigger immediate reindex of your repositories from remote systems via webhooks. For more information about this topic, see [**About GitLab Webhooks**](https://gitlab.com/gitlab-org/gitlab-ce/blob/master/doc/web_hooks/web_hooks.md).

## Getting started

Setup webhooks for your configured integration/repositories from remote systems by enabling the feature first.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399378/gitserver-gitmgr-manage-webhooks.png?version=2&modificationDate=1639304410476&cacheVersion=1&api=v2)

1.  From your Jira dashboard, go to the **Git** menu.

2.  Click **Manage repositories**.

3.  Click **Webhooks** on the sidebar to open the Webhooks configuration page.

4.  Turn on the webhook feature by setting **Reindex via webhooks** to `Enabled`.


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399378/gitserver-gitmgr-webhooks-cfg-page.png?version=1&modificationDate=1630642934511&cacheVersion=1&api=v2&width=680&height=270)

Use the **Webhook URL** to setup webhook for your remote git host. For detailed information on webhook configuration, see [Webhooks](/git-integration-for-jira-self-managed/Webhooks).

The **Secret Key** is a secure random-generated alphanumeric string at the time of the Git Integration for Jira app installation. The user can change this to a different value by generating another secret token according to your Git host.

Use this key in the form of:

```java
<JIRA_BASE_URL>/git/webhook/reindex/<SECRET_KEY>
```

|     |
| --- |
| **Assign your Jira base URL and Secret Key to the sample URL structure.** |
| Example:<br><br>```java<br>https://your.jira.com/rest/gitplugin/webhook/1.0/reindex/sdf34tGdfgGDG345g3y0045TYG23te37<br>``` |

All the repositories will be reindexed if the URL specified above is activated through `GET`, `POST`, or `PUT` and the webhooks are enabled.

There is no support for other HTTP methods such as  `DELETE`  or  `HEAD` .


For more information about triggers and event types, see [Creating reindex triggers for a single repository](/git-integration-for-jira-self-managed/creating-reindex-triggers-for-a-single-repository/).

## Advanced settings

The advanced options provide a couple of settings for webhook indexing performance improvements.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399378/gitserver-webhooks-ignore-dups-and-min-ridx-adv.png?version=2&modificationDate=1641382342014&cacheVersion=1&api=v2&width=680&height=151)

**Ignore unmatching webhooks** – Continuous reindexing of all repositories may cause significant performance issues if unmatching webhooks are not ignored. When set to `Enabled` (default), this setting filters out incoming webhooks without a matching repository. This setting is `Enabled` by default for new and upgrading users.

**Min. repository reindex interval** – The frequency of reindexing is set to a maximum of this value (in minutes). Default value is 5 minutes. Set this value to 0 (zero) to disable this setting.
