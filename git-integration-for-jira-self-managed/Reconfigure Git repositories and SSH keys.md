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

4.  [Open the Connect wizard](/wiki/spaces/GIJDC/pages/1930397090/Using+the+Connect+Repository+wizard), use the repository location (git clone URL) and then upload the private key stated above.



