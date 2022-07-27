---

title: Repositories
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This page contains solutions to common issues encountered while connecting and configuring git repositories.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([support@bigbrassband.com](mailto:support@bigbrassband.com?subject=Repository%20connection%20issues%20-)) if you don't see what you're looking for.

- [I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?](#i-have-an-existing-git-repository-on-a-jira-server-how-can-i-figure-out-what-values-should-be-used-for-repository-origin-and-repository-root-fields)
- [Can the app be configured to handle or scan multiple keys for one project? How is this supposed to work?](#can-the-app-be-configured-to-handle-or-scan-multiple-keys-for-one-project-how-is-this-supposed-to-work)
- [Where is the location of the local git repository?](#where-is-the-location-of-the-local-git-repository)
- [How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?](#how-do-you-configure-the-repository-root-which-is-not-located-in-a-jira-home-directory-with-git-integration-for-jira)
- [I get the following error: "Host or port specified in \<git\_repository\_url\> are inaccessible". Do I also need a git instance on the Jira server?](#i-get-the-following-error-host-or-port-specified-in-git_repository_url-are-inaccessible-do-i-also-need-a-git-instance-on-the-jira-server)
- [We use GitBlit without SSH keys and use only HTTPS instead. Does Git Integration for Jira app support this?](#we-use-gitblit-without-ssh-keys-and-use-only-https-instead-does-git-integration-for-jira-app-support-this)
- [I am using Jira which is hosted on Windows. I changed the password of the Active Directory account running Jira. Now, I cannot access my repository. Why?](#i-am-using-jira-which-is-hosted-on-windows-i-changed-the-password-of-the-active-directory-account-running-jira-now-i-cannot-access-my-repository-why)

* * *

## I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?

1.  Change current directory to the folder where repository is located.

2.  Run `pwd`.

3.  Response should go to **Repository root** field.

4.  Run `git remote show origin`.

5.  Find origin URL in the command response.

6.  Set this value for **Repository origin** field.

## Can the app be configured to handle or scan multiple keys for one project? How is this supposed to work?

Yes – the Git Integration for Jira app supports multiple Jira issue keys in a multiple-line commit message.

For more information, see [Smart Commits: Advanced examples](/git-integration-for-jira-data-center/advanced-examples-gij-self-managed).

## Where is the location of the local git repository?

The Repository Root (in settings) must be a local path for server which is used to run Jira.

In other words, the plugin must point to a clone of the repository and this clone must run locally with Jira.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/2051080265/faq-git-repo-advanced-screen.png?version=1&modificationDate=1642078696400&cacheVersion=1&api=v2&width=680&height=344)

## How do you configure the Repository Root which is not located in a Jira home directory with Git Integration for Jira?

There are three possible ways to do this:

*   Clone the repository outside of Jira then connect to it via **Connect to Git Repository** ➜ **Advanced Setup**.

*   Clone the repository with the standard **Connect to Git Repository Wizard** into the Jira home directory. Soon afterwards, move the cloned repository and update the settings on the repository.

*   You could symlink the `{$Jira_HOME}/data/git-plugin` directory to a different volume. The standard **Connect to Git Repository Wizard** will still write there, but the data will reside on the different volume. But be aware, that the Git Integration for Jira app treats anything in the Git-Plugin folder as a clone that it owns.

## I get the following error: "Host or port specified in \<git\_repository\_url\> are inaccessible". Do I also need a git instance on the Jira server?

If your Jira and Git servers are running through a firewall, configure the firewall to allow access using the URL schemes for git repositories. For authentication issues, make sure to check first the correct port for its connection.

Below are the default ports for common git URL protocols:

| Protocol | Default port |
| :--- | :--- |
| ssh:// | 22  |
| git:// | 9418 |
| http:// | 80  |
| https:// | 443 |


Test git connection and repository URL by doing the following:

1.  Install git client (or run `sudo apt-get install git`)

2.  Place your ssh key into `~/.ssh`

3.  Clone the repository (or run `git clone <your_repository_url>`)


The Git Integration for Jira app will run successfully if the above connection test ran without errors.

## We use GitBlit without SSH keys and use only HTTPS instead. Does Git Integration for Jira app support this?

Yes. The Git Integration for Jira app definitely supports GitBlit via HTTPS authentication.  Use the **Connect to Git Repository** wizard to connect to your repositories. Towards the end of the process, a username and password will be required for connection authentication.

## I am using Jira which is hosted on Windows. I changed the password of the Active Directory account running Jira. Now, I cannot access my repository. Why?

When using Active Directory accounts for repository access, changing the password of the AD account running Jira can cause repository authentication issues.

You need to restart Jira to regain access to repositories.

