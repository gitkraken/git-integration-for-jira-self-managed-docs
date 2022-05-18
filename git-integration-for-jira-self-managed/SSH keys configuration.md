---

title: SSH keys configuration
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Manage and associate SSH keys to connected git repositories via the **SSH Keys** in Git Integration for Jira Server app repository configuration page.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396746/add-ssh-and-associate-keys.png?version=1&modificationDate=1630642804864&cacheVersion=1&api=v2&width=680&height=222)

The list of added private SSH keys is accessible on this page. Both types of SSH keys are displayed in this list.  Legacy filesystem-based keys contain directory path in the _**Private key**_ column.

Refer to the following table for list column information:

|     |     |
| --- | --- |
| **Column** | **Description** |
| _**Name**_ | The name of the private SSH key will appear here. |
| _**Private key**_ | This is the private SSH key in hex mode. |
| _**Passphrase**_ | A lock icon is displayed if the SSH key pair has a passphrase. |
| _**Associations**_ | Lists the repositories that are associated with this SSH key. |
| _**Last Used By**_ | Lists the repositories that are using this SSH key. |
| _**Operations**_ | Click the icon to perform **Delete** or **Associations** functions. |

You cannot delete filesystem-based keys by using the Git Integration app configuration.

The SSH keys are also automatically added to this list when adding new repositories that require SSH keys.

[« Adding a public SSH key](/wiki/spaces/GIJDC/pages/1930396728/Adding+a+public+SSH+Key)

[Adding and associating SSH keys »](/wiki/spaces/GIJDC/pages/1930396771/Adding+and+associating+SSH+keys)

### More related topics about SSH integration

*   Page:

    [Working with SSH keys](/wiki/spaces/GIJDC/pages/1930396577/Working+with+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Generating SSH keys](/wiki/spaces/GIJDC/pages/1930396609/Generating+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Adding a private SSH key](/wiki/spaces/GIJDC/pages/1930396698/Adding+a+private+SSH+key) (Git Integration for Jira Data Center)

*   Page:

    [Adding a public SSH Key](/wiki/spaces/GIJDC/pages/1930396728/Adding+a+public+SSH+Key) (Git Integration for Jira Data Center)

*   Page:

    [SSH keys configuration](/wiki/spaces/GIJDC/pages/1930396746/SSH+keys+configuration) (Git Integration for Jira Data Center)

*   Page:

    [Adding and associating SSH keys](/wiki/spaces/GIJDC/pages/1930396771/Adding+and+associating+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Removing SSH keys](/wiki/spaces/GIJDC/pages/1930396835/Removing+SSH+keys) (Git Integration for Jira Data Center)

*   Page:

    [Reconfigure Git repositories and SSH keys](/wiki/spaces/GIJDC/pages/1930396868/Reconfigure+Git+repositories+and+SSH+keys) (Git Integration for Jira Data Center)