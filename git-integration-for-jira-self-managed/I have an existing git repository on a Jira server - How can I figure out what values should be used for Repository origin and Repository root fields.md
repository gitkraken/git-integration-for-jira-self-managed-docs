---

title: I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/2051145752>

* * *

1.  Change current directory to the folder where repository is located.
    
2.  Run `pwd`.
    
3.  Response should go to **Repository root** field.
    
4.  Run `git remote show origin`.
    
5.  Find origin URL in the command response.
    
6.  Set this value for **Repository origin** field.
    

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