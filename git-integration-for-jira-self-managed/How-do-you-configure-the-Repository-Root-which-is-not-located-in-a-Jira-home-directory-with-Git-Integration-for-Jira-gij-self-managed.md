---

title: How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


There are three possible ways to do this:

*   Clone the repository outside of Jira then connect to it via **Connect to Git Repository** ➜ **Advanced Setup**.
    
*   Clone the repository with the standard **Connect to Git Repository Wizard** into the Jira home directory.  Soon afterwards, move the cloned repository and update the settings on the repository.
    
*   You could symlink the `{$Jira_HOME}/data/git-plugin` directory to a different volume.  The standard **Connect to Git Repository Wizard** will still write there, but the data will reside on the different volume. But be aware, that the Git Integration for Jira app treats anything in the Git-Plugin folder as a clone that it owns.
    