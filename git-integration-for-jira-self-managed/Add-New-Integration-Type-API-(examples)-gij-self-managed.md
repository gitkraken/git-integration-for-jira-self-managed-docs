---

title: Add New Integration Type API (examples)
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Only Jira admins can perform the Add New Integration Type API call.
    </div>
    </div>
</div>
<br>

Below are integration API examples for each integration types:

## Add new integration type

### url
`/rest/gitplugin/1.0/`**integration**

### method
POST

<br>

### Prameters

Request body is a _JSON_ structure.

For complete reference of the parameters, see [Add New Integration API](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed/).

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        When adding new repositories, we recommend to leave the <code>trustFolderStat</code> setting to <b>false</b> <i>(default)</i>. You can change this setting later on via <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ <b>Edit repository settings</b> in the Manage repositories page.
    </div>
    </div>
</div>
<br>


### GITHUB

**Example 1: (Username/password)**

```json
{
  "type": "GITHUB",
  "password": "mypassword",
  "username": "johnsmith",
  "displayName": "johnsmith's GitHub via API"
}
```

<br>

### GITHUB ENTERPRISE

**Example 1: (Username/password)**

```json
{
  "type": "GITHUB_SERVER",
  "displayName": "GitHub Ent. via API -- password",
  "origin": "https://mygithub.yourorg.com",
  "username": "githubadmin",
  "password": "4TKaCXtaf59G",
  "disableSslVerification": true
}
```

**Example 2: (Personal access token)**

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
  "origin": "D:\tmp\*"
}
```

<br>

### GERRIT

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        The origin field parameter is required.
    </div>
    </div>
</div>

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

