---

title: Adding Webhooks for Bitbucket
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Pull request webhooks are now supported. See details on this page.
        <div class='nextpara'>Supported webhook events:</div>
        <ul>
            <li><i>Repository</i> - Push</li>
            <li><i>Pull request</i> - Created</li>
            <li><i>Pull request</i> - Updated</li>
        </ul>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see <a href='/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed/'><b>Integration Webhooks</b></a>.
    </div>
    </div>
</div>
<br>

1.  Configure webhook by logging in to your Bitbucket:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/webhooks-bitbucket-add-shooks(c).png?version=1&modificationDate=1589622081232&cacheVersion=1&api=v2&width=408&height=329)

2.  Open a project by clicking on it.

3.  Click **Repository Settings** then under **WORKFLOW**, select **Webhooks**.

4.  Click **Add webhook** to create a webhook for the repository. The _**Add new webhook**_ screen appears.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/webhooks-add-new-whook-bitbucket-dlg(w).png?version=1&modificationDate=1589622080715&cacheVersion=1&api=v2&width=578&height=759)

    *   **Title** - This is the title name for this webhook.

    *   **URL** - This field accepts the webhook url from your Git Integration for Jira app > **Webhooks** setting.

    *   **Triggers** - By default, the trigger for the webhook is a repository push. If you want different actions to trigger the webhook, click _**Choose from a full list of triggers**_. The list of all the webhook trigger event types is displayed.

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

9.  For the **Triggers**, if your organization does not require pull request events, select **Repository push**. Otherwise, select _**Choose from a full list of triggers**_ (recommended) and then tick Repository (**Push**) and Pull Request (**Created**, **Updated**).

10.  Click **Save** to complete this setup.


### **Pull Request Webhooks**

The Git Integration for Jira app supports pull request webhooks now.

For pull request triggers, you will need to have three (3) separate service hooks configuration for it to work properly. See step 9, second option for the webhook triggers.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/498663799/webhooks-bitbucket-sample.png?version=1&modificationDate=1589622080978&cacheVersion=1&api=v2&width=680&height=195)

