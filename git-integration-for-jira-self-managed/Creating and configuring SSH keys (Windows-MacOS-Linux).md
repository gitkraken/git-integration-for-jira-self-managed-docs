---

title: Creating and configuring SSH keys (Windows/MacOS/Linux)
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
**What’s on this page:**

* * *

## Introduction

The Git Integration for Jira app supports SSH git repository connections via **Connect Wizard** or **Git** on the Add new integration panel.

As a summary, you need to perform the following tasks in order to successfully integrate your SSH git repositories with Jira:

*   Obtain SSH git repository URL from your git host repository configuration page

*   Generate SSH key pair (public and private key)

*   Add the public key to your git host SSH configuration

*   Add the private key by connecting your SSH git repositories via Git Integration for Jira app.


|     |
| --- |
| ### 1\. Acquire SSH Git Repository URL |
| ![](https://bigbrassband.atlassian.net/wiki/download/attachments/183271450/image-20220118-110313.png?version=1&modificationDate=1642504624168&cacheVersion=1&api=v2) |
| Get the git clone SSH URL from the repository home of the git host that will be used for Jira integration. The above screen represents an example from GitLab. |

|     |
| --- |
| ### 2\. Generate SSH key pair (public and private key) |
| Do note that when generating the key pair for use with Git Integration for Jira app, the following checklist must be considered:<br><br>*   The generated SSH key must not be created using the OpenSSH format. Instead, use the supported certificate format: RSA,<br>    <br>*   Add the private key to Git Integration app and set the public key to your git host.<br>    <br>*   The generated SSH key must use the OpenSSL PEM storage format.<br>    <br><br>For more information on SSH connection issues, see article [SSH key format is invalid](/wiki/spaces/GIJDC/pages/187957296/SSH+key+file+format+is+invalid). |
| #### Linux/MacOs |
| On Linux and MacOS, perform this command in Terminal to generate an SSH key in RSA format:<br><br>```java<br>ssh-keygen -t rsa -b 4096 -m pem -C "your_email@example.com"<br>```<br><br>MacOS often incorrectly creates an OpenSSH format certificate. For more details, see information on this [**common problem**](https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key).<br><br>![](https://bigbrassband.atlassian.net/wiki/download/attachments/183271450/image-20220118-110744.png?version=1&modificationDate=1642504624174&cacheVersion=1&api=v2)<br><br>For lost SSH passphrase in Linux, you will need to generate a new SSH key pair. There's no way to recover it.<br><br>For MacOS, if you configured your SSH passphrase with the password manager (Keychain), you may be able to recover it via Keychain Access. |
| #### Windows |
| For Windows, we recommend to use [**PuTTY**](https://www.putty.org/) and use PuTTYgen to generate key pair for your SSH git repository connection.<br><br>![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/183271450/puttygen-key-dlg.png%3Fversion=1&modificationDate=1642164294617&cacheVersion=1&api=v2?version=1&modificationDate=1642504624176&cacheVersion=1&api=v2&width=448&height=440)<br><br>1.  Launch **PuTTYgen** and refer to the above image for the rest of the steps on this section.<br>    <br>2.  Set the _**Type of key to generate**_ to **RSA**.<br>    <br>3.  Set the _**Number of bits in a generated key**_ to **4096**.<br>    <br>4.  Click **Generate**.<br>    <br>5.  Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.<br>    <br>6.  Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.<br>    <br>7.  Save your generated public and private keys to a file by clicking the respective options.<br>    <br>8.  Copy the generated key. This is the public key that will used on the SSH configuration page of your git host.<br>    <br><br>If you lose your SSH key passphrase, recovering it is impossible. You will need to generate a new SSH key pair and a new passphrase instead. |

|     |
| --- |
| ### 3\. Add the public key to your git host. |
| 1.  Login to your git host and go the SSH configuration page (_for example, **Profile**➜ **Settings** in GitLab or GitHub_).<br>    <br>2.  Paste the generated public SSH key from PuTTYgen to the provided box.<br>    <br>3.  Add this key to complete setting up the public key for SSH git connection for your git host. |

|     |
| --- |
| ### 4\. Add the private key via Git Integration in Jira app. |
| For the private key, PuTTY creates it in its own ".ppk" format. To convert it to ".pem" format:<br><br>1.  On PuTTYgen window, go to menu **Conversions**.<br>    <br>2.  Select **Export OpenSSH key**.<br>    <br><br>Add/upload this file to Git Integration for Jira app ➜ SSH keys or when prompted in connecting SSH git repositories. |

## Video Guide

Watch the video below to learn more details of the steps outlined above. As a bonus, the video also shows how to connect SSH git repositories to Jira and viewing commits and code diff in Jira issues. 

_Right click_ [_**here**_](https://bigbrassband.wistia.com/medias/migvqa03gw) _to open this video in a new tab/window for more viewing options._

## More how-to articles

*   Page:

    [Creating Personal Access Tokens](/wiki/spaces/GIJDC/pages/107380737/Creating+Personal+Access+Tokens)

*   Page:

    [Working with JMESPath Filters](/wiki/spaces/GIJDC/pages/135430238/Working+with+JMESPath+Filters)

*   Page:

    [Working with Custom API Path](/wiki/spaces/GIJDC/pages/135331922/Working+with+Custom+API+Path)

*   Page:

    [Creating and configuring SSH keys (Windows/MacOS/Linux)](/wiki/spaces/GIJDC/pages/183271450)

*   Page:

    [Require Personal Access Tokens for user actions (create branch/pull request)](/wiki/spaces/GIJDC/pages/317390849)

*   Page:

    [Setting Project Permissions](/wiki/spaces/GIJDC/pages/509444154/Setting+Project+Permissions)

*   Page:

    [How to get a quote?](/wiki/spaces/GIJDC/pages/1165721603)

*   Page:

    [Ways to Index Git Data to Jira Issues](/wiki/spaces/GIJDC/pages/1207828916/Ways+to+Index+Git+Data+to+Jira+Issues)

*   Page:

    [Proxy settings on adding integrations (except AWS CodeCommit)](/wiki/spaces/GIJDC/pages/1808007195)

*   Page:

    [Configure Source Code Diff Viewing](/wiki/spaces/GIJDC/pages/2054881287/Configure+Source+Code+Diff+Viewing)