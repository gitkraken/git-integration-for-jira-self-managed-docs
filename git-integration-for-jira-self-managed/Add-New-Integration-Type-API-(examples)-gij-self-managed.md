---

title: Add New Integration Type API (examples)
description: See example JSON request bodies for adding an integration of each supported Git host type through the Integration REST API.
product: Git Integration for Jira Data Center
feature: REST API
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [github, github-enterprise, gitlab, gitlab-self-managed, aws-codecommit, azure-devops, azure-devops-server, gerrit]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2024-06
llms_include: true
tags: [rest api, integration api, json examples, integration types, personal access tokens, tracked folders]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "rest-api-gij-self-managed"
    nav_label: "Add New Integration Type API (examples)"
    nav_order: 20
    nav_parent: "integration-api-gij-self-managed"
    page_type: "content"
---

> **Warning:** Only Jira admins can perform the Add New Integration Type API call.

<br>

Below are integration API examples for each integration types:

### url
`{JiraBaseURL}/rest/gitplugin/1.0/`**integration**

### method
POST

### Prameters

Request body is a JSON structure.

For complete reference of the parameters, see [Add New Integration API](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed/).

> **Tip:** When adding new repositories, we recommend to leave the <code>trustFolderStat</code> setting to <b>false</b> <i>(default)</i>. You can change this setting later on via <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit repository settings</b> in the Manage repositories page.

<br>


### GITHUB

```json
{
  "type": "GITHUB",
  "pat": "Sh#ft#t1Q6PDVm",
  "displayName": "johnsmith's GitHub via API"
}
```

<br>

### GITHUB ENTERPRISE

```json
{
  "type": "GITHUB_SERVER",
  "displayName": "GitHub Ent. via API -- pat",
  "origin": "https://mygithub.yourorg.com",
  "pat": "330sw9nqs1ges2osiffl4lzb6bm65ejbeua4rsju",
  "disableSslVerification": true
}
```

<br>

### GITLAB

```json
{
  "type": "GITLAB",
  "pat": "AvTfLwSd6wBoK6bSPzks",
  "displayName": "MY GITLAB"
}
```

<br>

### GITLAB CE/EE (Legacy)

```json
{
  "type": "GITLAB_SERVER_LEGACY",
  "displayName": "GITLAB_SERVER v.3 Legacy",
  "username": "gitlabadmin",
  "password": "G4eeNPpNK82d",
  "origin": "http://mygitlab.yourorg.com/"
}
```

<br>

### GITLAB CE/EE

```json
{
  "type": "GITLAB_SERVER",
  "displayName": "GITLAB_SERVER v.4",
  "origin": "http://mygitlabserver.yourorg.com",
  "pat": "7yz0b4sa8f3g59kaz7wn"
}
```

<br>

### AWS CODECOMMIT

```json
{
  "type": "AWS",
  "username": "AHMY0OGWY8RX3RB1SXTU",
  "password": "YupPNQD8fyREjfkHrY8KqmYNz7c5QzWPubqSw2az",
  "awsRegion": "us-east-1"
}
```

<br>

### AZURE

```json
{
  "type": "AZURE",
  "pat": "vuxz5i9kn2pqrr2culs0j2kryxqu38myg8i5s0t3gp86h47wb6ft"
}
```

<br>

### VSTS

```json
{
  "type": "VSTS",
  "pat": "vuxz5i9kn2pqrr2culs0j2kryxqu38myg8i5s0t3gp86h47wb6ft",
  "displayName": "Visual Studio Ent."
}
```

<br>

### TFS

```json
{
  "type": "TFS_SERVER",
  "displayName": "TFS 2018 via API",
  "origin": "http://tfs2018.yourorg:8080/tfs",
  "username": "tfsadmin",
  "password": "I26C953WPmNbFr7hp3eosf$Z68PcXAHe"
}
```

<br>

### AZURE DEVOPS

```json
{
  "type": "AZURE_DEVOPS",
  "displayName": "Azure Devops (TFS 2019) via API",
  "origin": "http://myazuredevops.yourorg.com/",
  "username": "adevopsadmin",
  "password": "G6Dz6BuUGKh5lo%Zh#cJm#0QdN@#fZ8#"
}
```

<br>

### TRACKED FOLDER

```json
{
  "type": "FILESPACE",
  "displayName": "Tracked folder via API",
  "origin": "D:\\tmp\\*"
}
```

<br>

### GERRIT

> **Warning:** <b>Note</b><br>
> The origin field parameter is required.

```json
{
  "origin": "http://yourorg.hostsvr.com:8080",
  "type": "GERRIT",  
  "refSpecNotes": true,
  "refSpecChanges": true,
  "username": "johnsmith",
  "password": "jfJHhKHfksjhfkdsjhfelkwhfKFHlKDSHF",
  "displayName": "Gerrit repos"
}
```

<br>

### Integration REST APIs

[Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)

**Add New Integration Type API (examples)** (this page)

[Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)

[Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)

[Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed)

[Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed)

