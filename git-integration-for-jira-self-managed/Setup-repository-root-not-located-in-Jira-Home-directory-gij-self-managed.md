---

title: Setup repository root not located in Jira Home directory
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

There are three possible ways to setup a repository root that is not located in the Jira home directory:

*   Clone the repository outside of Jira then connect to it via Connect to Git Repository ➜ **Advanced Setup**.

*   Clone the repository with the standard **Connect to Git Repository** wizard into the Jira home directory.  Soon afterwards, move the cloned repository and update the settings on the repository.

*   You could symlink the `{$Jira_HOME}/data/git-plugin` directory to a different volume. The standard **Connect to Git Repository** wizard will still write there, but the data will reside on the different volume. But be aware, that Git Integration app treats anything in the `git-plugin` folder as a clone that it owns.

&nbsp;
* * *

[**Prev:** Adding a repository hosted on Windows Server or Windows Network share](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-server-or-windows-network-share-gij-self-managed)

[**Next:** Tracked folders overview](/git-integration-for-jira-data-center/tracked-folders-overview-gij-self-managed)

&nbsp;

### More related topics on setting up repositories

[Git integration configuration page](/git-integration-for-jira-data-center/git-integration-configuration-page-gij-self-managed)

[Using the Add new integration wizard](/git-integration-for-jira-data-center/using-the-add-new-integration-wizard-gij-self-managed)

[Using the Connect Repository wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed)

[Connecting a repository via Advanced setup](/git-integration-for-jira-data-center/connecting-a-repository-via-advanced-setup-gij-self-managed)

[Adding a repository hosted on Windows Server or Windows Network Share](/git-integration-for-jira-data-center/adding-a-repository-hosted-on-windows-server-or-windows-network-share-gij-self-managed)

**Setup repository root not located in Jira HOME directory** (this page)

[Tracked folders overview](/git-integration-for-jira-data-center/tracked-folders-overview-gij-self-managed)

[Self-signed HTTPS integration](/git-integration-for-jira-data-center/self-signed-https-integration-gij-self-managed)

[Managing repository or integration configuration](/git-integration-for-jira-data-center/managing-repository-or-integration-configuration-gij-self-managed)

[Associating project permissions](/git-integration-for-jira-data-center/associating-project-permissions-gij-self-managed)

