---

title: Adding Webhooks for GitHub
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Pull request webhooks are now supported. See details on this page.

Supported webhook events:

*   Pushes event

*   Pull request events


_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/4fbw471kgh) _to open this video in a new browser tab for more viewing options._

Before you can proceed with the steps outlined on this guide, webhooks must be enabled in the Git Integration for Jira app repository configuration for your Jira instance. For more details, see [Webhooks - Getting Started](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/92013207/Webhooks#Getting-started).


Configure webhook by logging in to your GitHub account:

1.  Select a repository.

2.  ![](https://bigbrassband.atlassian.net/wiki/download/attachments/171377121/gitserver-webhook-github-add-webhook-steps-2-4(c).png?version=1&modificationDate=1649573919702&cacheVersion=1&api=v2)

    Go to the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Settings** page.

3.  On the sidebar under _Code and information_, click **Webhooks**.

4.  Click **Add webhook**. The following page is displayed:

5.  ![](https://bigbrassband.atlassian.net/wiki/download/attachments/171377121/gitserver-webhook-add-webhook-github-steps.png?version=1&modificationDate=1649573257610&cacheVersion=1&api=v2)

    Paste the obtained _**Secret URL**_ from the _Git Integration for Jira_ app ➜ **Webhooks** page into the _**Payload URL**_ field.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/171377121/jira-server-git-webhooks-loc-pointer-list.png?version=1&modificationDate=1649573257614&cacheVersion=1&api=v2)
6.  For the _**Content type**_, choose **application/json**. IMPORTANT

7.  Select the _**Just the push event**_ option as triggering event. This is the default option when creating a new webhook.

8.  Click **Add webhook** to save the new webhook settings.


## Pull request event webhook

The Git Integration for Jira app supports GitHub pull request webhooks now.

You will need to enable two (2) event triggers in your GitHub webhooks configuration _(Repo ➜ Settings ➜ Webhooks)_ for it to work properly. Under event triggers section, choose _**Let me select individual events**_ and then select both "**Pushes**" and "**Pull request**" triggers instead as outlined above in step **6**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/171377121/github-pull-request-event-trigger-webhook.png?version=2&modificationDate=1649573257621&cacheVersion=1&api=v2&width=676&height=334)

For the figure above:

*   **Just the** `push` event - This is the default configuration and this works only for commits.

*   **Send me** `everything` - This would send commits/pull requests events but is very verbose. We don't recommend this configuration.

*   **Let me select individual events (**`Pushes`/`Pull requests`) - This would work better than the second option and we recommend this configuration.


Webhooks will be automatically registered for each GitHub repository connected to Jira Server to instantly index your commits. For this to work, the connecting GitHub user must be the Organization Owner or have repository **ADMIN** rights.

Webhooks will be deleted when GitHub integration is disconnected from Git Integration for Jira Server.

Git Integration for Jira will index only the updated repositories as indicated by the GitHub organization or GitLab group webhook.

### More related topics about configuring webhooks

*   Page:

    [Creating reindex triggers for a single repository](/wiki/spaces/GIJDC/pages/171475191/Creating+reindex+triggers+for+a+single+repository) (Git Integration for Jira Data Center)

*   Page:

    [Adding Webhooks for GitHub](/wiki/spaces/GIJDC/pages/171377121/Adding+Webhooks+for+GitHub) (Git Integration for Jira Data Center)

*   Page:

    [Adding Webhooks for GitLab](/wiki/spaces/GIJDC/pages/171213219/Adding+Webhooks+for+GitLab) (Git Integration for Jira Data Center)

*   Page:

    [Webhooks GitHub Organization Support](/wiki/spaces/GIJDC/pages/171278716/Webhooks+GitHub+Organization+Support) (Git Integration for Jira Data Center)

*   Page:

    [Adding Webhooks for Azure DevOps Repos | VSTS](/wiki/spaces/GIJDC/pages/171999302/Adding+Webhooks+for+Azure+DevOps+Repos+%7C+VSTS) (Git Integration for Jira Data Center)

*   Page:

    [Adding Webhooks for Azure DevOps Server | TFS](/wiki/spaces/GIJDC/pages/235274262/Adding+Webhooks+for+Azure+DevOps+Server+%7C+TFS) (Git Integration for Jira Data Center)

*   Page:

    [Adding Webhooks for Bitbucket](/wiki/spaces/GIJDC/pages/498663799/Adding+Webhooks+for+Bitbucket) (Git Integration for Jira Data Center)

*   Page:

    [Adding webhooks for Gerrit](/wiki/spaces/GIJDC/pages/1509032414/Adding+webhooks+for+Gerrit) (Git Integration for Jira Data Center)