---

title: Getting started for Git administrators
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/gij-docs-introduction-bbb-overview_708.png)

<br>

# Welcome Git Admin!

You are probably reading this page because a Jira administrator has requested access to the Git server. The Jira administrator has installed the Git Integration for Jira app.

* * *

## What is the Git Integration for Jira app?

The Git Integration for Jira app pulls data from a Git source code control repository. Jira users will be able to see code in Git in context with Jira projects and issues. Even non-technical users will be able to see Git in the familiar Jira interface.

Jira users will be able to securely browse content in Git without requiring you to create IDs for every user.

## How does Jira interact with the Git server?

The Git Integration for Jira app acts as a regular Git client. It performs a scheduled pull from the repository.

## What does the Jira administrator need?

The Jira administrator needs the ability to clone the repository and pull from it just like a regular developer workstation would do.

We recommend that you create a new user identity specifically for this Jira server.
<br>
<br>
* * *

### For Git repositories with HTTP\/HTTPS access

Please do the following:

1.  Create a new user for the Jira server.
2.  Send the Jira administrator:
    *   The URL to the Git server
    *   _For example:_  `https://gitserver/repo/timetrackingproject.git`
    *   The username and password for the user you created

### For Git repositories with SSH access

Please do the following:
1.  Define a new SSH public/private key pair for the Jira server
2.  Install the public key on the Git server
3.  Send the Jira administrator:
    *   The URL to the Git server
    *   _For example:_  `git@gitserver:repo/timetrackingproject.git`
    *   The private key you created

### For Git repositories with Git protocol access

Send the Jira administrator the URL to the Git server.<br>
For example: `git://gitserver/repo/timetrackingproject.git`

### For Git repositories on the same host as Jira

Send the Jira administrator the full path to the Git repository.<br>
For example: `/home/git/repo/timetrackingproject.git`

### For Git repositories across network file shares

If you have users access the Git repository over a network file share using Windows file sharing or NFS, the network share will need to be mounted on the Jira server. Assist the Jira administrator in mounting the network share. Then, provide the Jira administrator with the path to the Git repository over the network share.

Linux example: `/mnt/gitserver/home/git/repo/timetracking.git`<br>
Windows example: `\\gitserver\git\repo\timetracking.git`

### For Git repositories hosted on Windows servers

For cases when git repositories are hosted at Windows servers (Windows Server network drive) – while it is using the Windows server networking, the network credentials accessing the git repository must be the same as the user running Jira.

The repository setting for _**Enable Fetches**_ of the configured network path must be `Git Repository hosted on same server as Jira`.

### For Jira hosted on Windows

When using Active Directory accounts for repository access, changing the password of the AD account running Jira can cause repository authentication issues.

Restart Jira to regain access to repositories.

## Does the Git Integration for Jira app have API commands that allow addition/removal of a Git project?

Yes, the **REST API** for add, update, and delete repository is available. The documentation for this feature is available at [Git Integration for Jira: Hook and API Reference - Repository REST API](/git-integration-for-jira-data-center/repository-api-gij-self-managed).

## Troubleshooting issues

For information on troubleshooting known errors and issues, see [Git Integration for Jira - Knowledge Base/FAQ](/git-integration-for-jira-data-center/frequently-asked-questions-gij-self-managed) and [Troubleshooting guides](/git-integration-for-jira-data-center/troubleshooting-articles-gij-self-managed).
<br>
<br>
* * *
<br>

| **Get new product notifications and feature updates from BigBrassBand LLC.** |
|:---:|
| [Click here to subscribe to our mailing list](http://eepurl.com/hhfbwz) |

<br>
<div class="bbb-callout bbb--tip">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      Need to know more features?  Read next: <a href='https://bigbrassband.com/tips-for-jira-admins.html' target='_blank' alt='Opens in a new tab'>Helpful Tips for Jira Administrators</a>.
    </div>
  </div>
</div>
<br>
<br>

<hr>

<br>
<br>

[**Prev:** Managing license key](/git-integration-for-jira-data-center/managing-license-key-gij-self-managed)

[**Next:** Setup GitLab Server to respond to incoming network API calls](/git-integration-for-jira-data-center/setup-gitLab-server-to-respond-to-incoming-network-API-calls-gij-self-managed)

