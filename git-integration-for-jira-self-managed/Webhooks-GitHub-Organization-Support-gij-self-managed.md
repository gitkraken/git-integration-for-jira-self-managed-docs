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

2.  Go to **Settings**.

3.  On the sidebar under _Code, planning, and automation_, go to **Webhooks**.

    *   On the Webhooks page, click **Add webhook**.

4.  Paste the webhook URL into the _**Payload URL**_ field. (The webhook URL is acquired from the Git Integration for Jira app webhook configuration page.)

5.  IMPORTANT For the **Content type**, choose **applications/json**.

6.  Enter the **Secret key** on the _**Secret**_ field.

7.  Set the webhook trigger to **Just the Push event**.

8.  Click **Add webhook** to complete this setup.


