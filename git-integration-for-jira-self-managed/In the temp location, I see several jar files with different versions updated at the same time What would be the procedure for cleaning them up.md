---

title: In the temp location, I see several jar files with different versions updated at the same time. What would be the procedure for cleaning them up?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Make sure that the UPM add-on installed in your Jira instance is the latest version.

The goal here is to end up with only one copy of the `jira_git_plugin jar` file in the `./home/plugins/installed-plugins` folder and all others removed:

1.  Stop Jira.
    
2.  Fully clean up the [**plugin temp folders**](https://answers.atlassian.com/questions/7110972/can-we-clean-up-osgi-plugins-in-jira) or at least remove these kind of files:
    
    **Example:**
    
    ```java
    JIRA_INSTALL_FOLDER/temp/*_git_plugin-*.jar
    JIRA_HOME_FOLDER/plugins/.osgi-plugins/transformed-plugins/*_git_plugin-*.jar
    ```
    
3.  Remove all versions of the Git Plugin from `installed-plugins` folder except the latest version (`JIRA_HOME_FOLDER/plugins/installed-plugins/*jira_git_plugin-x.y.z.jar`):
    
    **Example:**
    
    ```java
    JIRA_HOME_FOLDER/plugins/installed-plugins/*_git_plugin-*.jar
    ```
    
4.  Run Jira.
    
