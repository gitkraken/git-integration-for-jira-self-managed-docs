---

title: AWS CodeCommit
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Using <b>Jira Cloud</b>? <a href='/git-integration-for-jira-cloud/aws-codecommit-gij-cloud'>See the corresponding article</a>.
    </div>
    </div>
</div>
<br>

<img src='/wp-content/uploads/gij-aws-cc-logo-banner.png' width=512 height=106 style='max-width:100%' />

<br>

# Integrate AWS CodeCommit with Jira Data Center/Server

AWS CodeCommit is a git host service by Amazon Web Services to store and manage source code, related files and private Git repositories in the cloud.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        You can use the AWS CLI or the AWS CodeCommit console to track and manage your repositories.
    </div>
    </div>
</div>
<br>

Quickly learn how to connect AWS CodeCommit git repositories via Git Integration for Jira Data Center/Server.

**What's on this page:**
- [Integrate AWS CodeCommit with Jira Data Center/Server](#integrateaws-codecommit-with-jira-data-centerserver)
  - [Required permissions](#required-permissions)
    - [Basic features](#basic-features)
    - [All features](#all-features)
  - [Webhooks and triggers](#webhooks-and-triggers)
  - [Using Full feature integration](#using-full-feature-integration)
  - [Single repository (Manually connect via HTTP or HTTPS)](#single-repository-manually-connect-via-http-or-https)
  - [Single repository integration (Manually connect via SSH)](#single-repository-integration-manually-connect-via-ssh)
  - [Setting up AWS CodeCommit web links](#setting-up-aws-codecommit-web-links)
  - [Viewing git commits in Jira Data Center/Server](#viewing-git-commits-in-jira-data-centerserver)
  - [Working with branches and pull requests](#working-with-branches-and-pull-requests)
    - [Default branch](#default-branch)
    - [Creating branches](#creating-branches)
    - [Creating branches with Require user PAT enabled](#creating-branches-with-require-user-pat-enabled)
    - [Creating pull requests](#creating-pull-requests)
    - [Creating pull request with Require user PAT setting enabled](#creating-pull-request-with-require-user-pat-setting-enabled)
  - [Updating Require User PAT data](#updating-require-user-pat-data)

<br>
<br>
<hr>
<br>
<br>

## Required permissions

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>IMPORTANT!</b><br>
        Before performing an AWS CodeCommit integration, make sure to configure the recommended permissions.
    </div>
    </div>
</div>
<br>

The permissions detailed in the connect/Auto-connect wizard are necessary for specific features to work.

We recommend that the following AWS IAM policies are configured beforehand based on what features that will be used.

### Basic features

Configure <a href='http://docs.aws.amazon.com/codecommit/latest/userguide/access-permissions.html' target='_blank'><b>AWSCodeCommitReadOnly »</b></a> IAM policy for basic features:

| Feature | Required permission |
| :--- | :--- |
| show commits, process smart commits, show branches | `codecommit:ListRepositories`  <br>`codecommit:GitPull`  <br>`codecommit:BatchGetRepositories` |
| show pull requests | `codecommit:ListPullRequests`  <br>`codecommit:GetPullRequest` |

### All features

Configure [**AWSCodeCommitPowerUser »**](https://docs.aws.amazon.com/codecommit/latest/userguide/auth-and-access-control-permissions-reference.html) IAM policy for all features:

| Feature | Required permission |
| :--- | :--- |
| create pull request | `codecommit:CreatePullRequest` |
| create branch | `codecommit:CreateBranch` |
| delete branch | `codecommit:DeleteBranch` |
| configure webhooks automatically | `codecommit:GetRepositoryTriggers`  <br>`codecommit:PutRepositoryTriggers`  <br>`sns:CreateTopic`  <br>`sns:DeleteTopic`  <br>`sns:Subscribe` |

See [this article](/git-integration-for-jira-data-center/creating-personal-access-tokens-gij-self-managed) for related information.

## Webhooks and triggers

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>RECOMMENDED</b>

CodeCommit doesn't have webhooks but it has SNS triggers requiring a [**subscription confirmation »**](https://docs.aws.amazon.com/sns/latest/dg/SendMessageToHttp.html).

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For webhooks to work automatically, the IAM user used to setup the connection must have the <a href='#All-features'><i>configure webhooks automatically</i></a> permissions (<i>see Required permissions above – under IAM policy for</i> <u>all features</u>). If permissions has not been set, the repositories are connected but no webhooks are created.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        While the new UI is not fully functional in AWS CodeCommits, users are required to create triggers via the old UI or with the API.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Shorthand</b><br>
        With an existing AWS CC repository, enable triggers then create an SNS topic and subscribe to that topic.
    </div>
    </div>
</div>
<br>

For more information on Amazon SNS, see <a href='https://docs.aws.amazon.com/sns/latest/dg/sns-getting-started.html' target='_blank'><b>Amazon SNS: Getting Started »</b></a>.

<br>

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/657k3pibj6?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/657k3pibj6'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>
<br>

## Using Full feature integration

This process requires an AWS account with existing CodeCommit repositories.

We recommend using the Add new integration panel (_formerly Auto-connect integration panel_) to connect multiple repositories from your AWS CodeCommit git host.

1.  On the Jira Data Center/Server dashboard menu, go to Git ➜ **Manage repositories**. The git configuration page for connecting repositories is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitmgr-connect2git-sel-c.png)

2. On the Add new integration panel, click **CodeCommit**. The Auto-Connect wizard for AWS CodeCommit is displayed.

    ![](/wp-content/uploads/gij-gitserver-gitmgr-auto-connect-aws-wiz-dlg-c.png)

3.  Select the **Region** where the CodeCommit repositories reside then enter credentials for the **Access key ID** and **Secret access key**.

    See below on the supported regions:

        *   US East (N. Virginia)
        *   US East (Ohio)
        *   US West (N. California)
        *   US West (Oregon)
        *   Canada (Central)
        *   EU (Ireland)
        *   EU (Frankfurt)
        *   EU (London)
        *   EU (Paris)
        *   EU (Stockholm)
        *   EU (Milan)
        *   EU (Spain)
        *   EU (Zurich)
        *   Asia Pacific (Hyderabad)
        *   Asia Pacific (Mumbai)
        *   Asia Pacific (Singapore)
        *   Asia Pacific (Sydney)
        *   Asia Pacific (Seoul)
        *   Asia Pacific (Tokyo)
        *   Asia Pacific (Hong Kong)
        *   Asia Pacific (Osaka)
        *   Asia Pacific (Jakarta)
        *   Middle East (Bahrain)
        *   Middle East (UAE)
        *   Africa (Cape Town)
        *   South America (Sao Paulo)

    <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>OPTIONAL!</b> Configuring the **Advanced** settings (_under the credential fields_) is not required. However, admins/power users may set how the project listing is displayed.

    ![](/wp-content/uploads/gij-gitserver-aws-auto-connect-wiz-advanced-opt-c.png)

    *   **Fetch refspec**  –  Git refspec contains patterns mapped as references from the remote to the local repository.
        For more information, see <a href='https://git-scm.com/book/en/v2/Git-Internals-The-Refspec'><b>Git Internals -- The Refspec</b></a>.

        *   The first two refspec options are required.

        *   The rest of the options are OPTIONAL:

            *   **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching. This option is enabled by default. This affects git notes which are not shown:

                *   ...when `refs/notes` are disabled on connecting a repository.

                *   ...when a new note comes when `refs/notes` is disabled.

            *   ***Clone and index changes (refs/changes)** – This is a reference to `refs/changes/*` used for fetching. This option is turned off by default.

            *   **Clone and index other refs** – This is a user-defined list of references used for fetching. It is a comma-separated list with the format:

                *   `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

4.  Click **Connect**.

5.  On the following screen, Git Integration for Jira app will read all available repositories from your AWS CodeCommit account. Click **Import repositories**.

    Repositories of the logged-in AWS CodeCommit user can be automatically connected to Jira Data Center/Server.  Repositories that are added or removed from AWS CodeCommit will be likewise connected or disconnected from Jira Data Center/Server.

6.  After the import process, the **Settings** dialog is displayed:

    ![](/wp-content/uploads/gij-gitserver-auto-connect-wizard-end-dlg-c.png)

    *   On the **Integration Settings**, setting the _**Require User PAT**_ option to `ON`, will require users to provide AWS Access Key ID and Secret Access Key specific for branch and pull requests creation/deletion _(via the_ [_Jira Git integration development panel_](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed) _on the Jira issue page)_. For more information on this feature, see [Integration feature settings: Require user PAT](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed).

    *   Set [Smart commits](/git-integration-for-jira-data-center/Smart-commits) and [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed) to enable/disable these features.

    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Setting project permissions](/git-integration-for-jira-data-center/setting-project-permissions-gij-self-managed).

7.  Click **Finish** to complete setting up this integration.

<br>

The AWS CodeCommit repositories are now connected to Jira Data Center/Server.

The Git Integration for Jira Data Center/Server app supports tracked folders for AWS CodeCommit git repositories. The connected git host is scanned for existing repository folders. The found repositories can then be added to the Git Repositories configuration.

There are two ways to configure the git repository connection using tracked folders with Git for Jira Data Center/Server:

*   connect via **Auto-connect** integration panel ➜ **CodeCommit**, or

*   connect via **Connect to Git Repository** dropdown ➜ **Connect to AWS CodeCommit**.

If the connected git host has newly added repositories, the Git Integration for Jira app will automatically add them to the git repositories configuration on the next reindex. For the deleted git repositories, these will be removed from the Git repositories configuration on the next reindex.

## Single repository (Manually connect via HTTP or HTTPS)

 <div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <a href='/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed'>Require user personal access token</a> feature is not available for single repository connections with AWS CodeCommit.
    </div>
    </div>
</div>
<br>

Connect a single AWS CodeCommit repository manually to Jira via HTTP/HTTPS connection.

![](/wp-content/uploads/gij-aws-repo-clone-url-sel.png)

1.  Use the Git clone HTTP/HTTPS URL of your AWS CodeCommit repository and paste it on the **Repository location** field on the Connect to Git repository wizard start screen.

    ![](/wp-content/uploads/gij-gitserver-connect2git-aws-start-c.png)

2.  On the Authentication screen, enter the _**Access Key ID**_ as the username then the _**Secret Access Key**_ as the password.

    ![](/wp-content/uploads/gij-gitserver-connect2git-aws-auth-c.png)

3.  Click **Next**. The wizard will verify the authentication details and proceeds to the next screen if there are no errors.

    ![](/wp-content/uploads/gij-gitserver-connect2git-aws-settings-end-c.png)

4.  On the **Permissions** dialog, set **Repository Browser** and **Project Association** permissions or leave them as is.

5.  Click **Finish** to complete setting up this connection.


The repository is now connected to Jira Data Center/Server.

## Single repository integration (Manually connect via SSH)

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/xq1xzic0tm?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/xq1xzic0tm'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The <a href='/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed'>Require user personal access token</a> feature is not available with single repository connections for AWS CodeCommit.
    </div>
    </div>
</div>
<br>

Connect a single AWS CodeCommit repository manually to Jira via SSH connection.

SSH connections are handled automatically if the PUBLIC KEY was added in the AWS IAM console and the associated PRIVATE KEY was added/uploaded on the Jira side (_Git Integration for Jira_ ➜ SSH Keys ➜ **Add SSH Key**).

If authentication issues are encountered during connecting an AWS repository to Jira, modify the original URL by inserting the **SSH Key ID** as the username. The **SSH Key ID** is an alphanumeric sequence provided by AWS IAM when importing a PUBLIC KEY for a particular user account in IAM.

For example, the original URL is:

```powershell
ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/test-repo
```

If the SSH Key ID **1a2b3c4d5e** is applied to the original SSH URL, the resulting URL would be:

```powershell
ssh://1a2b3c4d5e@git-codecommit.us-east-1.amazonaws.com/v1/repos/test-repo
```


The modified URL can now be used as a valid repository URL via _Git Integration for Jira_ ➜ **Connect to Git repository**.

## Setting up AWS CodeCommit web links

The Git Integration for Jira app automatically configures web linking for AWS CodeCommit repositories in Jira Data Center/Server.

## Viewing git commits in Jira Data Center/Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.


## Working with branches and pull requests

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This section requires the necessary permissions for <a href='#all-features'>all features</a>.
    </div>
    </div>
</div>
<br>

The Git Integration for Jira app supports creation of branches and pull requests from Jira via the developer panel.

### Default branch

Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex. Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

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
<br>

### Creating branches

1.  On your Jira Data Center/Server instance, open a Jira issue.

2.  On the Jira development panel under **Git integration**, click **Create branch**. The following dialog is displayed,

    ![](/wp-content/uploads/gij-gitserver-create-branch-dlg-aws.png)

    *   Select a **Repository** from the list.
        
        If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name.  For example, `johnsmith/second-webhook-test-repo`.

    *   Choose a **Base branch** (usually _**master**_).

    *   Enter a **Branch name** or leave it as is (recommended).

3.  Click **Create branch** to complete this process.
  
The newly-created branch appears on the development panel under _Branches_ section.

<img src='/wp-content/uploads/gij-gitserver-create-branches-list-dev-panel.png' width=331 height=294 style='display:block;margin:25px auto;max-width:100%' />

<br>

### Creating branches with Require user PAT enabled

If the [Require user PAT setting](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) is enabled in the **Integration feature settings** _Actions_ ➜ _Edit integration feature settings_) and a user PAT isn't configured yet for the selected repository via Repository Browser, the following create branch dialog is displayed instead.

<img src='/wp-content/uploads/gij-gitserver-create-branch-req-user-pat-enabled-aws.png' width=550 height=275 style='display:block;margin:25px auto;max-width:100%' />

Click the link label to setup the PAT.

The Setup your AWS Credentials dialog appears.

<img src='/wp-content/uploads/gij-gitserver-create-branches-setup-pat-dlg-aws.png' width=550 height=275 style='display:block;margin:25px auto;max-width:100%' />

Enter the required credentials then click **Update** to complete this setup. You can now proceed to create branches and pull requests for the selected repository.

If an invalid secret access key was configured for the selected repository, the branch and pull request creation process will fail.

### Creating pull requests

The pull request feature works the same as merge request.

1.  On your Jira Data Center/Server instance, open the Jira issue where you previously created a branch.

2.  On the development panel under **Git integration**, click **Create pull request**. The following dialog is displayed.

    ![](/wp-content/uploads/gij-gitserver-create-pullreq-aws-c.png)

    *   Select **Repository** from the list.

        If there are several repositories with the same name, the listed AWS CodeCommit repositories will have their names attached with an AWS CodeCommit owner name.  For example, `johnsmith/second-webhook-test-repo`.

    *   Choose the newly-created branch as the **Source branch**.

    *   Set _**master**_ as the **Target branch**.

    *   Enter a descriptive title or leave it as is (recommended).

    *   <b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>OPTIONAL</b> -- Click **Preview** to open this pull request in the Repository Browser ➜ Compare tab. See [this page](/git-integration-for-jira-data-center/comparing-branches-tags-in-repository-browser-gij-self-managed) for more information.

3.  Click **Create** to complete creating this pull request.

The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your AWS CodeCommit web portal.

### Creating pull request with Require user PAT setting enabled

If the [Require user PAT setting](/git-integration-for-jira-data-center/require-personal-access-tokens-for-user-actions-create-branch-pull-request-gij-self-managed) is enabled in the **Integration feature settings** ( _Actions_ ➜ _Edit integration feature settings_) and a user PAT isn't configured yet for the selected repository via Repository Browser, the following pull request dialog is displayed instead.

<img src='/wp-content/uploads/gij-gitserver-create-pullreq-dlg-reqPAT-aws.png' width=550 height=275 style='display:block;margin:25px auto;max-width:100%' />

Click the link label to setup the PAT.

The Setup your AWS Credentials dialog appears.

<img src='/wp-content/uploads/gij-gitserver-create-branches-setup-pat-dlg-aws.png' width=550 height=275 style='display:block;margin:25px auto;max-width:100%' />

Enter the required credentials then click **Update** to complete this setup. You can now proceed to create branches and pull requests for the selected repository.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If an invalid secret access key was configured for the selected repository, the branch and pull request creation process will fail.
    </div>
    </div>
</div>
<br>

## Updating Require User PAT data

If the secret access key has changed for your AWS account, update the credentials via Repository Browser (_dashboard menu Git_ ➜ _View all repositories_).

![](/wp-content/uploads/gij-gitserver-repo-browser-setup-pat-sel.png)

Click the edit ![](/wp-content/uploads/gij-edit-icon-dark.png) icon under the Personal access column for the selected repository. The same dialog for Setup your AWS Credentials appears. Enter the updated _**Secret access key**_ then click **Update** to save the settings.

