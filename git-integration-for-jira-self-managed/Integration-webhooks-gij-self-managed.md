---

title: Integration webhooks
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Trigger immediate reindex of your repositories from remote systems via webhooks. For more information about this topic, see [About GitLab Webhooks](https://gitlab.com/gitlab-org/gitlab-ce/blob/master/doc/web_hooks/web_hooks.md).

&nbsp;

### Getting started

Setup webhooks for your configured integration/repositories from remote systems by enabling the feature first.

![](/wp-content/uploads/gij-gitserver-gitmgr-manage-webhooks.png)

1.  From your Jira dashboard, go to the **Git** menu.

2.  Click **Manage repositories**.

3.  Click **Webhooks** on the sidebar to open the Webhooks configuration page.

4.  Turn on the webhook feature by setting **Reindex via webhooks** to `Enabled`.


![](/wp-content/uploads/gij-gitserver-gitmgr-webhooks-cfg-page.png)

Use the **Webhook URL** to setup webhook for your remote git host. For detailed information on webhook configuration, see [Webhooks](/git-integration-for-jira-data-center/webhooks-gij-self-managed).

The **Secret Key** is a secure random-generated alphanumeric string at the time of the Git Integration for Jira app installation. The user can change this to a different value by generating another secret token according to your Git host.

Use this key in the form of:

```powershell
<JIRA_BASE_URL>/git/webhook/reindex/<SECRET_KEY>
```

**Assign your Jira base URL and Secret Key to the sample URL structure:**

```powershell
https://your.jira.com/rest/gitplugin/webhook/1.0/reindex/sdf34tGdfgGDG345g3y0045TYG23te37
```

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        All the repositories will be reindexed if the URL specified above is activated through <code>GET</code>, <code>POST</code>, or <code>PUT</code> and the webhooks are enabled.
        <div class='nextpara'>
            There is no support for other HTTP methods such as <code>DELETE</code> or <code>HEAD</code>.
    </div>
    </div>
</div>

For more information about triggers and event types, see [Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/creating-reindex-triggers-for-a-single-repository-gij-self-managed).

&nbsp;

### Advanced settings

The advanced options provide a couple of settings for webhook indexing performance improvements.

![](/wp-content/uploads/gij-gitserver-webhooks-ignore-dups-and-min-ridx-adv.png)

**Ignore unmatching webhooks** – Continuous reindexing of all repositories may cause significant performance issues if unmatching webhooks are not ignored. When set to `Enabled` (default), this setting filters out incoming webhooks without a matching repository. This setting is `Enabled` by default for new and upgrading users.

**Min. repository reindex interval** – The frequency of reindexing is set to a maximum of this value (in minutes). Default value is 5 minutes. Set this value to 0 (zero) to disable this setting.

&nbsp;
* * *

[**Prev:** JQL searching](/git-integration-for-jira-data-center/jql-searching-gij-self-managed)

[**Next:** Jira Data Center (High availability and clustering)](/git-integration-for-jira-data-center/jira-data-center-(high-availability-and-clustering)-gij-self-managed)


