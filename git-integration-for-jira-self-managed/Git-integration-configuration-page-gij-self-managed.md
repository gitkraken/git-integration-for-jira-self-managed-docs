---

title: Git integration configuration page
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-manage-git-repo-screen.png?version=1&modificationDate=1630642814252&cacheVersion=1&api=v2)

On this page, you will be able to setup your git repositories and connect them to Jira via Manage git repositories page. Utilize the following features for git integration and configuration:

- [Add new integration panel](#add-new-integration-panel)
- [Connect to Git repository](#connect-to-git-repository)
- [Enable all or Disable all](#enable-all-or-disable-all)
- [Bulk change](#bulk-change)
- [Reindex all](#reindex-all)
- [Webhooks](#webhooks)
- [Related helpful tips](#related-helpful-tips)

* * *

## Add new integration panel

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-auto-connect-panel.png?version=1&modificationDate=1630642814741&cacheVersion=1&api=v2)

Formerly known as Auto-Connect integration panel.

In here, you will find special integration options for specific git hosts. This feature supports multiple connected repositories and automates git integration.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We highly recommend this feature for multiple repository configuration.
    </div>
    </div>
</div>

For more details on supported git hosts, see the Auto-connect section in our [Integration guides](/git-integration-for-jira-self-managed/Integration-Guides).

The **Add tracked folder** connection feature is added to the **Add new integration** panel for easy access.

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>GitLab</b><br>
        We are dropping support for Gitlab API v3. Please use <b>GitLab API v4</b> when adding new integrations for increased security.
    </div>
    </div>
</div>

## Connect to Git repository

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-connect-git-repo.png?version=1&modificationDate=1630642815446&cacheVersion=1&api=v2)

This feature opens the Connect wizard.

You can connect single git repositories using this setup such as git protocol, SSH, HTTP/HTTPS, etc. Clicking the adjacent **…** will open the dropdown list of integration options such as [Add tracked folder](/git-integration-for-jira-self-managed/Tracked-Folders) and equivalent integration connection options. |

## Enable all or Disable all

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-enable-disable-all.png?version=1&modificationDate=1630642815698&cacheVersion=1&api=v2)

The **Enable all** function will enable each integration in the repository list and mark all checkboxes in the _**Enabled**_ column. The **Disable all** function will disable each integration in the repository list and unmark all the checkboxes in the _**Enabled**_ column.

## Bulk change

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-bulk-change.png?version=1&modificationDate=1630642815933&cacheVersion=1&api=v2)

Bulk change provides an easier way to import or export repository configuration. This feature is useful when you are migrating from an old server to a new server and is also recommended when upgrading to a new version of Git Integration for Jira app.

**Export Configuration**  – this function will export your repository integration configuration to a tab-delimited file (.TSV).

**Import Configuration**  – this function will import your repository integration configuration from a tab-delimited file (.TSV).

For more information, see [Bulk change](/git-integration-for-jira-self-managed/Bulk-change).

## Reindex all

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-reindex-all.png?version=1&modificationDate=1630642816165&cacheVersion=1&api=v2)

This function will perform a reindex queue of all integration in the repository list. Disabled integrations are ignored.

For more information on this topic, see [Reindexing](/git-integration-for-jira-self-managed/Reindexing).

## Webhooks

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396951/gitserver-webhooks-sidebar.png?version=1&modificationDate=1630642817385&cacheVersion=1&api=v2)

Opens the Webhooks configuration page. Enable/disable webhooks to trigger immediate reindex of the connected git repositories and integration.

For more information about this topic, click [here](/git-integration-for-jira-self-managed/Integration-webhooks) to go to the **Webhooks documentation page**.

## Related helpful tips

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>SSH</b><br>
        When setting up repositories with the Git Integration app, you need to have the necessary access permissions on the private key on the Git server to proceed.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Windows Server</b><br>
        For cases when git repositories are hosted at Windows servers (Windows Server network drive) — while it is using the Windows server networking, the network credentials accessing the git repository must be the same as the user running Jira.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Windows Network Share</b><br>
        When using Windows network sharing for the repository origin, it is recommended to allocate repositories’ paths shorter than 256 characters.
        <div class='next para'>Example: <code>\\WS129\custom-repo\project-z\</code></div>
        <div>Otherwise, the provided URL will not be recognized as valid.</div>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>For Jira hosted on Windows</b><br>
        When using Active Directory accounts for repository access, changing the password of the AD account running Jira can cause repository authentication issues.
        <div class='nextpara'>The solution for this is to restart Jira to regain access to repositories.</div>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Repository REST API</b><br>
        As of <b>v2.8.3+</b> of the Git Integration for Jira app, the REST API for managing repositories are implemented. The documentation for this feature is available at <a href='/git-integration-for-jira-self-managed/Repository-API'>Repository REST API</a>.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Integration REST API<b><br>
        As of **v3.5.0.2+** of the Git Integration for Jira app, the REST API for managing integrations are implemented. The documentation for this feature is available at <a href='/git-integration-for-jira-self-managed/Integration-API'>Integration REST API</a>.
    </div>
    </div>
</div>

