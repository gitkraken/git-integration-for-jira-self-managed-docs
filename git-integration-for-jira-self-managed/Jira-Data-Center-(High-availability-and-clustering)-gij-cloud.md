---

title: Jira Data Center (High availability and clustering)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
As of **v2.6.12+** of the Git Integration for Jira app, the Data Center version of Jira is supported. Jira 6.3 or higher is required for Data Center editions of Jira.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Known issue (admins):</b><br>
        To provide access for both users for newly created tables, configure default tables and sequences permissions as follows (where <code>jira1</code> & <code>jira2</code> are users); see below.<br>
        <div class='nextpara'><pre><code>ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL PRIVILEGES ON tables TO jira1;
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
<br>

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
<br>

## The trustFolderStat setting

The trustFolderStat setting can be accessed in the following locations:

*   Jira dashboard menu **Git** ➜ Manage repositories ➜ **General Settings**.

*   Manage repositories ➜ <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit integration connection settings**.

*   <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Show integration repositories** ➜ click a repository (_Integration_ ➜ repository level settings).

*   <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Edit repository settings**.

*   Manage repositories page ➜ Connect to Git repository ➜ **Advanced setup**.


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

