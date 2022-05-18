---

title: Jira Data Center (High availability and clustering)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
As of **v2.6.12+** of the Git Integration for Jira app, the Data Center version of Jira is supported. Jira 6.3 or higher is required for Data Center editions of Jira.

**Known issue (admins):**
To provide access for both users for newly created tables, configure default tables and sequences permissions as follows (where `jira1` & `jira2` are users); see below.

```java
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON tables TO jira1;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON tables TO jira2;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON sequences TO jira1;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON sequences TO jira2;
```

The configured repositories are located on the shared resource, since the nodes do not contain their own copy of the repositories.

The git repositories are located in the Jira Data Center shared folder.


The smart commits are processed by the reindex job which run once per cluster. The node updates the index during the scheduled reindex job. For Jira Data Centers, the indexes are stored in each node.

The _GarbageCollection_ job should be run once on one node at the same time. The following are indexing triggers:

*   Indexing is run on newly created repository on other nodes.

*   Entries from index will be removed from other nodes.

*   Reindex all repositories on other nodes when the reindex job is triggered.


**For node changes:**
When the number of nodes in the Data Center cluster is changed, the Jira administrator should manually perform a full reindex for all repositories to rebuild index on new nodes.

Repositories with absolute paths should be migrated manually. Jira administrators will be responsible to place them to the correct path.

## The trustFolderStat setting

The trustFolderStat setting can be accessed in the following locations:

*   Jira dashboard menu **Git** ➜ Manage repositories ➜ **General Settings**.

*   Manage repositories ➜ ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit integration connection settings**.

*   ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Show integration repositories** ➜ click a repository (_Integration_ ➜ repository level settings).

*   ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit repository settings**.

*   Manage repositories page ➜ Connect to Git repository ➜ **Advanced setup**.


When the _**trustFolderStat**_ setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.

The _default_ setting for Jira Data Center is **false**.

If your repository is stored on a network share, it is highly recommended to set this setting to _**false**_.

[« Integration webhooks](/git-integration-for-jira-self-managed/Integration-webhooks)

[Localization support »](/git-integration-for-jira-self-managed/Localization-support)