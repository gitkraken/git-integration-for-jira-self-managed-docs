---

title: Getting started for Git administrators
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396073/bbb-overview.png?version=1&modificationDate=1630642781821&cacheVersion=1&api=v2)

# Welcome Git Admin!

You are probably reading this page because a Jira administrator has requested access to the Git server. The Jira administrator has installed the Git Integration for Jira app.

**What’s on this page:**

* * *

## What is the Git Integration for Jira app?

The Git Integration for Jira app pulls data from a Git source code control repository. Jira users will be able to see code in Git in context with Jira projects and issues. Even non-technical users will be able to see Git in the familiar Jira interface.

Jira users will be able to securely browse content in Git without requiring you to create IDs for every user.

## How does Jira interact with the Git server?

The Git Integration for Jira app acts as a regular Git client. It performs a scheduled pull from the repository.

## What does the Jira administrator need?

The Jira administrator needs the ability to clone the repository and pull from it just like a regular developer workstation would do.

We recommend that you create a new user identity specifically for this Jira server.

|     |
| --- |
| ### For Git repositories with HTTP/HTTPS access |
| Please do the following:<br><br>1.  Create a new user for the Jira server.<br>    <br>2.  Send the Jira administrator:<br>    <br><br>*   The URL to the Git server<br>    <br>*   _For example:_  `https://gitserver/repo/timetrackingproject.git`<br>    <br>*   The username and password for the user you created |

|     |
| --- |
| ### For Git repositories with SSH access |
| Please do the following:<br><br>1.  Define a new SSH public/private key pair for the Jira server<br>    <br>2.  Install the public key on the Git server<br>    <br>3.  Send the Jira administrator:<br>    <br><br>*   The URL to the Git server<br>    <br>*   _For example:_  `git@gitserver:repo/timetrackingproject.git`<br>    <br>*   The private key you created |

|     |
| --- |
| ### For Git repositories with Git protocol access |
| Send the Jira administrator the URL to the Git server.<br><br>For example:  `git://gitserver/repo/timetrackingproject.git` |

|     |
| --- |
| ### For Git repositories on the same host as Jira |
| Send the Jira administrator the full path to the Git repository.<br><br>For example:  `/home/git/repo/timetrackingproject.git` |

|     |
| --- |
| ### For Git repositories across network file shares |
| If you have users access the Git repository over a network file share using Windows file sharing or NFS, the network share will need to be mounted on the Jira server. Assist the Jira administrator in mounting the network share. Then, provide the Jira administrator with the path to the Git repository over the network share.<br><br>Linux example: `/mnt/gitserver/home/git/repo/timetracking.git`<br><br>Windows example: `\\gitserver\git\repo\timetracking.git` |

|     |
| --- |
| ### For Git repositories hosted on Windows servers |
| For cases when git repositories are hosted at Windows servers (Windows Server network drive) – while it is using the Windows server networking, the network credentials accessing the git repository must be the same as the user running Jira.<br><br>The repository setting for _**Enable Fetches**_ of the configured network path must be `Git Repository hosted on same server as Jira`. |

|     |
| --- |
| ### For Jira hosted on Windows |
| When using Active Directory accounts for repository access, changing the password of the AD account running Jira can cause repository authentication issues.<br><br>Restart Jira to regain access to repositories. |

## Does the Git Integration for Jira app have API commands that allow addition/removal of a Git project?

Yes. As of **v2.8.3+** of the Git Integration for Jira app, the **REST API** for add, update, and delete repository is implemented. The documentation for this feature is available at [Git Integration for Jira: Hook and API Reference - Repository REST API](/git-integration-for-jira-self-managed/Repository-API).

## Troubleshooting issues

For information on troubleshooting known errors and issues, see [Git Integration for Jira - Knowledge Base/FAQ](/wiki/spaces/GIJDC/pages/92176390/Frequently+Asked+Questions) and [Troubleshooting guides](https://bigbrassband.atlassian.net/wiki/spaces/DEVINFO/pages/146538616/Troubleshooting+articles).

[« Managing license key](/wiki/spaces/GIJDC/pages/1930396028/Managing+license+key)

[Setup GitLab Server to respond to incoming network API calls »](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls)

## More related topics about getting started for Jira admins

*   Page:

    [Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls) (Git Integration for Jira Data Center)

*   Page:

    [New GitLab v10+ authentication](/wiki/spaces/GIJDC/pages/1930396211) (Git Integration for Jira Data Center)

*   Page:

    [General settings: Improving Jira performance](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance) (Git Integration for Jira Data Center)

*   Page:

    [Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/wiki/spaces/GIJDC/pages/1930396287) (Git Integration for Jira Data Center)

*   Page:

    [Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317) (Git Integration for Jira Data Center)

*   Page:

    [Recommended reindex interval setting](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting) (Git Integration for Jira Data Center)

*   Page:

    [Reindex API to trigger indexing](/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing) (Git Integration for Jira Data Center)

*   Page:

    [Setting up web linking](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking) (Git Integration for Jira Data Center)

*   Page:

    [Setting up webhooks](/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks) (Git Integration for Jira Data Center)

*   Page:

    [Increasing timeout threshold for large repositories while doing a Git pull](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull) (Git Integration for Jira Data Center)

*   Page:

    [Working with Tracked folders](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders) (Git Integration for Jira Data Center)

*   Page:

    [Recommended upgrade method for Git Integration for Jira](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira) (Git Integration for Jira Data Center)

*   Page:

    [Discard cloned files in Jira Home directory (General setting)](/wiki/spaces/GIJDC/pages/1930396547) (Git Integration for Jira Data Center)


* * *

|     |
| --- |
| **Get new product notifications and feature updates from BigBrassBand LLC.** |
| [Click here to subscribe to our mailing list](http://eepurl.com/hhfbwz) |

Need to know more features?  Read next:  [Helpful Tips for Jira Administrators](https://bigbrassband.com/tips-for-jira-admins.html)