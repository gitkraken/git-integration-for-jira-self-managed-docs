---

title: Adding a repository hosted on Windows Servers or Windows Network Share (Admins)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Add a new network share or Windows server hosted repository via the Connect to Git Repository wizard.

The wizard will continue without errors if the following conditions are met:

*   The network credentials accessing the git repository must be the same as the user running Jira.

*   The network path is not longer than 255 characters.

*   The user under which Jira is running should have **read** access to network path.


In the Manage git repositories page, edit the repository via Actions ➜ **Edit repository settings**.

Under **Repository Settings**, set _**Enable Fetches**_ option to `Git repository hosted on the same server as Jira`.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396287/gitserver-edit-repocfg-fetches-sel2.png?version=1&modificationDate=1630642787827&cacheVersion=1&api=v2&width=442&height=81)

Considering the above conditions, verify if the repository can be cloned successfully using the network path.  With the server which hosts Jira, start the command-line session under the same user which Jira is running on.

For example:

```powershell
$ git clone file:////Ws148/Photo/repo
Cloning into ‘network-repo’...
```


If the path is invalid, does not exist or has permission issues, an error similar to the following will be displayed:

```java
fatal: '//Ws148/Photo/repo' does not appear to be a git repository
fatal: Could not read from remote repository.
Please make sure you have the correct access rights
and the repository exists.
```


For more information, see [Setting up repositories – Adding a Repository Hosted on Windows Servers or Windows Network Share](/git-integration-for-jira-self-managed/adding-a-repository-hosted-on-windows-server-or-windows-network-share/).

* * *

[Previous: General settings - Improving Jira performance](/git-integration-for-jira-self-managed/general-settings-improving-jira-performance/)

[Next: Setting up repository root not located in Jira Home directory (Admins)](/git-integration-for-jira-self-managed/setting-up-repository-root-not-located-in-jira-home-directory-admins/)

