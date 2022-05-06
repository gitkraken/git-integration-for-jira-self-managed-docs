---

title: Adding and associating SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Adding and associating SSH keys

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930396771/Adding+and+associating+SSH+keys>

* * *

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/0a1exzdgpc) _to open this video in a new browser tab for more viewing options._

  
Limit the usage of the SSH key by associating them to selected repositories. Strictly map SSH keys to repositories via SSH Actions menu.

1.  On the SSH Keys page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Associations** for the selected SSH key.
    
2.  The following screen is displayed:
    
3.  ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396771/gitserver-assoc-ssh-keys(c).png?version=1&modificationDate=1630642805980&cacheVersion=1&api=v2)
    
    Mark the required repository or repositories to associate the SSH key.
    
4.  Clicking the **Select All** text label marks all repositories that will be associated to this SSH key.
    
5.  Clicking the **Select None** text label deselects all repositories.
    
6.  Click **Save** to save the settings.  
    

If an SSH key is strictly associated with some repository, that SSH key is an associated key.

## Associating SSH keys for multiple repositories

If you have multiple repositories that uses the same SSH key, configure them via Git Integration app by doing the following steps:

1.  Configure a repository that requires an SSH key via [Using the Connect Repository wizard](/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard).
    
2.  Associate that SSH key with the currently configured repository via Manage git repositories ➜ **SSH keys** (sidebar).
    
3.  Add another repository that requires the same SSH key. You will be presented with the following screen:
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396771/connect-ssh-gitlab-repo(c).png?version=1&modificationDate=1630642806469&cacheVersion=1&api=v2&width=646&height=450)
4.  Select the SSH key that you have associated to the previously added repository from the **Existing key** list.
    
5.  Click **Next** to continue. Complete the wizard and add another repository as desired.
    

For third-party products or services (such as GitHub, GitLab, Bitbucket, etc.), register the PUBLIC KEY for target repository or in profile settings of your git account.

## Associating SSH for custom git servers

For custom git hosting servers, ask your administrator to check that the target keypair's PUBLIC KEY is added into the `authorized_keys` file of the git server.

For more information, see the following article [**Setting up Git on the Server**](https://git-scm.com/book/it/v2/Git-on-the-Server-Setting-Up-the-Server).

[« SSH keys configuration](/wiki/spaces/GIJDC/pages/1930396746/SSH+keys+configuration)

[Removing SSH keys »](/wiki/spaces/GIJDC/pages/1930396835/Removing+SSH+keys)

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