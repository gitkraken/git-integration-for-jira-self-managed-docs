---

title: Setup repository root not located in Jira Home directory
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Setup repository root not located in Jira Home directory

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397313/Setup+repository+root+not+located+in+Jira+Home+directory>

* * *

There are three possible ways to setup a repository root that is not located in the Jira home directory:

*   Clone the repository outside of Jira then connect to it via Connect to Git Repository ➜ **Advanced Setup**.
    
*   Clone the repository with the standard **Connect to Git Repository** wizard into the Jira home directory.  Soon afterwards, move the cloned repository and update the settings on the repository.
    
*   You could symlink the `{$Jira_HOME}/data/git-plugin` directory to a different volume. The standard **Connect to Git Repository** wizard will still write there, but the data will reside on the different volume. But be aware, that Git Integration app treats anything in the `git-plugin` folder as a clone that it owns.
    

[« Adding a repository hosted on Windows Server or Windows Network Share](/wiki/spaces/GIJDC/pages/1930397287/Adding+a+repository+hosted+on+Windows+Server+or+Windows+Network+share)

[Tracked folders overview »](/wiki/spaces/GIJDC/pages/1930397330/Tracked+folders+overview)

### More related topics about setting up repositories

*   Page:
    
    [Git integration configuration page](/wiki/spaces/GIJDC/pages/1930396951/Git+integration+configuration+page) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Using the Add new integration wizard](/wiki/spaces/GIJDC/pages/1930397044/Using+the+Add+new+integration+wizard) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Using the Connect Repository wizard](/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Connecting a repository via Advanced setup](/wiki/spaces/GIJDC/pages/1930397180/Connecting+a+repository+via+Advanced+setup) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Adding a repository hosted on Windows Server or Windows Network share](/wiki/spaces/GIJDC/pages/1930397287/Adding+a+repository+hosted+on+Windows+Server+or+Windows+Network+share) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setup repository root not located in Jira Home directory](/wiki/spaces/GIJDC/pages/1930397313/Setup+repository+root+not+located+in+Jira+Home+directory) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Tracked folders overview](/wiki/spaces/GIJDC/pages/1930397330/Tracked+folders+overview) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Self-signed HTTPS integration](/wiki/spaces/GIJDC/pages/1930397349/Self-signed+HTTPS+integration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Managing repository or integration configuration](/wiki/spaces/GIJDC/pages/1930397435/Managing+repository+or+integration+configuration) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Associating project permissions](/wiki/spaces/GIJDC/pages/1930397766/Associating+project+permissions) (Git Integration for Jira Data Center)