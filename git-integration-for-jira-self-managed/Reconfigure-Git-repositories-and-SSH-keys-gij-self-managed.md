---

title: Reconfigure Git repositories and SSH keys
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Perform the following steps to reconfigure repositories and SSH key:

1.  Remove any old SSH keys configured with the Git Integration app via `<JiraHOSTNAME> /secure/ViewSshKeys.jspa` (_Git Integration for Jira sidebar_ ➜ SSH keys).

2.  Restart Jira.

3.  Get the private key file from your Jira server to your Windows workstation: `/home/jira/.ssh/id_rsa`

4.  [Open the Connect wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed), use the repository location (git clone URL) and then upload the private key stated above.

For multiple repository configuration, see [Bulk change](/git-integration-for-jira-data-center/bulk-change-gij-self-managed).

<br>
<br>

[**Prev:** Removing SSH keys](/git-integration-for-jira-data-center/removing-ssh-keys-gij-self-managed)

[**Next:** Git URL ports](/git-integration-for-jira-data-center/git-url-ports-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

[Working with SSH keys (index)](/git-integration-for-jira-data-center/working-with-ssh-keys-gij-self-managed)

[Generating SSH keys](/git-integration-for-jira-data-center/generating-ssh-keys-gij-self-managed)

[Adding a private SSH key](/git-integration-for-jira-data-center/adding-a-private-ssh-key-gij-self-managed)

[Adding a public SSH Key](/git-integration-for-jira-data-center/adding-a-public-ssh-key-gij-self-managed)

[SSH keys configuration](/git-integration-for-jira-data-center/ssh-keys-configuration-gij-self-managed)

[Adding and associating SSH keys](/git-integration-for-jira-data-center/adding-and-associating-ssh-keys-gij-self-managed)

[Removing SSH keys](/git-integration-for-jira-data-center/removing-ssh-keys-gij-self-managed)

**Reconfigure Git repositories and SSH keys** (this page)


