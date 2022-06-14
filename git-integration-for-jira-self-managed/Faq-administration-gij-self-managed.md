---

title: Administration (FAQ)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
This page contains solutions targeted for administrators.

Use the [FAQ](/git-integration-for-jira-self-managed/frequently-asked-questions-gij-self-managed) find answers to common questions.  Feel free to contact our support team ([support@bigbrassband.com](mailto:support@bigbrassband.com)) if you don't see what you're looking for.

- [How do I let people browse Git securely but without defining Git IDs for everyone?](#how-do-i-let-people-browse-git-securely-but-without-defining-git-ids-for-everyone)
- [Does the Git Integration for Jira app have API commands that allow addition/removal of a Git project?](#does-the-git-integration-for-jira-app-have-api-commands-that-allow-additionremoval-of-a-git-project)
- [After upgrading Jira from 4.1.1 to 5.2.9, I get some errors "Folder ... FORNEOnlineSolver git doesn't exist". Where can I set the path correctly? Is there any properties file?](#after-upgrading-jira-from-411-to-529-i-get-some-errors-folder--forneonlinesolver-git-doesnt-exist-where-can-i-set-the-path-correctly-is-there-any-properties-file)
- [Does Jira+GitHub integration support multiple Jira projects (many) to multiple git repositories (many)? If it does not, how about many-to-one or one-to-many?](#does-jiragithub-integration-support-multiple-jira-projects-many-to-multiple-git-repositories-many-if-it-does-not-how-about-many-to-one-or-one-to-many)
- [How do I connect to HTTPS repositories with self signed SSL certificates or other SSL issues?](#how-do-i-connect-to-https-repositories-with-self-signed-ssl-certificates-or-other-ssl-issues)
- [I want to track all repositories hosted in my GitLab server from my Jira Data Center/Server. How do I configure the required NFS access permissions?](#i-want-to-track-all-repositories-hosted-in-my-gitlab-server-from-my-jira-data-centerserver-how-do-i-configure-the-required-nfs-access-permissions)
  - [Solution 1](#solution-1)
  - [Solution 2](#solution-2)
- [How do I setup GitLab Server to respond to incoming network API calls?](#how-do-i-setup-gitlab-server-to-respond-to-incoming-network-api-calls)

* * *

## How do I let people browse Git securely but without defining Git IDs for everyone?

With the Git Integration for Jira app, you only need to define a single ID for the Jira server.  Jira then lets authorized Jira users browse Git.

You can restrict access to the Repository Browser _(views git list/repo folders in Jira)_ for the selected repository by associating the project permissions. On Jira, the **View Development Tools** permission must be granted to Users / Group / Project Roles.

Configure this setting via:

*   Jira dashboard menu:

    *   Git ➜ **Manage repositories**

    *   ![](/wp-content/uploads/actions-icon.png) Actions ➜ Edit integration/repository settings ➜ **Project Permissions**

    *   Unmark the _**All Projects**_ checkbox and set one or two projects.

*   Connect Wizard:

    *   On the Integration Settings screen ➜ **Project Permissions**.

    *   Unmark the _**All Projects**_ checkbox and set one or two projects.

## Does the Git Integration for Jira app have API commands that allow addition/removal of a Git project?

Yes. The Git Integration for Jira app supports REST APIs for adding, updating, and deleting repository. The documentation for this feature is available at [Git Integration app: Hook and API Reference - Repository REST API](/git-integration-for-jira-self-managed/repository-api-gij-self-managed).

## After upgrading Jira from 4.1.1 to 5.2.9, I get some errors "Folder ... FORNEOnlineSolver git doesn't exist". Where can I set the path correctly? Is there any properties file?

Please visit Git Integration for Jira app config and check Git Repositories tab (_Jira dashboard menu Git_ ➜ _Manage repositories_ ➜ ![](/wp-content/uploads/actions-icon.png) **Actions**):

*   For integrations, go to ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Show integration repositories** ➜ click a repository to view the repository settings.

*   For repository connections, go to ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Edit repository settings**.

Check and verify the path to your configured repositories.

Also, an upgrade of Jira may lead to changing of user account used to run the service, which in turn, may result in lack of permissions.

## Does Jira+GitHub integration support multiple Jira projects (many) to multiple git repositories (many)? If it does not, how about many-to-one or one-to-many?

Yes — it does support repositories supporting many projects. That said, the associations are made by the developers when they commit code to a specific issue key (which is part of a project). The permission that allows a user to see these commits in a Jira project is whether they have the "**View Development Tools**" permission for that project (that's a Jira setting).

The only project permissions that the Git Integration for Jira app has are for the Repository Browser (Git dropdown menu). To associate a repository with all Jira projects or only specific projects, see [Project permissions setting](/git-integration-for-jira-self-managed/using-the-connect-repository-wizard-gij-self-managed#settings) in the Connect to Git Repository wizard or [associating project permissions](/git-integration-for-jira-self-managed/associating-project-permissions-gij-self-managed) via **Edit repository settings** in the Git Repositories configuration page.

## How do I connect to HTTPS repositories with self signed SSL certificates or other SSL issues?

This problem may be caused by a custom (a self-signed) certificate. Make sure to install the latest JRE and then change the `JAVA_HOME` of Jira server.

The above solution should work, otherwise, see below for the steps to workaround this issue:

1.  From your Jira Data Center/Server, clone the repository manually using the git client.

    **Example:**

    ```java
    cd /jira/home
    cd data/git-plugin
    git clone --mirror https://my-self-signed-repo/project.git
    ```

2.  Make sure that the Jira user has access to the folder above.

3.  Configure the repository to disable verification of the SSL certificate.

    **Example:**

    ```java
    cd project.git
    git config http.sslVerify false
    ```

4.  Run  `git config http.sslVerify false` in the repository folder.

5.  From your browser, log into Jira and go to Jira dashboard menu Git ➜ **Manage repositories**. The manage git repositories configuration page is displayed.

6.  Click **Connect to Git Repository** then [_Advanced setup_](/git-integration-for-jira-self-managed/connecting-a-repository-via-advanced-setup-gij-self-managed).

7.  For the _Display Name_, enter a description of the Git repository.

8.  For the _Repository Root_, enter the full path to the Git repository that you have cloned. Considering the example in **step 1**, it will be similar to `/jira/home/data/git-plugin/project.git`.

9.   Click the **Detect** button next to the _Repository Origin_.

10.  Click **Add** to add this repository to the Git repository configuration list.


The clone will be kept up-to-date and the SSL verification issues will be ignored.

There are alternative solutions to make Java trust this certificate.  Please refer to the following articles from Atlassian which focuses on helping to resolve SSL Verification Issues:

*   [**Unable to Connect to SSL Services due to PKIX Path Building Failed**](https://confluence.atlassian.com/kb/unable-to-connect-to-ssl-services-due-to-pkix-path-building-failed-779355358.html)

*   [**Connecting to SSL services**](https://confluence.atlassian.com/jira/connecting-to-ssl-services-117455.html)


If the problem persist, please [send us a support zip](/git-integration-for-jira-self-managed/faq-support#how-to-create-the-support-zip-file-gij-self-managed) to give us a better view of the issue.

## I want to track all repositories hosted in my GitLab server from my Jira Data Center/Server. How do I configure the required NFS access permissions?

Where a GitLab server is configured with NFS server and the Jira Data Center/Server is configured with NFS client, there are two possible solutions:

### Solution 1

The `'all_squash'` option must not be used in the NFS server **'etc/exports'** file for GitLab folders. The NFS client should have the **'git'** group with the same GID as the **'git'** group on the NFS server. The Jira user on the NFS client should be added to the group **'git'**.

_**Example:**_<br>
```java
/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,root_squash,async)
```
### Solution 2

Use the `'all_squash,async,anonuid=$uid,anongid=$gid'` option on NFS server, where _$uid_ and _$gid_are user ID and group ID for **'git'** user and **'git'** group respectively _(or another user/group which you are using to access GitLab repositories on GitLab server)_.

_**Example:**_

```java
/var/opt/gitlab/git-data/repositories/testrepo xx.xx.xx.xx/24(ro,all_squash,async,anonuid=497,anongid=497)
```

In both cases either `'ro'` or `'rw'` options may be used on NFS server.

## How do I setup GitLab Server to respond to incoming network API calls?

In order for GitLab to display correct repository clone links to your users it needs to know the URL under which it is reached by your users (e.g. `http://gitlab.example.com/`)

To reconfigure:

1.  Access the GitLab configuration file in `/etc/gitlab/gitlab.rb`. 

    ```java
    sudo vi /etc/gitlab/gitlab.rb
    ```

2.  Change the `external_url` value to your GitLab server URL. 

    ```java
    external_url "http://gitlab.example.com" #this is the default URL
    external_url "http://X.X.X.X.local/" #change it to your GitLab Server URL
    ```

3.  Run the **reconfigure** command to make the change take effect. 

    ```java
    sudo gitlab-ctl reconfigure
    ```


Read this [**GitLab documentation**](https://docs.gitlab.com/omnibus/settings/configuration.html#configuring-the-external-url-for-gitlab) to know more about configuring the external URL for GitLab.

You should be able to add the GitLab repositories via Git Integration for Jira app ➜ **Connect to Git Repository** / **Add New integration**.

