---

title: Adding Webhooks for GitLab
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Merge request webhooks are now supported. See details on this page.

Supported webhook events:

*   Push events
*   Merge request events



Git Integration for Jira Data Center app now supports **GitLab System Hooks** (menu Admin Area > System Hooks > _Merge Request events)_. However, it is only available for self-hosted GitLab instances. We highly recommend that Jira administrators should use this feature as it greatly reduces the amount of configuration time to setup webhooks.



Right-click [here](https://bigbrassband.wistia.com/medias/try008fv53) and view this video in a new browser tab.





Before you can add a webhook to your favorite git repository, you need to enable it in the git repositories configuration page of your Jira Data Center instance.

Configure webhook by logging in to your GitLab account:

1. Select a repository.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/171213219/web-hooks-gitlab-settings.png?version=1&modificationDate=1583387986115&cacheVersion=1&api=v2)

2\. Go to the settings page by clicking **Setting** on the sidebar.

3. Select **Webhooks**. The following page is displayed:

![](https://bigbrassband.com/docimgs/web-hooks-gitlab-settings-add.png)

4\. Switch to your Jira instance and copy the Webhook URL by clicking the copy icon adjacent to the URL field.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/171213219/jira-server-git-webhooks-loc-pointer.png?version=1&modificationDate=1589617459140&cacheVersion=1&api=v2)

5\. Switch back to your GitLab session and paste the obtained **_Secret URL_** from the _Git Integration for Jira_ app  >  **Webhooks** page into the **_Payload URL_** field.

6\. Select the _**Push events**_ as a triggering event option.  This is the default option when creating a new webhook.

7\. Click **Add webhook** to save the new webhook settings.



### **Merge Request Event Webhook**

The Git Integration for Jira app supports GitLab merge request webhooks now.

You will need to enable two (2) event triggers in your GitLab webhooks configuration _(Repo > Settings > Integrations)_ for it to work properly. Select both "**Push events**" and "**Merge request events**" triggers as outlined above in step **5**.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/171213219/gitlab-merge-request-event-trigger-webhook.png?version=1&modificationDate=1578535252769&cacheVersion=1&api=v2)