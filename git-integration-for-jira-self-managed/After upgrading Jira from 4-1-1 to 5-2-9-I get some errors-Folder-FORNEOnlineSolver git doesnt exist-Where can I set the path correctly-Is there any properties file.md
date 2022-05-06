---

title: After upgrading Jira from 4.1.1 to 5.2.9, I get some errors "Folder ... FORNEOnlineSolver git doesn't exist". Where can I set the path correctly? Is there any properties file?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# After upgrading Jira from 4.1.1 to 5.2.9, I get some errors "Folder ... FORNEOnlineSolver git doesn't exist". Where can I set the path correctly? Is there any properties file?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2042331241>

* * *

Please visit Git Integration for Jira app config and check Git Repositories tab (_Jira dashboard menu **Git** ➜ **Manage repositories** ➜_ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _**Actions**_):

*   For integrations, go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Show integration repositories** ➜ click a repository to view the repository settings.
    
*   For repository connections, go to ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit repository settings**.
    

Check and verify the path to your configured repositories.

Also, an upgrade of Jira may lead to changing of user account used to run the service, which in turn, may result in lack of permissions.

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