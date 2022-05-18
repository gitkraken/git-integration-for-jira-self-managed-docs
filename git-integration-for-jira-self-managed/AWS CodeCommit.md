---

title: AWS CodeCommit
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Using **Jira Cloud**? [See the corresponding article](/wiki/spaces/GITCLOUD/pages/86180077/AWS+CodeCommit).

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/aws-cc-logo.png?version=1&modificationDate=1631448492185&cacheVersion=1&api=v2&width=387&height=81)

# Integrate AWS CodeCommit with Jira Server

AWS CodeCommit is a git host service by Amazon Web Services to store and manage source code, related files and private Git repositories in the cloud.

You can use the AWS CLI or the AWS CodeCommit console to track and manage your repositories.


Quickly learn how to connect AWS CodeCommit git repositories via Git Integration for Jira Server.


**What’s on this page:**

* * *

## Required permissions

IMPORTANT

Before performing an AWS CodeCommit integration, make sure to configure the recommended permissions.

The permissions detailed in the connect/Auto-connect wizard are necessary for specific features to work.

We recommend that the following AWS IAM policies are configured beforehand based on what features that will be used.

Configure [**AWSCodeCommitReadOnly »**](http://docs.aws.amazon.com/codecommit/latest/userguide/access-permissions.html) IAM policy for basic features:

|     |     |
| --- | --- |
| **Feature** | **Required permission** |
| show commits, process smart commits, show branches | `codecommit:ListRepositories`  <br>`codecommit:GitPull`  <br>`codecommit:BatchGetRepositories` |
| show pull requests | `codecommit:ListPullRequests`  <br>`codecommit:GetPullRequest` |

#### All features

Configure [**AWSCodeCommitPowerUser »**](https://docs.aws.amazon.com/codecommit/latest/userguide/auth-and-access-control-permissions-reference.html) IAM policy for all features:

|     |     |
| --- | --- |
| **Feature** | **Required permission** |
| create pull request | `codecommit:CreatePullRequest` |
| create branch | `codecommit:CreateBranch` |
| delete branch | `codecommit:DeleteBranch` |
| configure webhooks automatically | `codecommit:GetRepositoryTriggers`  <br>`codecommit:PutRepositoryTriggers`  <br>`sns:CreateTopic`  <br>`sns:DeleteTopic`  <br>`sns:Subscribe` |

See [this article](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens#CreatingPersonalAccessTokens-AWSCodeCommit) for related information.

## Webhooks and triggers

RECOMMENDED

CodeCommit doesn't have webhooks but it has SNS triggers requiring a [**subscription confirmation »**](https://docs.aws.amazon.com/sns/latest/dg/SendMessageToHttp.html).

For webhooks to work automatically, the IAM user used to setup the connection must have the [_configure webhooks automatically_](#All-features) permissions (_see Required permissions above – under IAM policy for_ all features). If permissions has not been set, the repositories are connected but no webhooks are created.

While the new UI is not fully functional in AWS CodeCommits, users are required to create triggers via the old UI or with the API.

**Shorthand**
With an existing AWS CC repository, enable triggers then create an SNS topic and subscribe to that topic.


For more information on Amazon SNS, see [**Amazon SNS: Getting Started »**](https://docs.aws.amazon.com/sns/latest/dg/sns-getting-started.html).

_Right click_ [_**here**_](https://bigbrassband.wistia.net/medias/657k3pibj6) _to open this video in a new tab/window for more viewing options._

## Using Auto-Connect integration

This process requires an AWS account with existing CodeCommit repositories.

We recommend using the Auto-connect integration panel (_Add new integration_) to connect multiple repositories from your AWS CodeCommit git host.

1.  On the Jira Server dashboard menu, go to Git ➜ **Manage repositories**. The git configuration page for connecting repositories is displayed.

2.  ![](https://bigbrassband.atlassian.net/wiki/download/attachments/92176493/gitserver-gitmgr-connect2git-sel(c).png?version=1&modificationDate=1631448492192&cacheVersion=1&api=v2)

    On the Auto-connect integration panel, click **CodeCommit**. The Auto-Connect wizard for AWS CodeCommit is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-gitmgr-auto-connect-aws-wiz-dlg(c).png?version=1&modificationDate=1631448492197&cacheVersion=1&api=v2&width=646&height=472)
    1.  Select the **Region** where the CodeCommit repositories reside then enter credentials for the **Access key ID** and **Secret access key**.

    2.  See below on the supported regions:

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

        *   Asia Pacific (Mumbai)

        *   Asia Pacific (Singapore)

        *   Asia Pacific (Sydney)

        *   Asia Pacific (Seoul)

        *   Asia Pacific (Tokyo)

        *   Asia Pacific (Hong Kong)

        *   Middle East (Bahrain)

        *   South America (Sao Paulo)

    3.  Configuring the **Advanced** settings (_under the credential fields_) is optional. However, admins/power users may set how the project listing is displayed.

        ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-aws-auto-connect-wiz-advanced-opt(c).png?version=1&modificationDate=1631448492201&cacheVersion=1&api=v2&width=510&height=224)
        1.  **Fetch refspec**  –  Git refspec contains patterns mapped as references from the remote to the local repository.
            For more information, see [**Git Internals -- The Refspec**](https://git-scm.com/book/en/v2/Git-Internals-The-Refspec).

            1.  The first two refspec options are required.

            2.  The rest of the options are OPTIONAL:

                1.  **Clone and index ref notes (refs/notes)** – This is a reference to `refs/notes/*` used for fetching. This option is enabled by default. This affects git notes which are not shown:

                    *   ...when `refs/notes` are disabled on connecting a repository.

                    *   ...when a new note comes when `refs/notes` is disabled.

                2.  **Clone and index changes (refs/changes)** – This is a reference to `refs/changes/*` used for fetching. This option is turned off by default.

                3.  **Clone and index other refs** – This is a user-defined list of references used for fetching. It is a comma-separated list with the format:

                    *   `+refs/refname1/*:refs/refname1/*`, `refs/refname2/*:refs/refname2/*`, ...

3.  Click **Connect**.

4.  On the following screen, Git Integration for Jira app will read all available repositories from your AWS CodeCommit account. Click **Import repositories**.

    *   Repositories of the logged-in AWS CodeCommit user can be automatically connected to Jira Server.  Repositories that are added or removed from AWS CodeCommit will be likewise connected or disconnected from Jira Server.

5.  After the import process, the **Settings** dialog is displayed:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-auto-connect-wizard-end-dlg(c).png?version=1&modificationDate=1631448492206&cacheVersion=1&api=v2&width=646&height=428)
    *   On the **Integration Settings**, setting the _**Require User PAT**_ option to `ON`, will require users to provide AWS Access Key ID and Secret Access Key specific for branch and pull requests creation/deletion _(via the_ [_Jira Git integration development panel_](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel) _on the Jira issue page)_. For more information on this feature, see [Integration feature settings: Require user PAT](/wiki/spaces/GIJDC/pages/317390849).

    *   Set [Smart commits](/git-integration-for-jira-self-managed/Smart-commits) and [Repository Browser](/git-integration-for-jira-self-managed/Repository-Browser) to enable/disable these features.

    *   Set **Project Permissions** according to your organization's project association rules. For detailed information, see [Setting project permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions).

6.  Click **Finish** to complete setting up this integration.



The AWS CodeCommit repositories are now connected to Jira Server.

The Git Integration for Jira Server app supports tracked folders for AWS CodeCommit git repositories. The connected git host is scanned for existing repository folders. The found repositories can then be added to the Git Repositories configuration.

There are two ways to configure the git repository connection using tracked folders with Git for Jira Server:

*   connect via **Auto-connect** integration panel ➜ **CodeCommit**, or

*   connect via **Connect to Git Repository** dropdown ➜ **Connect to AWS CodeCommit**.


If the connected git host has newly added repositories, the Git Integration for Jira app will automatically add them to the git repositories configuration on the next reindex. For the deleted git repositories, these will be removed from the Git repositories configuration on the next reindex.

## Single repository (Manually connect via HTTP or HTTPS)

The [Require user personal access token](/wiki/spaces/GIJDC/pages/317390849) feature is not available for single repository connections with AWS CodeCommit.

Connect a single AWS CodeCommit repository manually to Jira via HTTP/HTTPS connection.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/aws-repo-clone-url-sel.png?version=1&modificationDate=1631448492210&cacheVersion=1&api=v2&width=680&height=236)

1.  Use the Git clone HTTP/HTTPS URL of your AWS CodeCommit repository and paste it on the **Repository location** field on the Connect to Git repository wizard start screen.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-connect2git-aws-start(c).png?version=1&modificationDate=1631448492214&cacheVersion=1&api=v2&width=646&height=510)
2.  On the Authentication screen, enter the _**Access Key ID**_ as the username then the _**Secret Access Key**_ as the password.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-connect2git-aws-auth(c).png?version=1&modificationDate=1631448492219&cacheVersion=1&api=v2&width=646&height=427)
3.  Click **Next**. The wizard will verify the authentication details and proceeds to the next screen if there are no errors.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-connect2git-aws-settings-end(c).png?version=1&modificationDate=1631448492223&cacheVersion=1&api=v2&width=646&height=428)
4.  On the **Permissions** dialog, set **Repository Browser** and **Project Association** permissions or leave them as is.

5.  Click **Finish** to complete setting up this connection.


The repository is now connected to Jira Server.

## Single repository (Manually connect via SSH)

_Right click_ [_**here**_](https://bigbrassband.wistia.net/medias/xq1xzic0tm) _to open this video in a new tab/window for more viewing options._

The [Require user personal access token](/wiki/spaces/GIJDC/pages/317390849) feature is not available with single repository connections for AWS CodeCommit.

Connect a single AWS CodeCommit repository manually to Jira via SSH connection.

SSH connections are handled automatically if the PUBLIC KEY was added in the AWS IAM console and the associated PRIVATE KEY was added/uploaded on the Jira side (_Git Integration for Jira_ ➜ **SSH Keys** ➜ **Add SSH Key**).

If authentication issues are encountered during connecting an AWS repository to Jira, modify the original URL by inserting the **SSH Key ID** as the username. The **SSH Key ID** is an alphanumeric sequence provided by AWS IAM when importing a PUBLIC KEY for a particular user account in IAM.

For example, the original URL is:

```java
ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/test-repo
```


If the SSH Key ID **1a2b3c4d5e** is applied to the original SSH URL, the resulting URL would be:

```java
ssh://1a2b3c4d5e@git-codecommit.us-east-1.amazonaws.com/v1/repos/test-repo
```


The modified URL can now be used as a valid repository URL via _Git Integration for Jira_ ➜ **Connect to Git repository**.

## Setting up AWS CodeCommit web links

The Git Integration for Jira app automatically configures web linking for AWS CodeCommit repositories in Jira Server.

## Viewing git commits in Jira Server

1.  Perform a git commit by adding the Jira issue key in the commit message. This will associate the commit to the mentioned Jira issue.

2.  Open the Jira issue.

3.  Scroll down to the _**Activity**_ panel then click the **Git Commits** tab.

4.  Click **View Full Commit** to view the code diff.


## Working with branches and pull requests

This section requires the necessary permissions for [all features](#All-features).

The Git Integration for Jira app supports creation of branches and pull requests from Jira via the developer panel.

**Default branch**
Most git integrations allow changing of the default branch of the repository/project other than "master". This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex. Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level.

Main branch for repositories within an integration can only be changed on the git server.

### Creating branches

1.  On your Jira Server, open a Jira issue.

2.  On the Jira development panel under **Git integration**, click **Create branch**. The following dialog is displayed,

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-branch-dlg(c).png?version=1&modificationDate=1631448492228&cacheVersion=1&api=v2&width=544&height=300)
    1.  Select a **Repository** from the list.
        If there are several repositories with the same name, the listed GitLab repositories will have their names attached with a GitLab owner name.  For example, `johnsmith/second-webhook-test-repo`.

    2.  Choose a **Base branch** (usually _**master**_).

    3.  Enter a **Branch name** or leave it as is (recommended).

3.  Click **Create branch** to complete this process. The newly-created branch appears on the development panel under _Branches_ section.


![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-branches-list-dev-panel.png?version=1&modificationDate=1631448492233&cacheVersion=1&api=v2&width=331&height=294)

### Creating branches with Require user PAT enabled

If the [Require user PAT setting](/wiki/spaces/GIJDC/pages/317390849) is enabled in the **Integration feature settings** (![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Actions_ ➜ _Edit integration feature settings_) and a user PAT isn't configured yet for the selected repository via Repository Browser, the following create branch dialog is displayed instead.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-branch-req-user-pat-enabled-aws.png?version=1&modificationDate=1631448492238&cacheVersion=1&api=v2&width=550&height=275)

Click the link label to setup the PAT. The Setup your AWS Credentials dialog appears.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-branches-setup-pat-dlg-aws.png?version=2&modificationDate=1631448492444&cacheVersion=1&api=v2&width=550&height=275)

Enter the required credentials then click **Update** to complete this setup. You can now proceed to create branches and pull requests for the selected repository.

If an invalid secret access key was configured for the selected repository, the branch and pull request creation process will fail.

### Creating pull requests

The pull request feature works the same as merge request.

1.  On your Jira Server, open the Jira issue where you previously created a branch.

2.  On the development panel under **Git integration**, click **Create pull request**. The following dialog is displayed.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-pullreq-aws(c).png?version=1&modificationDate=1631448492247&cacheVersion=1&api=v2&width=544&height=309)
    1.  Select **Repository** from the list.

    2.  If there are several repositories with the same name, the listed AWS CodeCommit repositories will have their names attached with an AWS CodeCommit owner name.  For example, `johnsmith/second-webhook-test-repo`.

    3.  Choose the newly-created branch as the **Source branch**.

    4.  Set _**master**_ as the **Target branch**.

    5.  Enter a descriptive title or leave it as is (recommended).

    6.  OPTIONAL Click **Preview** to open this pull request in the Repository Browser ➜ Compare tab. See [this page](/wiki/spaces/GIJDC/pages/1930398705) for more information.

3.  Click **Create** to complete creating this pull request.


The pull request is listed on the developer panel of the Jira issue page.

The pull request is also ready for approval by the reviewers in your AWS CodeCommit web portal.

### Creating pull request with Require user PAT setting enabled

If the [Require user PAT setting](/wiki/spaces/GIJDC/pages/317390849) is enabled in the **Integration feature settings** (![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Actions_ ➜ _Edit integration feature settings_) and a user PAT isn't configured yet for the selected repository via Repository Browser, the following pull request dialog is displayed instead.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-pullreq-dlg-reqPAT.png?version=1&modificationDate=1631448492252&cacheVersion=1&api=v2&width=550&height=275)

Click the link label to setup the PAT. The Setup your AWS Credentials dialog appears.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-create-branches-setup-pat-dlg-aws.png?version=2&modificationDate=1631448492444&cacheVersion=1&api=v2&width=550&height=275)

Enter the required credentials then click **Update** to complete this setup. You can now proceed to create branches and pull requests for the selected repository.

If an invalid secret access key was configured for the selected repository, the branch and pull request creation process will fail.

## Updating Require User PAT data

If the secret access key has changed for your AWS account, update the credentials via Repository Browser (_dashboard menu Git_ ➜ _View all repositories_).

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/92176493/gitserver-repo-browser-setup-pat-sel.png?version=1&modificationDate=1631448492486&cacheVersion=1&api=v2&width=680&height=308)

