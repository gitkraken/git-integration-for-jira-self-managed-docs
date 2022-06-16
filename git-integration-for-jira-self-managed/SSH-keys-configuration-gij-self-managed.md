---

title: SSH keys configuration
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
Manage and associate SSH keys to connected git repositories via the **SSH Keys** in Git Integration for Jira Server app repository configuration page.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396746/add-ssh-and-associate-keys.png?version=1&modificationDate=1630642804864&cacheVersion=1&api=v2&width=680&height=222)

The list of added private SSH keys is accessible on this page. Both types of SSH keys are displayed in this list. Legacy filesystem-based keys contain directory path in the _**Private key**_ column.

Refer to the following table for list column information:

| **Column** | **Description** |
| :--- | :--- |
| _**Name**_ | The name of the private SSH key will appear here. |
| _**Private key**_ | This is the private SSH key in hex mode. |
| _**Passphrase**_ | A lock icon is displayed if the SSH key pair has a passphrase. |
| _**Associations**_ | Lists the repositories that are associated with this SSH key. |
| _**Last Used By**_ | Lists the repositories that are using this SSH key. |
| _**Operations**_ | Click the icon to perform **Delete** or **Associations** functions. |

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        You cannot delete filesystem-based keys by using the Git Integration app configuration.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The SSH keys are also automatically added to this list when adding new repositories that require SSH keys.
    </div>
    </div>
</div>

