---

title: Reconfigure Git repositories and SSH keys
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Perform the following steps to reconfigure repositories and SSH key:

1.  Remove any old SSH keys configured with the Git Integration app via `<JiraHOSTNAME> /secure/ViewSshKeys.jspa` (_Git Integration for Jira sidebar_ ➜ SSH keys).

2.  Restart Jira.

3.  Get the private key file from your Jira server to your Windows workstation: `/home/jira/.ssh/id_rsa`

4.  [Open the Connect wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed), use the repository location (git clone URL) and then upload the private key stated above.

For multiple repository configuration, see [Bulk change](/git-integration-for-jira-data-center/bulk-change-gij-self-managed/).

