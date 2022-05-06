---

title: How do I let people browse Git securely but without defining Git IDs for everyone?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# How do I let people browse Git securely but without defining Git IDs for everyone?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2042331224>

* * *

With the Git Integration for Jira app, you only need to define a single ID for the Jira server.  Jira then lets authorized Jira users browse Git.

You can restrict access to the Repository Browser _(views git list/repo folders in Jira)_ for the selected repository by associating the project permissions. On Jira, the **View Development Tools** permission must be granted to Users / Group / Project Roles.

Configure this setting via:

*   Jira dashboard menu:
    
    *   Git ➜ **Manage repositories**
        
    *   ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ Edit integration/repository settings ➜ **Project Permissions**
        
    *   Unmark the _**All Projects**_ checkbox and set one or two projects.
        
*   Connect Wizard:
    
    *   On the Integration Settings screen ➜ **Project Permissions**.
        
    *   Unmark the _**All Projects**_ checkbox and set one or two projects.
        

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