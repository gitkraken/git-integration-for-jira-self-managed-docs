---

title: Disabling Source and Commits tabs
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The **Source** tab is part of the FishEye Plugin and is used for integration with SVN.  The **Commits**tab is part of the Jira DVCS Connector Plugin and is used for integration with gits _(Git, Mercurial, BitBucket etc.)_.

Atlassian enables these tabs by default.

If either **FishEye** or **Jira DVCS Connector** plugin is not installed, the **Source** or **Commits** tab will not be visible on the **Issues** page.

## Hiding the Source tab

To hide the **Source** tab from the **Issues** page, disable the **FishEye Plugin**:

1.  On your Jira dashboard, go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ **Manage Apps**.

2.  Find and click **FishEye Plugin** under the installed add-ons to expand its options.

3.  Click **Disable**.


## Hiding the Commits tab

To hide the **Commits** tab from the **Issues** page, disable the **Jira DVCS Connector Plugin**:

1.  On your Jira dashboard, go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ **Manage Apps**.

2.  Find and click **Jira DVCS Connector Plugin** under the installed add-ons to expand its options.

3.  Click **Disable**.


[« Web linking](/wiki/spaces/GIJDC/pages/1930398212/Web+linking)

[Linking git commits to Jira issues »](/wiki/spaces/GIJDC/pages/1930398265/Linking+git+commits+to+Jira+issues)