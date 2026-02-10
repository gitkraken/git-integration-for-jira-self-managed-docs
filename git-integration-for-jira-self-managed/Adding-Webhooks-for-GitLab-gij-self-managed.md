---

title: Adding Webhooks for GitLab
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
        Merge request webhooks are now supported. See <a href='#merge-request-event-webhook'>details</a> on this page.
        <p>Supported webhook events:<p>
        <ul>
            <li>Push events</lI>
            <li>Merge request events</lI>
        </ul>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Git Integration for Jira Data Center app now supports <b>GitLab System Hooks</b> (menu Admin Area ➜ System Hooks ➜ <i>Merge Request events</i>). However, it is only available for self-hosted GitLab instances. We highly recommend that Jira administrators should use this feature as it greatly reduces the amount of configuration time to setup webhooks.
    </div>
    </div>
</div>
<br>
<br>

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/try008fv53?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/try008fv53'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Before you can add a webhook to your favorite git repository, you need to enable it in the git repositories configuration page of your Jira Data Center/Server instance.
    </div>
    </div>
</div>
<br>

Configure webhook by logging in to your GitLab account:

1.  Select a repository.

    ![](/wp-content/uploads/gij-web-hooks-gitlab-settings-c.png)

<br>

2.  Go to the settings page by clicking **Setting** on the sidebar.

3.  Select **Webhooks**. The following page is displayed:

    ![](/wp-content/uploads/gij-web-hooks-gitlab-settings-add-c.png)

4.  Switch to your Jira instance and copy the Webhook URL by clicking the copy icon adjacent to the URL field.

    ![](/wp-content/uploads/gij-jira-server-git-webhooks-loc-pointer-list.png)

<br>

5.  Switch back to your GitLab session and paste the obtained **_Secret URL_** from the _Git Integration for Jira_ app ➜ **Webhooks** page into the **_Payload URL_** field.

6.  Select the _**Push events**_ as a triggering event option. This is the default option when creating a new webhook.

7.  Click **Add webhook** to save the new webhook settings.

<br>

### Merge Request Event Webhook

The Git Integration for Jira app supports GitLab merge request webhooks now.

You will need to enable two (2) event triggers in your GitLab webhooks configuration _(Repo ➜ Settings ➜ Integrations)_ for it to work properly. Select both "**Push events**" and "**Merge request events**" triggers as outlined above in step **5**.

![](/wp-content/uploads/gij-gitlab-merge-request-event-trigger-webhook.png)

<br>

## More related articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

[Adding webhooks for GitHub](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitHub-gij-self-managed)

**Adding webhooks for GitLab** (this page)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/adding-webhooks-for-gerrit-gij-self-managed)

