---

title: Webhooks GitHub Organization Support
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The GitHub Organization webhooks is now supported.  Rather than creating a webhook for each repository manually, configure the webhook at the GitHub Organization level to automatically register webhook for each repository.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/171278716/gitserver-github-org-webhooks-cfg.png?version=1&modificationDate=1649573002925&cacheVersion=1&api=v2&width=680&height=434)

To configure GitHub organization webhook:

1.  Login to your GitHub account and go to your GitHub Organization.

2.  Go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Settings**.

3.  On the sidebar under _Code, planning, and automation_, go to **Webhooks**.

    *   On the Webhooks page, click **Add webhook**.

4.  Paste the webhook URL into the _**Payload URL**_ field. (The webhook URL is acquired from the Git Integration for Jira app webhook configuration page.)

5.  IMPORTANT For the **Content type**, choose **applications/json**.

6.  Enter the **Secret key** on the _**Secret**_ field.

7.  Set the webhook trigger to **Just the Push event**.

8.  Click **Add webhook** to complete this setup.


### More related topics about webhook configuration

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