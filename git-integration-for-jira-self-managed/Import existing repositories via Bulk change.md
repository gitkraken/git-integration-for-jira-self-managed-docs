---

title: Import existing repositories via Bulk change
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
For administrators who have several repositories, the Git Integration for Jira app allows you to import multiple repository configuration using a **.tsv** file. This will make managing large Git repository lists more efficient.

If you already have the formatted .tsv file ready for import such as the exported bulk change configuration from a couple of pages back:

1.  On the manage git configuration page, go to Bulk change ➜ **2\. Import configuration**. The following dialog is displayed.

2.  ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397888/gitserver-gitcfg-bulk-change-import-dlg(c).png?version=1&modificationDate=1630642863364&cacheVersion=1&api=v2&width=544&height=412)

    Click **Choose File...** on the Import repository configuration dialog.

3.  Navigate to the location of the .tsv file then click **Open**.

4.  Click **Upload** to start the import process.


The Git Integration for Jira app will read the list from the file, detect the existing configured repositories, and automatically update its settings. If an error is found, it will be displayed in the message log on the import screen and in the _**Status**_ column on the repository configuration list. 

Make the required changes to correct the errors on the affected rows and redo the upload.

[« Requirement for secured import](/wiki/spaces/GIJDC/pages/1930397869/Requirement+for+secured+import)

[Import new repositories via Bulk change »](/wiki/spaces/GIJDC/pages/1930397912/Import+new+repositories+via+Bulk+change)

### More related topics about bulk change

*   Page:

    [Bulk change](/git-integration-for-jira-self-managed/Bulk-change) (Git Integration for Jira Data Center)

*   Page:

    [Exporting repository configuration via Bulk change](/wiki/spaces/GIJDC/pages/1930397830/Exporting+repository+configuration+via+Bulk+change) (Git Integration for Jira Data Center)

*   Page:

    [Requirement for secured import](/wiki/spaces/GIJDC/pages/1930397869/Requirement+for+secured+import) (Git Integration for Jira Data Center)

*   Page:

    [Import existing repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397888/Import+existing+repositories+via+Bulk+change) (Git Integration for Jira Data Center)

*   Page:

    [Import new repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397912/Import+new+repositories+via+Bulk+change) (Git Integration for Jira Data Center)

*   Page:

    [Editing existing repository settings in the TSV File](/wiki/spaces/GIJDC/pages/1930397941/Editing+existing+repository+settings+in+the+TSV+File) (Git Integration for Jira Data Center)

*   Page:

    [Removing existing repositories via Bulk change](/wiki/spaces/GIJDC/pages/1930397978/Removing+existing+repositories+via+Bulk+change) (Git Integration for Jira Data Center)