---

title: Adding Webhooks for Azure DevOps Server | TFS
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
        <div class='nextpara'>Supported webhook events:</div>
        <ul style='margin-bottom:0px;'>
            <li>Code pushed</li>
            <li>Pull request created</li>
            <li>Pull request updated</li>
            <li>Pull request merge attempted</li>
        </ul>
    </div>
    </div>
</div>

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/61wl72vp91?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/61wl72vp91'><b>here</b></a> and view this video in a new browser tab. (While the above video showcases VSTS/Azure DevOps, the entire process is entirely the same for Azure Repos webhooks setup.)</i>
</div>

&nbsp;

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see <a href='/git-integration-for-jira-data-center/webhooks-gij-self-managed'><b>Webhooks - Getting Started</b></a>.
    </div>
    </div>
</div>

Configure webhook by logging in to your Azure DevOps Server/TFS account:

1.  Open a project by clicking on it.

    ![](/wp-content/uploads/gij-webhooks-azure-devops-sel-proj-c.png)

2.  On the sidebar, click **Project Settings** then select **Service Hooks**. The following screen is displayed.

    ![](/wp-content/uploads/gij-webhooks-azure-devops-add-service-hooks-c.png)

3.  Click **Create subscription** to add a new service hook subscription.

4.  Scroll down to **Web Hooks** and click to select it.

5.  Click **Next**. The following screen is displayed.

    ![](/wp-content/uploads/gij-webhooks-azure-devops-triggers-cfg-c.png)

    a.  Set **"code pushed"** for the _**Trigger on this type of event**_ selector.

    b.  Set all **FILTERS** to **"Any"**.

    c.  Click **Next** to proceed to the following screen.

    ![](/wp-content/uploads/gij-webhooks-azure-devops-action-cfg-c.png)

6.  Switch to your Jira instance then navigate to **Git** ➜ **Manage repositories** page and then open **Webhooks**.

    ![](/wp-content/uploads/gij-webhooks-azure-devops-copy-webhook-url-c.png)

7.  Copy the complete Webhook URL by clicking the copy icon adjacent to the right of the URL field.

8.  Switch back to your Azure DevOps Server/TFS web portal (where you left off):

    ![](/wp-content/uploads/gij-webhooks-azure-devops-service-settings-c.png)

    a.  Paste the webhook URL into the **URL** field.

    b.  For the **HTTP header**, enter `X-GIJ-Microsoft-Event:1`. This header will improve webhook processing efficiency since we are only expecting specific MS events.

    c.  Set <u>Resource details to send</u> to **All**.

    d.  Set <u>Messages to send</u> to **None**.

    e.  Set <u>Detailed messages to send</u> to **None**.

    The settings **8.d** and **8.e** limits the data transfered to your Jira instance since too much webhook traffic can degrade Jira performance.

9. Click **Test** to verify if webhook integration is successful or not.

    ![](/wp-content/uploads/gij-webhooks-azure-devops-test-cfg-c.png)

10. Click **Finish** to complete this setup.

&nbsp;

### Pull Request Webhooks

The Git Integration for Jira app supports pull request webhooks now.

You will need to have three (3) separate service hooks configuration for it to work properly. Aside from setting up the "**Code pushed**" service hook outlined above in step **5.a**, perform the same process with **_Pull request created_** and _**Pull request updated**_ for the triggers.

![](/wp-content/uploads/gij-azure-devops-server-2019-req-service-hooks.png)

&nbsp;

### More related articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

**Adding webhooks for Azure DevOps Server \| TFS** (this page)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/adding-webhooks-for-gerrit-gij-self-managed)

