---

title: GitLab.com
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <b>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/gitlab-com/'>See the corresponding article</a>.
    </div>
    </div>
</div>

# Integrate GitLab.com with Jira Server/Data Center

<img src='https://bigbrassband.com/confluence/images/gitlab_wm_no_bg.png' width=240 height=91 />

<br>

GitLab introduced personal access tokens (PAT) since version 8.8 and now (v10+) prefers this type of authentication for accessing the git repositories. Service users are strongly advised to switch from using username/password to using Personal Access Tokens (PAT) for GitLab.com.

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        We are dropping support for Gitlab API v3. Please use <b>GitLab API v4</b> when adding new integrations for increased security.
    </div>
    </div>
</div>
<br>

Quickly learn how to connect GitLab.com git repositories via Git Integration for Jira app.

**What's on this page:**

  
* * *

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/eqwv6puk4k?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/eqwv6puk4k'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

## Permissions

GitLab can have users with different access level to a group or project. If the user's connected GitLab repositories to Jira are not accessible or commits are not showing for that user -- it's related to permission issues. This can be a per user, repository or a project level restriction.

If you encounter access permission issues, you will need to ask your Git administrator to grant you the required level of access to specific projects. If you are a Git administrator, you will need to setup a GitLab user with the minimum required permissions to view GitLab projects from Jira.

Take the following cases for example:

*   The personal access token (PAT) that the GitLab user provided doesn't have the correct permisions within GitLab to view source code for specific repositories.
*   The GitLab user doesn't have access privileges to a GitLab repository or is not a member of a group that has access to specific repositories.

We recommend creating a specific GitLab user for the integration. This way, the GitLab user can have specific permissions to do the given tasks.

![](https://bigbrassband.com/images/bbb/gitlab-member-role-screen.png)

**For minimum access (read-only) permissions:**

1.  Set the user account profile's PAT scope to **read repository**.
2.  The GitLab user is set to only **read** a specific repository. Set to **Reporter** role.

This level of access allows the user to view commits for the specific repository.

<br>

**For users who will be tasked with creating branches and merge requests:**

1.  Set the user account profile's PAT scope to **api**.
2.  The GitLab user should be set to **read/write** access for the specific repository. Set to **Developer** role.

This level of access allows the user to create/delete branches and create merge requests.

For more information, see [**GitLab Permissions »**](https://docs.gitlab.com/ee/user/permissions.html "GitLab User Documentation - Permissions").

## **Creating a Personal Access Token**

If two-factor authentication is enabled for your GitLab account, you will need to create a PAT to access your git repositories. Enable two-factor authentication in your GitLab.com account for increased security.

While instructions from GitLab works just fine, [follow this article](/git-integration-for-jira-self-managed/creating-personal-access-tokens#gitlab--gitlab-ceee) for some specific instructions to get you started.

## Using Auto-Connect

This process requires an existing GitLab.com account. Multiple git repositories in a GitLab.com account will be connected via Git Integration for Jira app.

While instructions from GitLab works just fine, here are some specific instructions to get you up and running.

We recommend using the Auto-connect integration panel to connect multiple repositories from your GitLab.com account.

1.  Go to **Manage Git Repositories** (_Dashboard_ ➜ **Git** menu) in Jira Server/Data Center.

2.  Click **GitLab** in the Auto-connect integration panel.

3.  GitLab.com is selected by default. Paste the personal access token in the provided field.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/gitserver-gitlab-autoconnect-dlg(c).png?api=v2)

    Configuring the **Advanced** settings is optional. However, admins/power users may set  how the project listing is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/gitserver-general-advanced-autoconnect-opt(c).png?api=v2)
    
    *   **Custom API Path**  –  this is a relative path that starts with "/". The maximum allowed length is 2000 characters or less. The integration will use the relative REST API path to retrieve the list of tracked repositories. For more information on GitLab custom API paths, see [**GitLab API**](https://docs.gitlab.com/ee/api/projects.html). To learn more examples, see article [Jira Server/Data Center: Working with Custom API Path](/git-integration-for-jira-self-managed/working-with-custom-api-path/).

    ```bash
    GitLab version API support:
    ---------------------------
    Gitlab v9.5 and above -- only API v4
    Gitlab v9.0 to v9.4.x -- API v4 (support for API v3 is deprecated)
    ```
    ![](https://bigbrassband.atlassian.net/wiki/s/1809036785/6452/b2c29440e6bad88b92f3d3fb442795ae33975e0e/_/images/icons/emoticons/information.png) **Remember!** The GitLab.com API can see all the public projects. For GitLab.com, we recommend using JMESPath over the Custom API path when possible.
        *   
    *   **JMESPath filter**  –  JMESPath is a query language for JSON used to filter API results and to limit which repositories are integrated. The maximum allowed length is 2000 characters or less. Read about JMESPath expressions on their [website](http://jmespath.org/). For help with writing expressions, please contact [support](mailto:support@bigbrassband.com?subject=Help%20with%20writing%20JMESPath%20filter%20expressions). To learn more examples, see article [Jira Server/Data Center: Working with JMESPath Filters](/git-integration-for-jira-self-managed/working-with-jmespath-filters/).

    While Custom API Path and JMESPath filter are mutually exclusive, you can use one, the other, both or neither.

4. Click **Connect**.

5. On the following screen, the Git Integration for Jira app will read all available repositories from your GitLab account. Click **Import repositories**.

    Repositories of the logged-in GitLab user can be automatically connected to Jira Server/Data Center.  Repositories that are added or removed from GitLab will be likewise connected or disconnected from Jira Server/Data Center.

    On the first connection of this integration, the first 30 repositories are displayed in the list for import. The entire repository list can be viewed via Manage repositories ➜ **Actions** ➜ **Show integration repositories**.

6. After the import process, enable/disable **_integration settings_** and set **Project Permissions** according to your organization's rules:

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/gitserver-auto-connect-wiz-settings-screen(c).png?api=v2)

   *   On the Integration Settings, setting the **_Require User PAT_** option to `ON`, will require users to provide PAT specific for branch and merge requests _(via the [developer panel](/git-integration-for-jira-self-managed/jira-git-integration-development-panel/ "Git add-on documentation - Jira developer panel") on the Jira issue page)_. For more information on this feature, see [Integration Settings: Require User PAT](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request/).
   
   *   Set **Smart Commits** and **Repository Browser** to enable/disable these features.
  
   *   Set **Project Permissions** according to your organization's project association rules.

7. Click **Finish**.

The GitLab.com git repositories are now connected to Jira Server/Data Center.

There will be a slight delay in adding 2FA-enabled repositories compared to others. These will show in the git configuration list eventually.

## **Single Repository (Manual integration)**

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This section is for users who are using SSH connections or those who wanted to only connect a single specific repository.
    </div>
    </div>
</div>

This process requires an existing GitLab git repository. Look for the the GitLab repository URL on the repository project page. Choose between SSH or HTTPS.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/image-20211209-101005.png?api=v2)

Use this information to connect the GitLab git repository to your Jira Server/Data Center via Git Integration for Jira app:

1.  On your Jira dashboard menu, go to **Git** ➜ **Manage repositories**.
2.  Click **Connect to Git Repository** to open the Connect Wizard.
3.  Paste the URL from GitLab in the provided box.
4.  Continue to the next step by following the screen instructions.
5.  Click **Finish** to complete this process. 

The repository is now connected to Jira Server/Data Center. There will be a slight delay in adding 2FA-enabled repositories compared to others. These will show in the git configuration list eventually.

## **Setting Up GitLab Web Links**

The Git Integration for Jira app automatically configures web linking for GitLab git repositories.

## **Working with Branches and Merge Requests with GitLab**

This process requires a GitLab git repository and a PAT with **`api`** scope.

For GitLab Group, the user must have the **Write** permissions and the **`api`** PAT scope.

### **Default Branch**

Most git integrations allow changing of the default branch of the repository/project other than "master".  This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex.  Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Main branch for repositories within an integration can only be changed on the git server.
    </div>
    </div>
</div>

### **Creating Branches**

1. On your Jira Server/Data Center, open a Jira issue. On the Jira developer panel under **Git integration**, click **Create Branch**.

2. The following dialog is displayed:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/gitserver-create-branches-dlg(c).png?api=v2)

*   Select a **Repository** from the list.

If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, **`johnsmith/second-webhook-test-repo`**.

*   Choose a **Base branch**.
*   Enter a **Branch name** or leave it as is (recommended).

If the [**Require User PAT option**](/git-integration-for-jira-self-managed/require-personal-access-tokens-for-user-actions-create-branch-pull-request/) is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/gitserver-create-branches-dlg-req-userPAT(c).png?api=v2)

