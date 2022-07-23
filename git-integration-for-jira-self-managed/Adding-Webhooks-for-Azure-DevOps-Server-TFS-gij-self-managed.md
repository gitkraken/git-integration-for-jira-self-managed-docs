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
        Pull request webhooks are now supported. See details on this page.
        <div class='nextpara'>Supported webhook events:</div>
        <ul>
            <li>Code pushed</li>
            <li>Pull request created</li>
            <li>Pull request updated</li>
            <li>Pull request merge attempted</li>
        </ul>
    </div>
    </div>
</div>
<br>

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/61wl72vp91?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/61wl72vp91'><b>here</b></a> and view this video in a new browser tab. (While the above video showcases VSTS/Azure DevOps, the entire process is entirely the same for Azure Repos webhooks setup.)</i>
</div>
<br>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see <a href='/git-integration-for-jira-data-center/webhooks-gij-self-managed/'><b>Webhooks - Getting Started</b></a>.
    </div>
    </div>
</div>
<br>

1.  Configure webhook by logging in to your Azure DevOps Server/TFS account:

2.  Open a project by clicking on it.

3.  Click **Project Settings** (sidebar) then select **Service Hooks**. The following screen is displayed.

    ![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-add-shooks.png)

4.  Click  **+**  to add a new service hook subscription.

5.  Scroll to **Web Hooks** and click to select it.

6.  Click **Next**. The following screen is displayed.

    ![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-triggers-cfg.png)

    *   Set **"code pushed"** for the _**Trigger on this type of event**_ selector.
    
    *   Set all **FILTERS** to **"Any"**.
    
    *   Click **Next** to proceed to the following screen.

    ![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-action-cfg.png)

7.  Switch to your Jira instance then navigate to Git ➜ **Manage repositories** page and then open **Webhooks**.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/235274262/jira-server-git-webhooks-loc-pointer.png?version=1&modificationDate=1589621082796&cacheVersion=1&api=v2)

8.  Copy the complete Webhook URL by clicking the copy icon adjacent to the right of the URL field.

9.  Switch back to Azure DevOps Server/TFS (where you left off) and paste this information into the provided **URL** box.

10. Click **Test** to verify if webhook integration is successful or not.

    ![](https://bigbrassband.com/confluence/images/webhooks-azure-devops-test-cfg.png)

11. Click **Finish** to complete this setup.



### **Pull Request Webhooks**

The Git Integration for Jira app supports pull request webhooks now.

You will need to have three (3) separate service hooks configuration for it to work properly. Aside from setting up the "**Code pushed**" service hook outlined above in step **6.a**, perform the same process with **_Pull request created_** and _**Pull request updated**_ for the triggers.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/235274262/azure-devops-server-2019-req-service-hooks.png?version=1&modificationDate=1578491768289&cacheVersion=1&api=v2)

