---

title: Integration basics - Creating branches and pull | merge requests (Basics)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
The Git Integration for Jira app adds two features on the Jira issue developer panel – **Create Branch**, and **Create Pull/Merge Request**. For more information about the developer panel, see the [Jira Git Integration Developer Panel](/git-integration-for-jira-data-center/jira-git+-integration-development-panel-gij-self-managed/) documentation.

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

For detailed information on this feature, see [Creating branches from Jira](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/)).

## Creating pull/merge requests

Open a Jira issue then on the developer panel, click **Create pull/merge request** label to create a pull/merge request for the selected repository.

For detailed information on this feature, see [Creating pull/merge requests from Jira](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/).

