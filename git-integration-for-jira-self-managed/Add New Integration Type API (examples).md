---

title: Add New Integration Type API (examples)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Only Jira admins can perform the Add New Integration Type API call.

Below are integration API examples for each integration types:

|     |
| --- |
| **Add new integration type** |
| _**url**_ |
| `/rest/gitplugin/1.0/`**integration** |
| _**method**_ |
| POST |
| _**parameters**_ |
| Request body is a _JSON_ structure.<br><br>For complete reference of the parameters, see [Add New Integration API](/wiki/spaces/GIJDC/pages/380666461/Add+New+Integration). |

When adding new repositories, we recommend to leave the `trustFolderStat` setting to **false** _(default)_. You can change this setting later on via ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _Actions_ ➜ _**Edit repository settings**_ in the Manage repositories page.

|     |
| --- |
| **GITHUB** |
| **Example 1: (Username/password)**<br><br>```java<br>{<br>  "type": "GITHUB",<br>  "password": "mypassword",<br>  "username": "johnsmith",<br>  "displayName": "johnsmith's GitHub via API"<br>}<br>```<br><br>**Example 2: (Personal access token)**<br><br>```java<br>{<br>  "type": "GITHUB",<br>  "pat": "q9ie8y8lwrrlsg943ioox3qdv085hyr63h005rxb",<br>  "displayName": "johnsmith's GitHub via API (pat)"<br>}<br>``` |

|     |
| --- |
| **GITHUB ENTERPRISE** |
| **Example 1: (Username/password)**<br><br>```java<br>{<br>  "type": "GITHUB_SERVER",<br>  "displayName": "GitHub Ent. via API -- password",<br>  "origin": "https://mygithub.yourorg.com",<br>  "username": "githubadmin",<br>  "password": "4TKaCXtaf59G",<br>  "disableSslVerification": true<br>}<br>```<br><br>**Example 2: (Personal access token)**<br><br>```java<br>{<br>  "type": "GITHUB_SERVER",<br>  "displayName": "GitHub Ent. via API -- pat",<br>  "origin": "https://mygithub.yourorg.com",<br>  "pat": "330sw9nqs1ges2osiffl4lzb6bm65ejbeua4rsju",<br>  "disableSslVerification": true<br>}<br>``` |

|     |
| --- |
| **GITLAB** |
| ```java<br>{<br>  "type": "GITLAB",<br>  "pat": "AvTfLwSd6wBoK6bSPzks",<br>  "displayName": "MY GITLAB"<br>}<br>``` |

|     |
| --- |
| **GITLAB CE/EE (Legacy)** |
| ```java<br>{<br>  "type": "GITLAB_SERVER_LEGACY",<br>  "displayName": "GITLAB_SERVER v.3 Legacy",<br>  "username": "gitlabadmin",<br>  "password": "G4eeNPpNK82d",<br>  "origin": "http://mygitlab.yourorg.com/"<br>}<br>``` |

|     |
| --- |
| **GITLAB CE/EE** |
| ```java<br>{<br>  "type": "GITLAB_SERVER",<br>  "displayName": "GITLAB_SERVER v.4",<br>  "origin": "http://mygitlabserver.yourorg.com",<br>  "pat": "7yz0b4sa8f3g59kaz7wn"<br>}<br>``` |

|     |
| --- |
| **AWS CODECOMMIT** |
| ```java<br>{<br>  "type": "AWS",<br>  "username": "AHMY0OGWY8RX3RB1SXTU",<br>  "password": "YupPNQD8fyREjfkHrY8KqmYNz7c5QzWPubqSw2az",<br>  "awsRegion": "us-east-1"<br>}<br>``` |

|     |
| --- |
| **AZURE** |
| ```java<br>{<br>  "type": "AZURE",<br>  "pat": "vuxz5i9kn2pqrr2culs0j2kryxqu38myg8i5s0t3gp86h47wb6ft"<br>}<br>``` |

|     |
| --- |
| **VSTS** |
| ```java<br>{<br>  "type": "VSTS",<br>  "pat": "vuxz5i9kn2pqrr2culs0j2kryxqu38myg8i5s0t3gp86h47wb6ft",<br>  "displayName": "Visual Studio Ent."<br>}<br>``` |

|     |
| --- |
| **TFS** |
| ```java<br>{<br>  "type": "TFS_SERVER",<br>  "displayName": "TFS 2018 via API",<br>  "origin": "http://tfs2018.yourorg:8080/tfs",<br>  "username": "tfsadmin",<br>  "password": "I26C953WPmNbFr7hp3eosf$Z68PcXAHe"<br>}<br>``` |

|     |
| --- |
| **AZURE DEVOPS** |
| ```java<br>{<br>  "type": "AZURE_DEVOPS",<br>  "displayName": "Azure Devops (TFS 2019) via API",<br>  "origin": "http://myazuredevops.yourorg.com/",<br>  "username": "adevopsadmin",<br>  "password": "G6Dz6BuUGKh5lo%Zh#cJm#0QdN@#fZ8#"<br>}<br>``` |

|     |
| --- |
| **TRACKED FOLDER** |
| ```java<br>{<br>  "type": "FILESPACE",<br>  "displayName": "Tracked folder via API",<br>  "origin": "D:\\tmp\\*"<br>}<br>``` |

|     |
| --- |
| **GERRIT** |
| **Note**  <br>The _**origin**_ field parameter is required.<br><br>```java<br>{<br>  "origin": "http://yourorg.hostsvr.com:8080",<br>  "type": "GERRIT",<br>  "refSpecNotes": true,<br>  "refSpecChanges": true,<br>  "username": "johnsmith",<br>  "password": "jfJHhKHfksjhfkdsjhfelkwhfKFHlKDSHF",<br>  "displayName": "Gerrit repos"<br>}<br>``` |

