---

title: Reconfigure Git repositories and SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Reconfigure Git repositories and SSH keys

<https://bigbrassband.atlassian.net/spaces/GIJDC/pages/1930396868/Reconfigure+Git+repositories+and+SSH+keys>

* * *

Perform the following steps to reconfigure repositories and SSH key:

1.  Remove any old SSH keys configured with the Git Integration app via `<JiraHOSTNAME> /secure/ViewSshKeys.jspa` (_Git Integration for Jira sidebar_ ➜ SSH keys).
    
2.  Restart Jira.
    
3.  Get the private key file from your Jira server to your Windows workstation: `/home/jira/.ssh/id_rsa`
    
4.  [Open the Connect wizard](/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard), use the repository location (git clone URL) and then upload the private key stated above.
    

* * *

For multiple repository configuration, see [Bulk change](/wiki/spaces/GIJDC/pages/1930397801/Bulk+change).

[« Removing SSH keys](/wiki/spaces/GIJDC/pages/1930396835/Removing+SSH+keys)

[Git URL ports »](/wiki/spaces/GIJDC/pages/1930396890/Git+URL+ports)

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