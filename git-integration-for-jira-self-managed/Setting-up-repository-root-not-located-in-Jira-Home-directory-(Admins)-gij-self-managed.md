---

title: Setting up repository root not located in Jira Home directory (Admins)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
There are three possible ways to setup a repository root that is not located in the Jira home directory:

1.  Clone the repository outside of Jira then connect to it via Manage git repositories page ➜ Connect to Git Repository ➜ **Advanced Setup**.

2.  Clone the repository with the standard **Connect to Git Repository** wizard into the Jira home directory.  Soon afterwards, move the cloned repository and update the settings on the repository.

3.  You could symlink the `{$JIRA_HOME}/data/git-plugin` directory to a different volume. The standard **Connect to Git Repository** wizard will still write there, but the data will reside on the different volume. But be aware, that the Git Integration for Jira app treats anything in the `git-plugin` folder as a clone that it owns.

<br>
<br>

[**Prev:** Adding a repository hosted on Windows Servers or Windows Network Share \(Admins\)](/git-integration-for-jira-data-center/Adding-a-repository-hosted-on-Windows-Servers-or-Windows-Network-Share-(Admins)-gij-self-managed)

[**Next:** Reindex API to trigger indexing](/git-integration-for-jira-data-center/Reindex-API-to-trigger-indexing-gij-self-managed)


