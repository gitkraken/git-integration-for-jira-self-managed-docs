---

title: Setting up webhooks
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Before you can use webhooks, it needs to be enabled in the Git Integration for Jira webhook settings.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396415/jira-server-git-webhooks-new(c).png?version=1&modificationDate=1630642793039&cacheVersion=1&api=v2)

Access the Git Integration for Jira app webhook configuration page:

1.  Go to Jira dashboard menu Git ➜ **Manage repositories**.

2.  On the sidebar under _Git Integration for Jira_, click **Webhooks**.

3.  Enable the webhook feature by setting it to **Enabled**.


On this page, you can also find the **Webhook URL** and the **Secret key** for use with your git host webhook configuration.

## Secret key

The secret key is a secure random-generated alphanumeric string at the time of the Git Integration for Jira app installation.

Disabling, reinstalling or even installing another version of the Git Integration for Jira app does not change the value of the key (for security purposes and unique identity). Administrators can manually change this key to a different value by generating another secret token according to your Git host and organization policies. For instance:

```ruby
ruby -rsecurerandom -e 'puts SecureRandom.hex(32)'
```

The secret key also has the same restrictions on the valid set of characters as a regular URL. Invalid characters such as spaces, slashes, colon, etc. are not allowed. The default recommended length for the secret key is 32 chars and the maximum length is 255 chars.

## More information on webhooks configuration

For detailed information on setting up webhooks for supported git hosts, see [Git Integration for Jira: Integration webhooks](/git-integration-for-jira-self-managed/Integration-webhooks).

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app supports GitHub and GitLab push events to define individual repository to index. For more information, see <a href='/git-integration-for-jira-self-managed/creating-reindex-triggers-for-a-single-repository/'>Creating reindex triggers manually</a>.
    </div>
    </div>
</div>

* * *

[Previous: Setting up web linking](/git-integration-for-jira-self-managed/setting-up-web-linking/)

[Next: Increasing timeout threshold for large repositories while doing a Git pull](/git-integration-for-jira-self-managed/increasing-timeout-threshold-for-large-repositories-while-doing-a-git-pull/)

