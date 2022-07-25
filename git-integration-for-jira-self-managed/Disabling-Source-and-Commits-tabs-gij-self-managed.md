---

title: Disabling Source and Commits tabs
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The **Source** tab is part of the FishEye Plugin and is used for integration with SVN.  The **Commits** tab is part of the Jira DVCS Connector Plugin and is used for integration with gits _(Git, Mercurial, BitBucket etc.)_.

Atlassian enables these tabs by default.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If either <b>FishEye</b> or <b>Jira DVCS Connector</b> plugin is not installed, the <b>Source</b> or <b>Commits</b> tab will not be visible on the <b>Issues</b> page.
    </div>
    </div>
</div>
<br>

## Hiding the Source tab

To hide the **Source** tab from the **Issues** page, disable the **FishEye Plugin**:

1.  On your Jira dashboard, go to Jira Administration ➜ **Manage Apps**.

2.  Find and click **FishEye Plugin** under the installed add-ons to expand its options.

3.  Click **Disable**.


## Hiding the Commits tab

To hide the **Commits** tab from the **Issues** page, disable the **Jira DVCS Connector Plugin**:

1.  On your Jira dashboard, go to Jira Administration ➜ **Manage Apps**.

2.  Find and click **Jira DVCS Connector Plugin** under the installed add-ons to expand its options.

3.  Click **Disable**.

