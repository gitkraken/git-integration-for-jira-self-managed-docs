---

title: Creating Personal Access Tokens
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Creating Personal Access Tokens

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens>

* * *

This page contains steps for creating personal access tokens (PATs) for specific git hosts. Use the table of contents to navigate to the selected git host.

**What's on this page:**

*   [GitHub | GitHub Enterprise](#github)
    
*   [GitLab | GitLab CE/EE](#gitlab)
    
*   [Azure DevOps | Visual Studio Team Services (VSTS)](#azure-vsts)
    
*   [Team Foundation Server (TFS)](#tfs)
    
*   [Azure DevOps Server](#azure-server)
    
*   [AWS CodeCommit](#aws)
    

* * *

## GitHub | GitHub Enterprise

If two-factor authentication is enabled for your GitHub account, you will need to create a Personal Access Token (PAT) to access your git repositories. Enable two-factor authentication in your GitHub account for increased security.

While instructions from GitHub works just fine, here are some specific instructions to get you up and running:

1.  Login to your GitHub account then go to your profile settings.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/github-ghe-profile-settings(c).png?version=1&modificationDate=1650870599401&cacheVersion=1&api=v2&width=204&height=434)
2.  On your sidebar, click **Developer settings**.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/github-user-settings-sidebar-dev-cfg(c).png?version=1&modificationDate=1650870599408&cacheVersion=1&api=v2&width=251&height=393)
3.  On the following screen, click **Personal access tokens** on the sidebar.
    
4.  Generate a new personal access token (PAT) by clicking **Generate new token**.
    
5.  The following screen is displayed.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/jira-cloud-github-mfa-gen-access-token(c).png?version=1&modificationDate=1650870599411&cacheVersion=1&api=v2&width=646&height=460)
    1.  On the _**Note**_ field, enter a descriptive name for this PAT. For example, `git-integration-for-jira`.
        
    2.  For _**Expiration**_ (required), set for how long the token will expire or set it according to your organization’s rules and policies.
        
    3.  For _**Select scopes**_, tick the **repo** scope (_this also automatically selects all the scopes under it_ – keep this setting).
        
6.  Click **Generate token** to complete this setup.
    
7.  Copy the token (write it down or save it somewhere safe – this is the ONLY time you'll see the token).
    

## GitLab | GitLab CE/EE

GitLab introduced personal access tokens (PAT) since version 8.8 and now (v10+) prefers this type of authentication for accessing the git repositories.  Service users are strongly advised to switch from using username/password to using Personal Access Tokens (PAT) for GitLab.

If two-factor authentication is enabled for your GitLab account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitLab account for increased security.

While instructions from GitLab works just fine, here are some specific instructions to get you up and running:

1.  Login to your GitLab account then go to your profile settings (menu ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Profile ➜ **Preferences**).
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/gitlab-user-profile-settings(c).png?version=1&modificationDate=1650870599414&cacheVersion=1&api=v2&width=251&height=313)
2.  On the sidebar, click **Access Tokens**.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/gitlab-user-settings-sidebar-access-token(c).png?version=1&modificationDate=1650870599417&cacheVersion=1&api=v2&width=204&height=326)
3.  The following screen is displayed.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/jira-cloud-gitlab-mfa-gen-access-token(c).png?version=1&modificationDate=1650870599419&cacheVersion=1&api=v2&width=544&height=695)
    1.  Give the token a descriptive **Name**. (For example, "Git Integration for Jira")
        
    2.  Leave the **Expiration date** field blank or set the expiration date according to your organization’s rules and policies.
        
    3.  Select the _**api**_ scope.
        
4.  Click **Create personal access token** to complete this setup.
    
5.  Copy the token – (Write it down or be sure to save it. This is the ONLY time you'll see the token)
    

In your GitLab repository account setting, the _**api**_ scopes of the PAT have the ability to create branches and merge requests to specified GitLab repositories via developer panel of a Jira issue.

## Azure DevOps | Visual Studio Team Services (VSTS)

Creating a personal access token will allow control on how a service user accesses specific resources from your git repositories. PATs can give you access to Azure Repos without using your username or password directly.

If you have not yet generated a personal access token (PAT):

1.  On the VSTS/Azure portal dashboard, click the user settings icon on the top right corner of the page.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/vsts-azure-devops-user-profile-settings(c).png?version=1&modificationDate=1650870599422&cacheVersion=1&api=v2&width=374&height=423)
2.  Click **Personal access tokens**. You will be taken to the Personal Access Tokens configuration page.
    
3.  Click ![(plus)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/add.png) **New Token**. The following dialog is displayed.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/vsts-azure-create-pats-jira-server-cloud(c).png?version=1&modificationDate=1650870599424&cacheVersion=1&api=v2&width=544&height=643)
    1.  Enter a descriptive name for your PAT. Since this is a connection to Jira, you can name it, for example, `git-integration-for-jira`.
        
    2.  For the _**Organization**_, make sure to set it to **All accessible organizations**. IMPORTANT!
        
    3.  Set the desired lifespan of your token. Set it to _**Custom defined**_ if you want to choose a longer expiration date.
        
    4.  On the _**Scopes**_ section, set it to **Custom defined**.
        
    5.  Set the _**Code**_ section to **Read & write**.
        
4.  Click **Create** to finish creating your PAT.
    

When you're done, make sure to copy and save the token. This token can be used as your password.

For personal access tokens where _**Organization**_ is not set to **All accessible organizations**:

