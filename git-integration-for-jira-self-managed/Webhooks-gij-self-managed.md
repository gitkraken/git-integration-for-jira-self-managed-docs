---

title: Webhooks - Features
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- hooks and webhooks -->

**What's on this page:**
- [What are webhooks and why use them?](#what-are-webhooks-and-why-use-them)
- [Do I need to set up webhooks?](#do-i-need-to-set-up-webhooks)
- [Getting started](#getting-started)
- [Advanced settings](#advanced-settings)
- [GitHub/GitLab push events](#github-or-gitlab-push-events)
- [More articles about webhooks setup](#more-articles-about-webhooks-setup)

&nbsp;
* * *
&nbsp;

### What are webhooks and why use them?

Webhooks can be an extremely powerful tool that can be configured to trigger an immediate re-index of your repositories from remote systems. Your git server can send this near real-time data to Jira when your git data changes. This results in much faster indexing time so that you don’t have to wait for the regular polling interval (see [General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)).

Webhooks can be triggered whenever certain actions are performed. For example, you can configure a webhook to execute when:

*   a new commit is pushed

*   a pull request is opened

*   a branch is merged


You can create webhooks for individual repositories or most git providers will allow you to create webhooks at an account-level or org-level.

### Do I need to set up webhooks?

Short answer is no, the [regular reindexing](/git-integration-for-jira-data-center/general-settings-gij-self-managed) configured in General settings by the Jira administrator is the base requirement for indexing. However, by configuring webhooks to trigger reindexing, Jira will more often have up-to-date information. The normal frequency of the app limits this by polling at set intervals.

Without webhooks, you will rely on the default polling of the app which is unchangeable by non-Jira administrators. Jira users will have to wait for the default interval for updates which means users will not see new commits or pull requests until the next indexing interval.

### Getting started

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>IMPORTANT!</b><br>
To use the webhooks feature, it must be enabled in the Manage (Git) repositories page.

Configure webhooks to trigger immediate reindex of your repositories from remote systems.

1.  From your Jira dashboard, go to menu Git ➜ **Manage repositories**_._ On the sidebar, under _Git Integration for Jira_, click **Webhooks**.

    ![](/wp-content/uploads/gij-gitserver-gitmgr-webhooks-sidebar-sel-c.png)

2.  Enable/disable the webhook feature by clicking on the **Enabled/Disabled** option.

    ![](/wp-content/uploads/gij-gitserver-webhooks-settings-page-c.png)

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Copy the webhook URL to the system clipboard by clicking the copy icon adjacent to the right. Use this URL when required by the repository web hooks setting of your git host.
    </div>
    </div>
</div>

The **Secret Key** is a secure random-generated alphanumeric string at the time of the Git Integration for Jira app installation. The user can change this to a different value by generating another secret token according to your Git host.

Use this key in the form of:

```java
<JIRA_BASE_URL>/git/webhook/reindex/<SECRET_KEY>
```

**Assign your Jira base URL and Secret Key to the sample URL structure**

Example:<br>
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
        <p style='margin-bottom:0 !important'>There is no support for other HTTP methods such as <code>DELETE</code> or <code>HEAD</code>.</p>
    </div>
    </div>
</div>

&nbsp;

### Advanced settings

The advanced options provide a couple of settings for webhook indexing performance improvements.

![](/wp-content/uploads/gij-gitserver-webhooks-ignore-dups-and-min-ridx-adv.png)

**Ignore unmatching webhooks** – Continuous reindexing of all repositories may cause significant performance issues if unmatching webhooks are not ignored. When set to `Enabled` (default), this setting filters out incoming webhooks without a matching repository. This setting is `Enabled` by default for new and upgrading users.

**Min. repository reindex interval** – The frequency of reindexing is set to a maximum of this value (in minutes). Default value is 5 minutes. Set this value to 0 (zero) to disable this setting.

&nbsp;

### GitHub or GitLab push events

The Git Integration for Jira app supports GitLab and GitHub push event to define individual repository to index.

The webhook parses the following payload formats:

**GITHUB (Introduced v2.7.10)**

```json
{   
    "repository": {   
        "git_url": "git://github.com/testuser01/test-repo.git",
        "ssh_url": "git@github.com:testuser01/test-repo.git",
        "clone_url": "https://github.com/testuser01/public-repo.git",
        "svn_url": "https://github.com/testuser01/public-repo"
    }
}
```

<br>

**GITLAB**

```json
{   
    "repository": {   
        "git_ssh_url": "git@gitlab.com:testuser01/test-master.git",
        "git_http_url": "https://gitlab.com/testuser01/test-master.git"
    }
}
```

&nbsp;

### More articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/Adding-webhooks-for-Gerrit-gij-self-managed)

