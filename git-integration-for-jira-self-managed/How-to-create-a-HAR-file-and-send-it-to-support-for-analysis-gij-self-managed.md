---

title: How to create a HAR file and send it to support for analysis
description: Capture a HAR file in Google Chrome when an error appears and send it to GitKraken support for analysis.
product: Git Integration for Jira Data Center
feature: Support
content_type: how-to
audience: all
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [all]
version_required: all
status: GA
last_verified: 2023-03
llms_include: true
tags: [har file, chrome devtools, network tab, support, debugging]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "how-to-articles-gij-self-managed"
    nav_label: "How to create a HAR file and send it to support for analysis"
    nav_order: 30
    nav_parent: "how-to-articles-gij-self-managed"
    page_type: "content"
---

HAR (HTTP Archive) is basically a JSON file which is exported from a captured data used by several HTTP session tools. We use this file to analyze report data and debugging errors. This way, we may be able to reproduce your issue from our side. We ensure that all the data sent to us will only be used within our scope.

This guide covers related issue such as the unknown error example below:

<img src='/wp-content/uploads/gij-jira-instance-error-git-manager.png' style='margin:25px auto 40px auto;display:block;' />

## How to create a HAR file?

For generating the HAR file, we recommend to use Google Chrome. Make sure Chrome is updated to the latest version.

<img src='/wp-content/uploads/gij-browser-right-click-inspect.png' style='margin:25px auto;display:block;' />

1.  Right click on the blank area of the page with the error then click **Inspect** on the context menu. This will open the browser web tools.

2.  On the web tools UI, click on the **Network** tab.

    ![](/wp-content/uploads/gij-browser-dev-tools-network-tab.png)

3.  Reload the page to ensure that debug data is gathered from the very beginning.

4.  If the error screen persist, click on the **Export HAR** icon then save the file to an easily-accessible location. Alternatively, right click on the results list then click _**Save all as HAR with content**_ on the context menu.

    ![](/wp-content/uploads/gij-browser-dev-tools-network-tab-export-har.png)

5.  Send this file to [gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com) for analysis. If the file is larger than the email service attachment limit, you can use free Cloud storage services such as Google Drive, Dropbox etc. and share this link with our support team.


