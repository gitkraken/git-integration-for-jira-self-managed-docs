---

title: Setting up webhooks
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Before you can use webhooks, it needs to be enabled in the Git Integration for Jira webhook settings.

<img src='/wp-content/uploads/gij-git-serverdc-git-webhooks-new-c.png' style='display:block;margin:25px auto;max-width:100%' />

Access the Git Integration for Jira app webhook configuration page:

1.  Go to Jira dashboard menu Git ➜ **Manage repositories**.

2.  On the sidebar under _Git Integration for Jira_, click **Webhooks**.

3.  Enable the webhook feature by setting it to **Enabled**.


On this page, you can also find the **Webhook URL** and the **Secret key** for use with your git host webhook configuration.

## Secret key

The secret key is a secure random-generated alphanumeric string at the time of the Git Integration for Jira app installation.

Disabling, reinstalling or even installing another version of the Git Integration for Jira app does not change the value of the key (for security purposes and unique identity). Administrators can manually change this key to a different value by generating another secret token according to your Git host and organization policies. For instance:

```powershell
ruby -rsecurerandom -e 'puts SecureRandom.hex(32)'
```

The secret key also has the same restrictions on the valid set of characters as a regular URL. Invalid characters such as spaces, slashes, colon, etc. are not allowed. The default recommended length for the secret key is 32 chars and the maximum length is 255 chars.

## More information on webhooks configuration

For detailed information on setting up webhooks for supported git hosts, see [Git Integration for Jira: Integration webhooks](/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed).

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app supports GitHub and GitLab push events to define individual repository to index. For more information, see <a href='/git-integration-for-jira-data-center/creating-reindex-triggers-for-a-single-repository-gij-self-managed'>Creating reindex triggers manually</a>.
    </div>
    </div>
</div>
<br>

<br>
<br>

[**Prev:** Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

[**Next:** Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-Git-pull-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More related articles on Git for Jira administrators

[Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

[New GitLab v10+ authentication](/git-integration-for-jira-data-center/New-GitLab-v10-authentication-gij-self-managed)

[General settings: Improving Jira performance](/git-integration-for-jira-data-center/general-settings-Improving-Jira-performance-gij-self-managed)

[Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-servers-or-windows-network-share-(admins)-gij-self-managed)

[Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-data-center/setting-up-repository-root-not-located-in-Jira-Home-directory-(admins)-gij-self-managed)

[Reindex API to trigger indexing](/git-integration-for-jira-data-center/reindex-API-to-trigger-indexing-gij-self-managed)

[Recommended reindex interval setting](/git-integration-for-jira-data-center/recommended-reindex-interval-setting-gij-self-managed)

[Setting up web linking](/git-integration-for-jira-data-center/setting-up-web-linking-gij-self-managed)

**Setting up webhooks** (this page)

[Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-data-center/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull-gij-self-managed)

[Working with Tracked folders](/git-integration-for-jira-data-center/working-with-Tracked-folders-gij-self-managed)

[Recommended upgrade method for Git Integration for Jira](/git-integration-for-jira-data-center/recommended-upgrade-method-for-git-integration-for-jira-gij-self-managed)

[Discard cloned files in Jira Home directory (General setting)](/git-integration-for-jira-data-center/discard-cloned-files-in-Jira-Home-directory-(general-setting)-gij-self-managed)