*   Click the link label to setup the PAT.  This will show the Repository Browser listing connected git repositories.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/55312520/gitserver-setup-pat-dlg(c).png?api=v2)

*   Click 
     to setup a PAT for the selected repository. Paste a valid PAT of the current user to proceed. Invalid PATs will fail the branch creation process.

*   Click the 
    icon to use this PAT and save it to the current user profile. Otherwise, click the 
    icon on the right to cancel setting up PAT for this repository.

*   After the above steps have been taken, the users will be able to proceed with branch creation.

3\. Click Create Branch.  The newly-created branch is now listed in the developer panel under **Branches**.

Perform a commit to the newly-created branch to be ready for merge.

### **Creating Merge Request**

The merge request feature works the same as pull request.

To create a merge request and merge it to the main source (master):

1. On your Jira Server/Data Center, open the Jira issue where your previously created a branch.

2\. On the developer panel under **Git Source Code**, click **Create Merge Request**.

3\. The following dialog is displayed:

![](https://bigbrassband.com/images/bbb/jira-server-issue-merge-request-dialog.png)

*   Select a **Repository** from the list.

If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name. For example, **`johnsmith/second-webhook-test-repo`**.

*   Choose the newly-created branch as the **Source branch**.
*   Set **_master_** as the **Target branch**.
*   Enter a descriptive title or leave it as is _(recommended)_.

If the **[Require User PAT option »](/wiki/spaces/GIJDC/pages/92078126/Integration+Basics#IntegrationBasics-RequireUserPat)** is enabled in the Integration Settings and a user PAT isn't configured yet for the selected repository via Repository Browser, the following dialog is displayed instead:

![](https://bigbrassband.com/images/bbb/jira-server-issue-merge-req-dlg-cfg-pat.png)

If an invalid PAT was configured for the selected repository, the merge request creation process will fail.

4. Click Create to create the merge request.

The merge request is listed on the developer panel of the Jira issue page.

The merge request is also ready for approval by the reviewers in your GitLab web portal.

## **Viewing Git Commits in Jira Data Center**

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.
2.  Open the Jira issue.
3.  Scroll down to the **_Activity_** panel then click the **Git Commits** tab.
4.  Click **View Full Commit** to view the code diff.


* * *

^1^ _Logo owned by [GitLab Inc](https://gitlab.com/) used under [license](https://creativecommons.org/licenses/by-nc-sa/4.0/)_.