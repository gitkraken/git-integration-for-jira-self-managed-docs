---

title: I get the following error - "Host or port specified in are inaccessible". Do I also need a git instance on the Jira server?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


If your Jira and Git servers are running through a firewall, configure the firewall to allow access using the URL schemes for git repositories.  For authentication issues, make sure to check first the correct port for its connection.

Below are the default ports for common git URL protocols:

| **Protocol** | **Default port** |
| --- | --- |
| ssh:// | 22  |
| git:// | 9418 |
| http:// | 80  |
| https:// | 443 |

  
Test git connection and repository URL by doing the following:

1.  Install git client (or run `sudo apt-get install git`)
    
2.  Place your ssh key into `~/.ssh`
    
3.  Clone the repository (or run `git clone <your_repository_url>`)
    

The Git Integration for Jira app will run successfully if the above connection test ran without errors.
