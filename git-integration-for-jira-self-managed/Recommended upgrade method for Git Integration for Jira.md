---

title: Recommended upgrade method for Git Integration for Jira
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
For full list of features, version history and supported Jira version of the Git for Jira app, see [**Git Integration for Jira app Version History**](https://marketplace.atlassian.com/plugins/com.xiplink.jira.git.jira_git_plugin/versions).


If you have installed the Git Integration for Jira app with versions prior to v2.10.2, perform the following steps to upgrade with minimal risk:

1.  Do the upgrade at night – when the number of Jira users is minimal.

2.  Make backups.

    1.  **Make a Jira backup (recommended).** The Git for Jira app upgrade only updates its components.  Thus, it has no adverse effect to Jira. It is still better to make a backup of your Jira before any app upgrade as a safety measure.

    2.  **Make a Git Integration for Jira app configuration backup (recommended).** Make sure to do a backup of the Git repositories connection configuration.

        1.  Perform a bulk export of your existing repositories or integration via the Git Integration for Jira app repositories configuration page.

            1.  On your Jira dashboard menu Git ➜ **Manage repositories**.

            2.  Click the **Bulk Change** button drop down then select **1\. Export configuration**. For detailed steps, see [Bulk Change - Export Configuration](/wiki/spaces/GIJDC/pages/1930397830/Exporting+repository+configuration+via+Bulk+change).

                ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396509/bulk-export-loc-test(c).png?version=1&modificationDate=1630642797003&cacheVersion=1&api=v2)
        2.  Make sure that you have all the required SSH keys uploaded to the Git Integration for Jira app

            1.  On your Jira dashboard, go to menu Git ➜ **Manage repositories**.

            2.  Click **SSH keys** on the sidebar. This will make seamless connection of the SSH git repositories to Jira via [Bulk Change - Import Configuration](/wiki/spaces/GIJDC/pages/1930397888/Import+existing+repositories+via+Bulk+change).

                ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396509/add-ssh-key-loc-test(c).png?version=1&modificationDate=1630642797244&cacheVersion=1&api=v2)
3.  Upgrade the Git for Jira app to the latest version.


If you have several large repositories and have a problem with exceeded timeout, we recommend that you use our [Tracked folders](/wiki/spaces/GIJDC/pages/91947120) feature to scan local folders at once and import repositories automatically.

Another option is to completely uninstall then reinstall the Git for Jira app. However, this will result in Jira running on a clean state:

1.  Backup the Git repositories configuration via the Git for Jira app Bulk Export.

2.  Fully uninstall the Git Integration for Jira app  – follow [these instructions](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/91947236/Uninstall+and+Reinstall#UninstallandReinstall-uninstallapp).

3.  Install the Git Integration for Jira app via UPM.

4.  Add all required SSH keys again by uploading them into Git Integration for Jira app ➜ **SSH keys**.

5.  Using the file from Bulk Export, import all your repositories via Bulk Change ➜ **Import Configuration**.

6.  Manually reindex the repositories based on its usage priority or click **Reindex all** to reindex them all at once.


[« Working with Tracked folders](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders)

[Discard cloned files in Jira Home directory (General setting) »](/wiki/spaces/GIJDC/pages/1930396547)

### More related topics about getting started for git admins

*   Page:

    [Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls) (Git Integration for Jira Data Center)

*   Page:

    [New GitLab v10+ authentication](/wiki/spaces/GIJDC/pages/1930396211) (Git Integration for Jira Data Center)

*   Page:

    [General settings: Improving Jira performance](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance) (Git Integration for Jira Data Center)

*   Page:

    [Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/wiki/spaces/GIJDC/pages/1930396287) (Git Integration for Jira Data Center)

*   Page:

    [Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317) (Git Integration for Jira Data Center)

*   Page:

    [Recommended reindex interval setting](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting) (Git Integration for Jira Data Center)

*   Page:

    [Reindex API to trigger indexing](/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing) (Git Integration for Jira Data Center)

*   Page:

    [Setting up web linking](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking) (Git Integration for Jira Data Center)

*   Page:

    [Setting up webhooks](/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks) (Git Integration for Jira Data Center)

*   Page:

    [Increasing timeout threshold for large repositories while doing a Git pull](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull) (Git Integration for Jira Data Center)

*   Page:

    [Working with Tracked folders](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders) (Git Integration for Jira Data Center)

*   Page:

    [Recommended upgrade method for Git Integration for Jira](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira) (Git Integration for Jira Data Center)

*   Page:

    [Discard cloned files in Jira Home directory (General setting)](/wiki/spaces/GIJDC/pages/1930396547) (Git Integration for Jira Data Center)