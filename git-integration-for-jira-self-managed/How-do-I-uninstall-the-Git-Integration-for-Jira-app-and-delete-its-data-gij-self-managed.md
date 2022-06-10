---

title: How do I uninstall the Git Integration for Jira app and delete its data?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The following steps will remove the Git Integration for Jira app and delete its data from Jira:

|     |
| --- |
| **1\. Uninstall the Git Integration for Jira app from the Jira UPM (Universal Plugin Manager).** |
| Go to ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ **Manage apps** ➜ (sidebar) **Manage apps**. Under _User-installed apps_, select **Git Integration for Jira** then click **Uninstall**.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2053832772/gitserver-manage-apps-list.png?version=1&modificationDate=1642429474065&cacheVersion=1&api=v2&width=680&height=295) |
| **2\. Delete all repositories**. |
| **Example:**<br><br>```java<br>rm -rf $Jira_HOME/data/git-plugin<br>``` |
| **3\. Delete the index.** |
| **Example:**<br><br>```java<br>rm -rf $Jira_HOME/caches/indexes/plugins/jira-git-*<br>``` |
| **4\. Remove the Git Integration for Jira app tables (all tables starting with** `AO_8BA09E_`) from the Jira database. |
| Credentials are usually located in `$Jira_HOME/dbconfig.xml`. There is no standard SQL command to remove all tables by prefix. The list of tables depends on the installed Git Integration for Jira app version. All the tables are displayed in ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Jira Administration ➜ System ➜ (sidebar) **Plugin Data Storage** ➜ _Git Integration for Jira_.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2053832772/gitserver-system-plugin-data-storage.png?version=1&modificationDate=1642429788461&cacheVersion=1&api=v2&width=680&height=230) |
| **5\. Remove the table by performing the following SQL command:** `DROP TABLE table_name`**.** |

