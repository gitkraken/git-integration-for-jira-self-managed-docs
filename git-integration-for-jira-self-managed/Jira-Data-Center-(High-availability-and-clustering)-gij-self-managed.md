---

title: Jira Data Center (High availability and clustering)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The Git Integration for Jira app supports the Data Center version of Jira. We recommend Jira 8 or higher for Data Center editions of Jira.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Known issue (admins):</b><br>
        To provide access for both users for newly created tables, configure default tables and sequences permissions as follows (where <code>jira1</code> & <code>jira2</code> are users); see below.<br>
        <div><pre><code>ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON tables TO jira1;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON tables TO jira2;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON sequences TO jira1;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON sequences TO jira2;</code></pre>
        </div>
    </div>
    </div>
</div>

The configured repositories are located on the shared resource, since the nodes do not contain their own copy of the repositories.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The git repositories are located in the Jira Data Center shared folder.
    </div>
    </div>
</div>

&nbsp;

The smart commits are processed by the reindex job which run once per cluster. The node updates the index during the scheduled reindex job. For Jira Data Centers, the indexes are stored in each node.

The _GarbageCollection_ job should be run once on one node at the same time. The following are indexing triggers:

*   Indexing is run on newly created repository on other nodes.

*   Entries from index will be removed from other nodes.

*   Reindex all repositories on other nodes when the reindex job is triggered.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>For node changes:</b><br>
        When the number of nodes in the Data Center cluster is changed, the Jira administrator should manually perform a full reindex for all repositories to rebuild index on new nodes.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Repositories with absolute paths should be migrated manually. Jira administrators will be responsible to place them to the correct path.
    </div>
    </div>
</div>

&nbsp;

### The trustFolderStat setting

The trustFolderStat setting can be accessed in the following locations:

*   Jira dashboard menu **Git** ➜ Manage repositories ➜ **General Settings**.

*   Manage repositories ➜ ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit integration connection settings**.

*   <img src='/wp-content/uploads/actions-icon.png' style='display:inline-block;margin-right:3px;' /> Actions ➜ **Show integration repositories** ➜ click a repository (_Integration_ ➜ repository level settings).

*   <img src='/wp-content/uploads/actions-icon.png' style='display:inline-block;margin-right:3px;' /> Actions ➜ **Edit repository settings**.

*   Manage repositories page ➜ Connect to Git repository wizard ➜ **Advanced setup**.


When the _**trustFolderStat**_ setting is set to **false**, the `.git/objects/pack` folder will be always scanned to check for new pack files. If set to **true**, the `last-modified` attribute of the folder will be used to check the folder for modifications.

The _default_ setting for Jira Data Center is **false**.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If your repository is stored on a network share, it is highly recommended to set this setting to <b><i>false</i></b>.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Integration webhooks](/git-integration-for-jira-data-center/integration-webhooks-gij-self-managed)

[**Next:** Localization support](/git-integration-for-jira-data-center/localization-support-gij-self-managed)


