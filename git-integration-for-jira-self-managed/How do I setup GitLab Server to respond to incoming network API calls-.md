---

title: How do I setup GitLab Server to respond to incoming network API calls?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# How do I setup GitLab Server to respond to incoming network API calls?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2040627711>

* * *

In order for GitLab to display correct repository clone links to your users it needs to know the URL under which it is reached by your users (e.g. `http://gitlab.example.com/`)

To reconfigure:

1.  Access the GitLab configuration file in `/etc/gitlab/gitlab.rb`. 
    
    ```java
    sudo vi /etc/gitlab/gitlab.rb
    ```
    
2.  Change the `external_url` value to your GitLab server URL. 
    
    ```java
    external_url "http://gitlab.example.com" #this is the default URL
    external_url "http://X.X.X.X.local/" #change it to your GitLab Server URL
    ```
    
3.  Run the **reconfigure** command to make the change take effect. 
    
    ```java
    sudo gitlab-ctl reconfigure
    ```
    

  
Read this [**GitLab documentation**](https://docs.gitlab.com/omnibus/settings/configuration.html#configuring-the-external-url-for-gitlab) to know more about configuring the external URL for GitLab.

You should be able to add the GitLab repositories via Git Integration for Jira app ➜ **Connect to Git Repository** / **Add New integration**.

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