---

title: Import existing repositories via Bulk change
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
For administrators who have several repositories, the Git Integration for Jira app allows you to import multiple repository configuration using a **.tsv** file. This will make managing large Git repository lists more efficient.

If you already have the formatted .tsv file ready for import such as the exported bulk change configuration from a couple of pages back:

1.  On the manage git configuration page, go to Bulk change ➜ **2\. Import configuration**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitcfg-bulk-change-import-dlg-c.png)

2.  Click **Choose File...** on the Import repository configuration dialog.

3.  Navigate to the location of the .tsv file then click **Open**.

4.  Click **Upload** to start the import process.


The Git Integration for Jira app will read the list from the file, detect the existing configured repositories, and automatically update its settings. If an error is found, it will be displayed in the message log on the import screen and in the _**Status**_ column on the repository configuration list. 

Make the required changes to correct the errors on the affected rows and redo the upload.

<p>&nbsp;</p>
<hr>
<p>&nbsp;</p>

[**Prev:** Requirement for secured import](/git-integration-for-jira-data-center/requirement-for-secured-import-gij-self-managed)

[**Next:** Import new repositories via Bulk change](/git-integration-for-jira-data-center/Import-new-repositories-via-Bulk-change-gij-self-managed)

&nbsp;

## More related articles on Bulk change

[Exporting repository configuration via Bulk change](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed)

[Requirement for secured import](/git-integration-for-jira-data-center/requirement-for-secured-import-gij-self-managed)

**Import existing repositories via Bulk change** (this page)

[Import new repositories via Bulk change](/git-integration-for-jira-data-center/import-new-repositories-via-bulk-change-gij-self-managed)

[Editing existing repository settings in the TSV File](/git-integration-for-jira-data-center/editing-existing-repository-settings-in-the-TSV-file-gij-self-managed)

[Removing existing repositories via Bulk change](/git-integration-for-jira-data-center/removing-existing-repositories-via-bulk-change-gij-self-managed)

[Bulk change (index)](/git-integration-for-jira-data-center/bulk-change-gij-self-managed)

