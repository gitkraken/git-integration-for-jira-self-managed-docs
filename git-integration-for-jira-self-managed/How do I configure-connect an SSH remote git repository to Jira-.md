---

title: How do I configure/connect an SSH remote git repository to Jira?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# How do I configure/connect an SSH remote git repository to Jira?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2041708556>

* * *

In Jira, use the **Connect to Git Repository** wizard to configure SSH integration with any remote git repositories.

1.  Go to Jira dashboard menu **Git** ➜ **Manage repositories**. _(Alternatively, go to Jira Dashboard menu_ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Jira Administration ➜ Applications)._ The manage git repositories page is displayed.
    
2.  Click **Connect to Git Repository**. The **Connect to Git Repository** wizard appears.
    
3.  Enter the **Repository location** of your SSH git server. Click **Next**.
    
4.  Upload the private key or paste it on the provided field. Click **Next**.
    
5.  Enter **Passphrase** (if the SSH has one). Click **Next**.
    
6.  The wizard will start cloning the selected repository. When the process is complete, the Permissions dialog is displayed.
    
7.  Leave settings as is and click **Next**.
    
8.  Click **Finish** to complete the setup. The repository is added to the repositories list.
    

Here's a video to guide you step-by-step as stated above:

_Watch how to add an SSH Git repository. Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/qmumdo048n) _to open this video_  
_in a new browser tab for more viewing options._

*   Page:
    
    [Creating and configuring SSH keys (Windows/MacOS/Linux)](/wiki/spaces/GIJDC/pages/183271450)
    
*   Page:
    
    [Are passphrases supported on SSH keys?](/wiki/spaces/GIJDC/pages/2040692788)
    
*   Page:
    
    [Does this app support authenticating to git repositories via SSH?](/wiki/spaces/GIJDC/pages/2041184292)
    
*   Page:
    
    [How do you configure the SSH key used when adding a new project?](/wiki/spaces/GIJDC/pages/2041020434)
    
*   Page:
    
    [Why do I need to provide a PRIVATE KEY to the Git Integration for Jira app instead of a PUBLIC KEY?](/wiki/spaces/GIJDC/pages/2041577508)
    
*   Page:
    
    [How do I configure/connect an SSH remote git repository to Jira?](/wiki/spaces/GIJDC/pages/2041708556)