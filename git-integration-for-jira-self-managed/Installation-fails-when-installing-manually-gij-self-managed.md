---

title: Installation fails when installing manually
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
## Problem

Git Integration for Jira application installation fails when using the file upload install method.

## Diagnosis

*   Jira admins will see the installation screen in the Universal Plugin Manager (UPM) a message similar to the one below when installing the Git Integration for Jira app via the [file upload](https://confluence.atlassian.com/upm/installing-marketplace-apps-273875715.html#InstallingMarketplaceapps-Installingbyfileupload) method.
*   The "Installing" dialog hangs indefinitely.
*   The error message: "An unexpected error occurred. Refer to the logs for more information." is shown behind the dialog.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/167247873/capture.PNG?version=1&modificationDate=1567569013701&cacheVersion=1&api=v2&width=942&height=249)

## Cause

The Jira system is behind a type of proxy, firewall or network security and the network security/proxy has a limitation on request size.

## Solutions

See the following articles from Atlassian on a resolution:

*   [Updating add-ons by file upload hangs using UPM](https://confluence.atlassian.com/stashkb/updating-add-ons-by-file-upload-hangs-using-upm-660735049.html)
*   [Attaching a File Results in Request Entity Too Large](https://confluence.atlassian.com/jirakb/attaching-a-file-results-in-request-entity-too-large-320602682.html)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://bigbrassband.atlassian.net/servicedesk/customer/portals'>Support Desk</a> or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com)
    </div>
    </div>
</div>

