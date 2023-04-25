---

title: Setting Project Permissions
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- HOW TO ARTICLES -->

## Introduction

By default - integrations (GitLab, GitHub, etc) and individual repositories are associated with all Jira projects. Jira administrators can limit which Jira projects are associated to integrations or individual repositories.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Related Features</b><br>
        Associating a Jira project with an integration or repository will limit repository content displaying in:<br><br>
        <ul style='margin-bottom:-10px'>
            <li><b>Git Commits</b> issue tab</li>
            <li><b>Git Roll Up</b> issue tab</li>
            <li><b>Git integration</b> issue side panel</li>
            <li><b>View all repositories</b> page</li>
            <li><b>Repository Browser: Browse</b> page</li>
            <li><b>Repository Browser: Commits</b> page</li>
            <li><b>Repository Browser: Compare</b> page</li>
            <li><b>Create branch issue</b> dialog</li>
            <li><b>Create pull/merge request</b> dialog</li>
        </ul>
    </div>
    </div>
</div>
<br>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Jira users must have the <b>View Development Tools</b> permission in the context of a Jira project to view content from the Git Integration for Jira app.
    </div>
    </div>
</div>
<br>

## Instructions for integrations (GitLab, GitHub, etc)

To limit which Jira projects are associated with an integration's repositories:

1.  Navigate to Jira dashboard menu Git ➜ **Manage repositories.**

2.  Add a new integration or edit existing integration's settings.

3.  Locate the **Project Permissions** setting.

4.  Uncheck **Associate with all projects.**

5.  Select one or more Jira projects (at least one must be selected).

6.  Click **Update.**

<br>

### Video Example 1: Setting project permissions for an existing GitLab integration

<div class='embed-container' style='padding-bottom:75.21%'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/rnm5t639cz?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/rnm5t639cz'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

### Video Example 2: Setting project permissions at the repository level for an existing GitLab integration

<div class='embed-container' style='padding-bottom:75.21%'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/fder2qnpgw?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/fder2qnpgw'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<p>&nbsp;</p>

## Instructions for individual repositories

To limit which Jira projects are associated for individual repositories:

1.  Navigate to Jira dashboard menu Git ➜ **Manage repositories.**

2.  Add a new repository or edit existing repository's settings.

3.  Locate the **Project Permissions** setting.

4.  Uncheck **Associate with all projects.**

5.  Select one or more Jira projects (at least one must be selected).

6.  Click **Update.**


### Video Example: Setting project permissions for a repository

<div class='embed-container' style='padding-bottom:75.21%'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/xvzj32nxou?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/xvzj32nxou'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

<p>&nbsp;</p>

## More How-to articles

[How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed/)

**Setting Project Permissions** (this page)

[How to create a HAR file and send it to support for analysis](/git-integration-for-jira-data-center/how-to-create-a-har-file-and-send-it-to-support-for-analysis-gij-self-managed/)

[Working with Custom API Path](/git-integration-for-jira-data-center/Working-with-Custom-API-Path-gij-self-managed)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

[Creating and configuring SSH keys (Windows/MacOS/Linux)](/git-integration-for-jira-data-center/creating-and-configuring-ssh-keys-windows-macos-linux-gij-self-managed)

[Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/Require-Personal-Access-Tokens-for-user-actions-(create-branch-pull-request)-gij-self-managed)

[Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/Ways-to-Index-Git-Data-to-Jira-Issues-gij-self-managed)

[Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/Proxy-settings-on-adding-integrations-(except-AWS-CodeCommit)-gij-self-managed)

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

