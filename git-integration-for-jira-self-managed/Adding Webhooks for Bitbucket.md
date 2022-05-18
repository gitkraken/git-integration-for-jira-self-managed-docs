---

title: Adding Webhooks for Bitbucket
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Pull request webhooks are now supported.  [See details](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/498663799/Adding+Webhooks+for+Bitbucket#Pull-Request-Webhooks) on this page.

Supported webhook events:

*   _Repository_ - Push

*   _Pull request -_ Created

*   _Pull request_ - Updated


Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance.  For more details, see [**Integration Webhooks**](https://bigbrassband.atlassian.net/wiki/spaces/~493751811/pages/452329484/Integration+Webhooks).

1.  Configure webhook by logging in to your Bitbucket:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/webhooks-bitbucket-add-shooks(c).png?version=1&modificationDate=1589622081232&cacheVersion=1&api=v2&width=408&height=329)
2.  Open a project by clicking on it.

3.  Click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Repository Settings** then under **WORKFLOW**, select **Webhooks**.

4.  Click **Add webhook** to create a webhook for the repository. The _**Add new webhook**_ screen appears.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/webhooks-add-new-whook-bitbucket-dlg(w).png?version=1&modificationDate=1589622080715&cacheVersion=1&api=v2&width=578&height=759)
    1.  **Title** - This is the title name for this webhook.

    2.  **URL** - This field accepts the webhook url from your Git Integration for Jira app > **Webhooks** setting.

    3.  **Triggers** - By default, the trigger for the webhook is a repository push. If you want different actions to trigger the webhook, click _**Choose from a full list of triggers**_. The list of all the webhook trigger event types is displayed.
        Set the necessary scope depending on your organization access/usage rules. For this guide, choose the following triggers:

        1.  Repository - **Push** (required)

        2.  Pull Request (optional) - select these options to also include the pull request triggers

            *   **Created**

            *   **Updated**

5.  Switch to your Jira instance then navigate to **Git** > **Manage repositories** page and then open **Webhooks**.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/jira-server-git-webhooks-loc-pointer-list.png?version=1&modificationDate=1589622080453&cacheVersion=1&api=v2&width=646&height=298)
6.  Copy the complete Webhook URL by clicking the copy icon adjacent to the right of the URL field.

7.  Switch back to Bitbucket (where you left off) and paste this information into the provided **URL** box.

8.  Enter a meaningful **Title** name for this webhook.

9.  For the **Triggers**, if your organization does not require pull request events, select ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Repository push**. Otherwise, select _**Choose from a full list of triggers**_ (recommended) and then tick Repository (**Push**) and Pull Request (**Created**, **Updated**).

10.  Click **Save** to complete this setup.


### **Pull Request Webhooks**

The Git Integration for Jira app supports pull request webhooks now.

For pull request triggers, you will need to have three (3) separate service hooks configuration for it to work properly. See step 9, second option for the webhook triggers.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/webhooks-bitbucket-sample.png?version=1&modificationDate=1589622080978&cacheVersion=1&api=v2&width=680&height=195)