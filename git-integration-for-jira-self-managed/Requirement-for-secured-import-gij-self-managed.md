---

title: Requirement for secured import
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

### SSH integration

Before adding repositories (new or existing) via Bulk change, make sure that you have added SSH keys for the respective git hosts in the Git Integration for Jira app configuration page. For example, you have GitHub and GitLab repositories to import, add the private SSH keys to the Git for Integration Jira app ➜ **SSH Keys** (_sidebar_) for each git host. For more information, see [Documentation – Adding a private SSH key](/git-integration-for-jira-data-center/adding-a-private-ssh-key-gij-self-managed).

&nbsp;

### HTTP/HTTPS integration

If you use HTTP/HTTPS URLs in the origin field, the Git Integration for Jira app will not be able to import said repositories due to missing credentials. Entering repository login credentials in the TSV file is not advisable due to a possible security risk. Therefore, when editing the _**origin**_ field of the TSV file, enter value using the `git@<repository-url>:[your-git-repo].git` format. This format will use the SSH key(s) from the Git Integration for Jira app configuration instead.

Proceed to import repositories by following on the next topic.

&nbsp;
* * *

[**Prev:** Exporting repository configuration via Bulk change](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed)

[**Next:** Import existing repositories via Bulk change](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed)

&nbsp;

### More related articles on Bulk change

[Exporting repository configuration via Bulk change](/git-integration-for-jira-data-center/exporting-repository-configuration-via-bulk-change-gij-self-managed)

**Requirement for secured import** (this page)

[Import existing repositories via Bulk change](/git-integration-for-jira-data-center/import-existing-repositories-via-bulk-change-gij-self-managed)

[Import new repositories via Bulk change](/git-integration-for-jira-data-center/import-new-repositories-via-bulk-change-gij-self-managed)

[Editing existing repository settings in the TSV File](/git-integration-for-jira-data-center/editing-existing-repository-settings-in-the-TSV-file-gij-self-managed)

[Removing existing repositories via Bulk change](/git-integration-for-jira-data-center/removing-existing-repositories-via-bulk-change-gij-self-managed)

[Bulk change (index)](/git-integration-for-jira-data-center/bulk-change-gij-self-managed)