Click the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) edit icon under the Personal access column for the selected repository. The same dialog for Setup your AWS Credentials appears. Enter the updated _**Secret access key**_ then click **Update** to save the settings.

## More integration guides

*   Page:

    [Integration Basics](/git-integration-for-jira-self-managed/Integration-Basics) (Git Integration for Jira Data Center)

*   Page:

    [GitHub.com](/wiki/spaces/GIJDC/pages/91979804/GitHub.com) (Git Integration for Jira Data Center)

*   Page:

    [GitHub Enterprise Server](/wiki/spaces/GIJDC/pages/91914350/GitHub+Enterprise+Server) (Git Integration for Jira Data Center)

*   Page:

    [GitLab CE/EE](/wiki/spaces/GIJDC/pages/91947056) (Git Integration for Jira Data Center)

*   Page:

    [GitLab.com](/wiki/spaces/GIJDC/pages/91881531/GitLab.com) (Git Integration for Jira Data Center)

*   Page:

    [Azure DevOps | Visual Studio Team Services (VSTS)](/wiki/spaces/GIJDC/pages/92176406) (Git Integration for Jira Data Center)

*   Page:

    [Azure DevOps Server | Team Foundation Services (TFS)](/wiki/spaces/GIJDC/pages/91979843) (Git Integration for Jira Data Center)

*   Page:

    [AWS CodeCommit](/git-integration-for-jira-self-managed/AWS-CodeCommit) (Git Integration for Jira Data Center)

*   Page:

    [Gerrit](/wiki/spaces/GIJDC/pages/91979855/Gerrit) (Git Integration for Jira Data Center)

*   Page:

    [Bitbucket Server](/git-integration-for-jira-self-managed/Bitbucket-Server) (Git Integration for Jira Data Center)

*   Page:

    [Bonobo](/wiki/spaces/GIJDC/pages/91947111/Bonobo) (Git Integration for Jira Data Center)

*   Page:

    [Windows Network | Server Share](/wiki/spaces/GIJDC/pages/91881564/Windows+Network+%7C+Server+Share) (Git Integration for Jira Data Center)

*   Page:

    [Tracked Folders](/git-integration-for-jira-self-managed/Tracked-Folders) (Git Integration for Jira Data Center)