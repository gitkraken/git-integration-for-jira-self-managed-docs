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
        Pull request webhooks are now supported. See <a href='#pull-request-webhooks'>details</a> on this page.
        <p>Supported webhook events:</p>
        <ul>
            <li><i>Repository</i> - Push</li>
            <li><i>Pull request</i> - Created</li>
            <li><i>Pull request</i> - Updated</li>
        </ul>
    </div>
    </div>
</div>
<br>
<br>

<div class='embed-container' style='padding-bottom:56.25%'>
    <iframe width='709' height='399' src='https://fast.wistia.com/embed/iframe/s26h3avwuo?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/v2c5qrgps8'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i><br>
    <i>(While the above video showcases other integration, jump to 01:41 to see Webhook setup for Bitbucket Cloud.)</i>
</div>
<br>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see <a href='/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed'><b>Integration Webhooks</b></a>.
    </div>
    </div>
</div>
<br>

1.  Configure webhook by logging in to your Bitbucket:

    ![](/wp-content/uploads/webhooks-bitbucket-add-shooks-c.png)

2.  Open a project by clicking on it.

3.  Click **Repository Settings** then under **WORKFLOW**, select **Webhooks**.

4.  Click **Add webhook** to create a webhook for the repository. The _**Add new webhook**_ screen appears.

    ![](/wp-content/uploads/gij-webhooks-add-new-whook-bitbucket-dlg-w.png)

    *   **Title** - This is the title name for this webhook.

    *   **URL** - This field accepts the webhook url from your Git Integration for Jira app > **Webhooks** setting.

    *   **Triggers** - By default, the trigger for the webhook is a repository push. If you want different actions to trigger the webhook, click _**Choose from a full list of triggers**_. The list of all the webhook trigger event types is displayed.

        Set the necessary scope depending on your organization access/usage rules. For this guide, choose the following triggers:

        1.  Repository - **Push** (required)

        2.  Pull Request (optional) - select these options to also include the pull request triggers:

            *   **Created**
            *   **Updated**

5.  Switch to your Jira instance then navigate to **Git** > **Manage repositories** page and then open **Webhooks**.

    ![](/wp-content/uploads/gij-jira-server-git-webhooks-loc-pointer-list.png)

6.  Copy the complete Webhook URL by clicking the copy icon adjacent to the right of the URL field.

7.  Switch back to Bitbucket (where you left off) and paste this information into the provided **URL** box.

8.  Enter a meaningful **Title** name for this webhook.

9.  For the **Triggers**, if your organization does not require pull request events, select **Repository push**. Otherwise, select _**Choose from a full list of triggers**_ (recommended) and then tick Repository (**Push**) and Pull Request (**Created**, **Updated**).

10.  Click **Save** to complete this setup.


### Pull Request Webhooks

The Git Integration for Jira app supports pull request webhooks now.

For pull request triggers, you will need to have three (3) separate service hooks configuration for it to work properly. See step 9, second option for the webhook triggers.

![](/wp-content/uploads/gij-webhooks-bitbucket-sample.png)

<br>

## More related articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

**Adding webhooks for Bitbucket** (this page)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/adding-webhooks-for-gerrit-gij-self-managed)

