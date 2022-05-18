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



Contact Us

If you still have a question - reach out to our [Support Desk](https://bigbrassband.atlassian.net/servicedesk/customer/portals) or email us at [support@bigbrassband.com](mailto:support@bigbrassband.com)

## Related articles

*   Page:

    [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/wiki/spaces/GIJDC/pages/873332786/Avoid+OutOfMemory+exceptions+by+configuring+or+memory+allocation+with+Jira+to+accommodate+large+repositories)

*   Page:

    [SQLException 'Incorrect string value' in merge requests](/wiki/spaces/GIJDC/pages/843448333/SQLException+%27Incorrect+string+value%27+in+merge+requests)

*   Page:

    ["Dangerous use of multiple connections" error on local database](/wiki/spaces/GIJDC/pages/821919745)

*   Page:

    ["Service proxy has been destroyed" exceptions in log](/wiki/spaces/GIJDC/pages/458883074)

*   Page:

    [Indexing error - Too many open files](/wiki/spaces/GIJDC/pages/318013497/Indexing+error+-+Too+many+open+files)