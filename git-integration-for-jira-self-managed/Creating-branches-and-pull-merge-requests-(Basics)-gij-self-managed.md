---

title: Creating branches and pull/merge requests (Integration basics)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The Git Integration for Jira app adds two features on the Jira issue developer panel – **Create Branch**, and **Create Pull/Merge Request**. For more information about the developer panel, see the [Jira Git Integration Developer Panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed) documentation.

## Default branch

Most git integrations allow changing of the default branch of the repository/project other than `master`. This change is reflected in the  Repository Settings of the Git Integration for Jira app on the next reindex. Auto-connected integrations support this feature where Git Integration for Jira app gets the default branch from almost all integrations and apply this setting at repository level. For the case with Gerrit, the default main branch is always `master`.

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

## Creating branches

Open a Jira issue then on the developer panel, click **Create Branch** label to create a branch for the selected repository.

For detailed information on this feature, see [Creating branches from Jira](/git-integration-for-jira-data-center/creating-branches-gij-self-managed)).

## Creating pull/merge requests

Open a Jira issue then on the developer panel, click **Create pull/merge request** label to create a pull/merge request for the selected repository.

For detailed information on this feature, see [Creating pull/merge requests from Jira](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed).

## More related articles on integration basics

[Connecting to a git host account via Add new integration panel](/git-integration-for-jira-data-center/connecting-to-a-git-host-account-via-Add-new-integration-panel-gij-self-managed)

[Connecting to a single git repository (HTTPS | SSH)](/git-integration-for-jira-data-center/connecting-to-a-single-git-repository-(HTTPS-SSH)-gij-self-managed)

[Setting up web links](/git-integration-for-jira-data-center-gij-self-managed/setting-up-web-links-gij-self-managed)

[Link git commits to Jira issues (Basics)](/git-integration-for-jira-data-center/Link-git-commits-to-Jira-issues-(Basics)-gij-self-managed)

[Using smart commits](/git-integration-for-jira-data-center/using-smart-commits-gij-self-managed)

[Using the Repository Browser](/git-integration-for-jira-data-center/using-the-repository-browser-gij-self-managed)

**Creating branches and pull/merge requests** (this page)

