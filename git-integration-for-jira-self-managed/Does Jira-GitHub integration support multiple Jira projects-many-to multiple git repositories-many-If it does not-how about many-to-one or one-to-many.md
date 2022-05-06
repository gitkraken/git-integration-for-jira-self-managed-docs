---

title: Does Jira+GitHub integration support multiple Jira projects (many) to multiple git repositories (many)? If it does not, how about many-to-one or one-to-many?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Does Jira+GitHub integration support multiple Jira projects (many) to multiple git repositories (many)? If it does not, how about many-to-one or one-to-many?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2040627549>

* * *

Yes — it does support repositories supporting many projects.  That said, the associations are made by the developers when they commit code to a specific issue key (which is part of a project). The permission that allows a user to see these commits in a Jira project is whether they have the "**View Development Tools**" permission for that project (that's a Jira setting).

The only project permissions that the Git Integration for Jira app has are for the Repository Browser (Git dropdown menu). To associate a repository with all Jira projects or only specific projects, see [Project permissions setting](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard##Settings) in the Connect to Git Repository wizard or [associating project permissions](/wiki/spaces/GIJDC/pages/1930397766/Associating+project+permissions) via Edit repository settings in the Git Repositories configuration page.

*   Page:
    
    [How do I let people browse Git securely but without defining Git IDs for everyone?](/wiki/spaces/GIJDC/pages/2042331224)
    
*   Page:
    
    [Does the Git Integration for Jira app have API commands that allow addition/removal of a Git project?](/wiki/spaces/GIJDC/pages/2040627498)
    
*   Page:
    
    [After upgrading Jira from 4.1.1 to 5.2.9, I get some errors "Folder ... FORNEOnlineSolver git doesn't exist". Where can I set the path correctly? Is there any properties file?](/wiki/spaces/GIJDC/pages/2042331241)
    
*   Page:
    
    [Does Jira+GitHub integration support multiple Jira projects (many) to multiple git repositories (many)? If it does not, how about many-to-one or one-to-many?](/wiki/spaces/GIJDC/pages/2040627549)
    
*   Page:
    
    [How do I connect to HTTPS repositories with self signed SSL certificates or other SSL issues?](/wiki/spaces/GIJDC/pages/2042331271)
    
*   Page:
    
    [I want to track all repositories hosted in my GitLab server from my Jira Data Center. How do I configure the required NFS access permissions?](/wiki/spaces/GIJDC/pages/2040660424)
    
*   Page:
    
    [How do I setup GitLab Server to respond to incoming network API calls?](/wiki/spaces/GIJDC/pages/2040627711)