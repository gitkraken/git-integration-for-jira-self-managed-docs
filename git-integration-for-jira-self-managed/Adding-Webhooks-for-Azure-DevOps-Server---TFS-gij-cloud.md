---

title: Adding Webhooks for Azure DevOps Server | TFS
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Pull request webhooks are now supported. [See details](/wiki/pages/resumedraft.action?draftId=235274262#AddingWebhooksforAzureDevOpsServer|TFS-pullreq) on this page.

Supported webhook events:

*   Code pushed
*   Pull request created
*   Pull request updated
*   Pull request merge attempted



Right-click [here](https://bigbrassband.wistia.com/medias/61wl72vp91) and view this video in a new browser tab. (While the above video showcases VSTS/Azure DevOps, the entire process is entirely the same for Azure Repos webhooks setup.)



Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance.  For more details, see [**Webhooks - Getting Started**](/wiki/spaces/GITCLOUD/pages/171475219/Indexing+Triggers).

****1.**** Configure webhook by logging in to your Azure DevOps Server/TFS account:

**2.** Open a project by clicking on it.

**3.** Click **Project Settings** 
 (sidebar) then select **Service Hooks**. The following screen is displayed.

![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-add-shooks.png)

**4.** Click  **+**  to add a new service hook subscription.

**5.** Scroll to **Web Hooks** and click to select it.

**6.** Click **Next** . The following screen is displayed.

![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-triggers-cfg.png)

**a.** Set **"code pushed"** for the _**Trigger on this type of event**_ selector.

**b.** Set all **FILTERS** to **"Any"**.

**c.** Click **Next** to proceed to the following screen.

![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-action-cfg.png)

**7.** Switch to your Jira instance then navigate to **Git** > **Manage repositories** page and then open **Webhooks**.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/235274262/jira-server-git-webhooks-loc-pointer.png?version=1&modificationDate=1589621082796&cacheVersion=1&api=v2)

**8.** Copy the complete Webhook URL by clicking the copy icon adjacent to the right of the URL field.

**9.** Switch back to Azure DevOps Server/TFS (where you left off) and paste this information into the provided **URL** box.

**10.** Click **Test** to verify if webhook integration is successful or not.

![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-test-cfg.png)

**11.** Click **Finish** to complete this setup.



### **Pull Request Webhooks**

The Git Integration for Jira app supports pull request webhooks now.

You will need to have three (3) separate service hooks configuration for it to work properly. Aside from setting up the "**Code pushed**" service hook outlined above in step **6.a**, perform the same process with **_Pull request created_** and _**Pull request updated**_ for the triggers.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/235274262/azure-devops-server-2019-req-service-hooks.png?version=1&modificationDate=1578491768289&cacheVersion=1&api=v2)