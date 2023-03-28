---

title: Adding Webhooks for GitHub
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
        Pull request webhooks are now supported. See <a href='#pull-request-webhooks'>details</a> on this page.<div class='nextpara'>Supported webhook events:</div>
        <ul>
            <li>Pushes event</li>
            <li>Pull request events</li>
        </ul>
    </div>
    </div>
</div>
<br>

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/4fbw471kgh?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style=margin-top:10px>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/4fbw471kgh'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see <a href='/git-integration-for-jira-data-center/webhooks-gij-self-managed'>Webhooks - Getting Started</a>.
    </div>
    </div>
</div>
<br>

Configure webhook by logging in to your GitHub account:

1.  Select a repository.

    ![](/wp-content/uploads/gij-gitserver-webhook-github-add-webhook-steps-2-4-c.png)

2.  Go to the **Settings** page.

3.  On the sidebar under _Code and information_, click **Webhooks**.

4.  Click **Add webhook**. The following page is displayed:

    ![](/wp-content/uploads/gij-gitserver-webhook-add-webhook-github-steps.png)

    *   Paste the obtained _**Secret URL**_ from the _Git Integration for Jira_ app ➜ **Webhooks** page into the _**Payload URL**_ field.

    ![](/wp-content/uploads/gij-jira-server-git-webhooks-loc-pointer-list.png)

6.  For the _**Content type**_, choose **application/json**. IMPORTANT

7.  Select the _**Just the push event**_ option as triggering event. This is the default option when creating a new webhook.

8.  Click **Add webhook** to save the new webhook settings.


## Pull request event webhook

The Git Integration for Jira app supports GitHub pull request webhooks now.

You will need to enable two (2) event triggers in your GitHub webhooks configuration _(Repo ➜ Settings ➜ Webhooks)_ for it to work properly. Under event triggers section, choose _**Let me select individual events**_ and then select both "**Pushes**" and "**Pull request**" triggers instead as outlined above in step **6**.

![](/wp-content/uploads/gij-github-pull-request-event-trigger-webhook.png)

<br>

For the figure above:

*   **Just the** `push` event - This is the default configuration and this works only for commits.

*   **Send me** `everything` - This would send commits/pull requests events but is very verbose. We don't recommend this configuration.

*   **Let me select individual events (**`Pushes`/`Pull requests`) - This would work better than the second option and we recommend this configuration.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Webhooks will be automatically registered for each GitHub repository connected to Jira Server to instantly index your commits. For this to work, the connecting GitHub user must be the Organization Owner or have repository <b>ADMIN</b> rights.
        <p style='margin-bottom: 0px !important'>Webhooks will be deleted when GitHub integration is disconnected from Git Integration for Jira Server.</p>
    </div>
    </div>
</div>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Git Integration for Jira will index only the updated repositories as indicated by the GitHub organization or GitLab group webhook.
    </div>
    </div>
</div>

## More related articles about webhooks setup

[Creating reindex triggers for a single repository](/git-integration-for-jira-data-center/Creating-reindex-triggers-for-a-single-repository-gij-self-managed)

**Adding webhooks for GitHub** (this page)

[Adding webhooks for GitLab](/git-integration-for-jira-data-center/Adding-Webhooks-for-GitLab-gij-self-managed)

[Webhooks GitHub Organization support](/git-integration-for-jira-data-center/Webhooks-GitHub-Organization-Support-gij-self-managed)

[Adding webhooks for Azure DevOps Repos \| VSTS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Repos-VSTS-gij-self-managed)

[Adding webhooks for Azure DevOps Server \| TFS](/git-integration-for-jira-data-center/Adding-Webhooks-for-Azure-DevOps-Server-TFS-gij-self-managed)

[Adding webhooks for Bitbucket](/git-integration-for-jira-data-center/Adding-Webhooks-for-Bitbucket-gij-self-managed)

[Adding webhooks for Gerrit](/git-integration-for-jira-data-center/adding-webhooks-for-gerrit-gij-self-managed)

