---

title: Uninstall and reinstall
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This page contains related questions about installation management of Git Integration for Jira add-on.

Use the FAQ below to find answers to common questions.  Feel free to contact our support team ([support@gitkraken.com](mailto:support@gitkraken.com?subject=Uninstall/Reinstall%20issues%20-)) or visit our [support portal](https://help.gitkraken.com/git-integration-for-jira-cloud/gij-cloud-contact-support/) if you don't see what you're looking for.

- [How do I reinstall the plugin?](#how-do-i-reinstall-the-plugin)
- [How do I uninstall the Git Integration for Jira app and delete its data?](#how-do-i-uninstall-the-git-integration-for-jira-app-and-delete-its-data)
- [In the temp location, I see several jar files with different versions updated at the same time. What would be the procedure for cleaning them up?](#in-the-temp-location-i-see-several-jar-files-with-different-versions-updated-at-the-same-time-what-would-be-the-procedure-for-cleaning-them-up)
- [When removing the Git Integration for Jira app indexing service, there are 2 services listed: "GitRevisionIndexerJob" AND "Git Revision Indexing Service". Which should I delete?](#when-removing-the-git-integration-for-jira-app-indexing-service-there-are-2-services-listed-gitrevisionindexerjob-and-git-revision-indexing-service-which-should-i-delete)

<br>
<hr>
<br>

## How do I reinstall the plugin?

1.  Do a full uninstall of the plugin as detailed in [**here**](#how-do-i-uninstall-the-git-integration-for-jira-app-and-delete-its-data).

2.  Install the Git Integration for Jira app as outlined in [**here**](/git-integration-for-jira-data-center/Installation-gij-self-managed).

## How do I uninstall the Git Integration for Jira app and delete its data?

The following steps will remove the Git Integration for Jira app and delete its data from Jira:

1.  **Uninstall the Git Integration for Jira app from the Jira UPM (Universal Plugin Manager).**

    Go to Jira Administration ➜ **Manage apps** ➜ (sidebar) **Manage apps**. Under _User-installed apps_, select **Git Integration for Jira** then click **Uninstall**.

    ![](/wp-content/uploads/gij-gitserver-manage-apps-list.png)

2. **Delete all repositories**.

    **Example:**<br>
    ```powershell
    rm -rf $Jira_HOME/data/git-plugin
    ```

3. **Delete the index.**

    **Example:**<br>
    ```powershell
    rm -rf $Jira_HOME/caches/indexes/plugins/jira-git-*
    ```

4. **Remove the Git Integration for Jira app tables (all tables starting with**

    `AO_8BA09E_`) from the Jira database.

    Credentials are usually located in `$Jira_HOME/dbconfig.xml`. There is no standard SQL command to remove all tables by prefix. The list of tables depends on the installed Git Integration for Jira app version.

    All the tables are displayed in Jira Administration ➜ System ➜ (sidebar) **Plugin Data Storage** ➜ _Git Integration for Jira_.

    ![](/wp-content/uploads/gij-gitserver-system-plugin-data-storage.png)

5. **Remove the table by performing the following SQL command:**

    `DROP TABLE table_name`.

## In the temp location, I see several jar files with different versions updated at the same time. What would be the procedure for cleaning them up?

Make sure that the UPM add-on installed in your Jira instance is the latest version.

The goal here is to end up with only one copy of the `jira_git_plugin jar` file in the `./home/plugins/installed-plugins` folder and all others removed:

1.  Stop Jira.

2.  Fully clean up the [**plugin temp folders**](https://answers.atlassian.com/questions/7110972/can-we-clean-up-osgi-plugins-in-jira) or at least remove these kind of files:

    **Example:**

    ```powershell
    JIRA_INSTALL_FOLDER/temp/*_git_plugin-*.jar
    JIRA_HOME_FOLDER/plugins/.osgi-plugins/transformed-plugins/*_git_plugin-*.jar
    ```

3.  Remove all versions of the Git Plugin from `installed-plugins` folder except the latest version (`JIRA_HOME_FOLDER/plugins/installed-plugins/*jira_git_plugin-x.y.z.jar`):

    **Example:**

    ```powershell
    JIRA_HOME_FOLDER/plugins/installed-plugins/*_git_plugin-*.jar
    ```

4.  Run Jira.

## When removing the Git Integration for Jira app indexing service, there are 2 services listed: "GitRevisionIndexerJob" AND "Git Revision Indexing Service". Which should I delete?

**GitRevisionIndexerJob** is the correct one. Keep that job.

**Git Revision Indexing Service** is an old job and should be removed.

