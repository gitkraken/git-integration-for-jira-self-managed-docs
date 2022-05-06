---

title: How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


# How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2052128856>

* * *

There are three possible ways to do this:

*   Clone the repository outside of Jira then connect to it via **Connect to Git Repository** ➜ **Advanced Setup**.
    
*   Clone the repository with the standard **Connect to Git Repository Wizard** into the Jira home directory.  Soon afterwards, move the cloned repository and update the settings on the repository.
    
*   You could symlink the `{$Jira_HOME}/data/git-plugin` directory to a different volume.  The standard **Connect to Git Repository Wizard** will still write there, but the data will reside on the different volume. But be aware, that the Git Integration for Jira app treats anything in the Git-Plugin folder as a clone that it owns.
    

*   Page:
    
    [I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?](/wiki/spaces/GIJDC/pages/2051145752)
    
*   Page:
    
    [Can the app be configured to handle or scan multiple keys for one project? How is this supposed to work?](/wiki/spaces/GIJDC/pages/2052128838)
    
*   Page:
    
    [Where is the location of the local git repository?](/wiki/spaces/GIJDC/pages/2051080265)
    
*   Page:
    
    [How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?](/wiki/spaces/GIJDC/pages/2052128856)
    
*   Page:
    
    [I get the following error: "Host or port specified in <git\_repository\_url> are inaccessible". Do I also need a git instance on the Jira server?](/wiki/spaces/GIJDC/pages/2051375166)
    
*   Page:
    
    [We use GitBlit without SSH keys and use only HTTPS instead. Does Git Integration for Jira app support this?](/wiki/spaces/GIJDC/pages/2051440710)
    
*   Page:
    
    [I am using Jira which is hosted on Windows. I changed the password of the Active Directory account running Jira. Now, I cannot access my repository. Why?](/wiki/spaces/GIJDC/pages/2051768359)