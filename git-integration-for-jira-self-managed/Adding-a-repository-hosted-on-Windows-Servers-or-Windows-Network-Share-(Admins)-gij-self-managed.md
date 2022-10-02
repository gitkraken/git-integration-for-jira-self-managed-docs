---

title: Adding a repository hosted on Windows Servers or Windows Network Share (Admins)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Add a new network share or Windows server hosted repository via the Connect to Git Repository wizard.

The wizard will continue without errors if the following conditions are met:

*   The network credentials accessing the git repository must be the same as the user running Jira.

*   The network path is not longer than 255 characters.

*   The user under which Jira is running should have **read** access to network path.


In the Manage git repositories page, edit the repository via ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit repository settings**.

Under **Repository Settings**, set _**Enable Fetches**_ option to `Git repository hosted on the same server as Jira`.

<img src='/wp-content/uploads/gij-gitserver-edit-repocfg-fetches-sel2.png' style='display:block;margin:25px auto;max-width:100%' width=442 height=81 />

Considering the above conditions, verify if the repository can be cloned successfully using the network path.  With the server which hosts Jira, start the command-line session under the same user which Jira is running on.

For example:

```powershell
$ git clone file:////Ws148/Photo/repo
Cloning into ‘network-repo’...
```


If the path is invalid, does not exist or has permission issues, an error similar to the following will be displayed:

```bash
fatal: '//Ws148/Photo/repo' does not appear to be a git repository
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
and the repository exists.
```


For more information, see [Integration guide -- Windows Network Share](/git-integration-for-jira-data-center/windows-network-server-share-gij-self-managed).