*   Set the _**Scopes**_ section to **Full Access**; or
    
*   Set the _**Scopes**_ section to **Custom defined** and then set the _**Code**_ section to **Read**, **Status**.
    

As for _**Scopes**_:

*   `Code (read)`  –  This scope allows only to view commits and smart commits, and browse repositories (if enabled) of connected VSTS/Azure repositories inside Jira.
    
*   `Code (read and write)`  –  This scope has the `Code (read)` functions plus the ability to create branches and pull requests to specified VSTS/Azure repositories via developer panel of a Jira issue.
    

## Team Foundation Server (TFS) 2017 | (TFS) 2018

TFS 2017 and newer can use personal access token for on-premises TFS installations. This will allow control on how a service user accesses specific resources from your git repositories. PATs can give you access to Azure Repos without using your username or password directly.

Follow the steps below, if you have not yet generated a personal access token (PAT) for your user account:

1.  On the TFS portal dashboard, clicking the user settings icon on the top right corner of the page then click **Security**.
    
2.  ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/tfs-201718-acct-menu-panel(c).png?version=1&modificationDate=1650870599427&cacheVersion=1&api=v2&width=306&height=287)
    
    Click **Add** on the Personal Access Token page to see the following screen.
    
3.  ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/tfs-201718-create-pat-screen-sample(c2).png?version=1&modificationDate=1650870599430&cacheVersion=1&api=v2&width=646&height=323)
    
    Enter a meaningful name as **Description**.
    
4.  Set the lifespan of your token as desired.
    
5.  On the **Authorized Scopes** section, set it to **Selected scopes** then enable one of the settings that will be assigned to this service user:
    
    1.  For viewing commits, smart commits and browse repositories inside Jira, the recommended scope is **code (read)**.
        
    2.  For having the above access privilege plus branch and pull request creation via developer panel of a Jira issue, the recommended scope is **code (read and write)**.
        
6.  Click **Create token** to create this PAT with the specified scope.
    

When you're done, make sure to copy and save the token. This token can be used as your password.

## Azure DevOps Server

TFS 2017 and newer can use personal access token for on-premises Azure DevOps Server installations. This will allow control on how a service user accesses specific resources from your git repositories. PATs can give you access to Azure Repos without using your username or password directly.

Azure DevOps Server was formerly named Visual Studio Team Foundation Server (TFS).

Follow the steps below, if you have not yet generated a personal access token (PAT) for your user account:

1.  On the Azure DevOps Server portal dashboard, open the account settings by clicking the _user profile icon_ on the top right corner of the page then click **Security**.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/azure-devops-2019-acct-settings.png?version=2&modificationDate=1650870599435&cacheVersion=1&api=v2&width=251&height=389)
2.  On the Personal Access Token page, click ![(plus)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/add.png) **Add** to see the following screen.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/azure-devops-2019-pat-settings(c).png?version=1&modificationDate=1650870599492&cacheVersion=1&api=v2&width=646&height=322)
3.  Enter a meaningful name in the **Description** field.
    
4.  Set the lifespan of the PAT as desired.
    
5.  On the **Authorized Scopes** section, set it to **Selected scopes** then enable one of the settings that will be assigned to this service user:
    
    1.  For viewing commits, smart commits and browse repositories inside Jira, the recommended scope is **code (read)**.
        
    2.  For having the above access privilege plus branch and pull request creation via developer panel of a Jira issue, the recommended scope is **code (read and write)**.
        
6.  Click **Create token** to create this PAT with the specified scope.
    

When you're done, make sure to copy and save the token. This token can be used as your password.

## AWS CodeCommit

While AWS CodeCommit does offer not personal access tokens for authentication, an IAM Access Key ID and Secret Access Key can be used in place of a personal access token. 

The following [AWS CodeCommit IAM Policy actions](https://docs.aws.amazon.com/IAM/latest/UserGuide/list_awscodecommit.html) must be granted to an IAM user to create branches and/or pull requests in the Git Integration for Jira app:

*   `CodeCommit:Write:CreateBranch`
    
*   `CodeCommit:Write:CreatePullRequest`
    

To create a new Access Key ID and Secret Access Key, go to IAM ➜ Users ➜ Security credentials ➜ **Create access key**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/107380737/IAM-user-create-access-key-diagram.png?version=1&modificationDate=1650870599495&cacheVersion=1&api=v2&width=680&height=429)

AWS IAM only allows two Access Keys per IAM user.

We recommend that AWS administrators should not use the same IAM user's Access Key for the Git Integration for Jira app tasks.

* * *

## More how-to articles

*   Page:
    
    [Creating Personal Access Tokens](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Working with Custom API Path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Creating and configuring SSH keys (Windows/MacOS/Linux)](/wiki/spaces/GIJDC/pages/183271450) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Setting Project Permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions) (Git Integration for Jira Data Center)
    
*   Page:
    
    [How to get a quote?](/wiki/spaces/GIJDC/pages/1165721603) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Ways to Index Git Data to Jira Issues](/wiki/spaces/GIJDC/pages/1207828916/Ways+to+Index+Git+Data+to+Jira+Issues) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Proxy settings on adding integrations (except AWS CodeCommit)](/wiki/spaces/GIJDC/pages/1808007195) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Configure Source Code Diff Viewing](/wiki/spaces/GIJDC/pages/2054881287/Configure+Source+Code+Diff+Viewing) (Git Integration for Jira Data Center)