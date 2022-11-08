---

title: Creating and configuring SSH keys
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

**What's on this page:**
- [Introduction](#introduction)
- [1\. Acquire SSH Git Repository URL](#1-acquire-ssh-git-repository-url)
- [2\. Generate SSH key pair (public and private key)](#2-generate-ssh-key-pair-public-and-private-key)
  - [Linux/MacOS](#linuxmacos)
  - [Windows](#windows)
- [3\. Add the public key to your git host.](#3-add-the-public-key-to-your-git-host)
- [4\. Add the private key via Git Integration in Jira app.](#4-add-the-private-key-via-git-integration-in-jira-app)
- [Video Guide](#video-guide)
- [More How-to articles](#more-how-to-articles)

<br>
<br>
<hr>
<br>
<br>

## Introduction

The Git Integration for Jira app supports SSH git repository connections via Connect Wizard or Git on the Add new integration panel.

As a summary, you need to perform the following tasks in order to successfully integrate your SSH git repositories with Jira:

*   Obtain SSH git repository URL from your git host repository configuration page

*   Generate SSH key pair (public and private key)

*   Add the public key to your git host SSH configuration

*   Add the private key by connecting your SSH git repositories via Git Integration for Jira app.

## 1\. Acquire SSH Git Repository URL

<img src='/wp-content/uploads/gij-gitserver-gitlab-example-acquire-ssh-home-repo.png' style='display:block;margin:25px auto;max-width:100%' />

Get the git clone SSH URL from the repository home of the git host that will be used for Jira integration. The above screen represents an example from GitLab.

## 2\. Generate SSH key pair (public and private key)

Do note that when generating the key pair for use with Git Integration for Jira app, the following checklist must be considered:

*   The generated SSH key must not be created using the OpenSSH format. Instead, use the supported certificate format: RSA,

*   Add the private key to Git Integration app and set the public key to your git host.

*   The generated SSH key must use the OpenSSL PEM storage format.

For more information on SSH connection issues, see article [SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed).

### Linux/MacOS

On Linux and MacOS, perform this command in Terminal to generate an SSH key in RSA format:

```powershell
ssh-keygen -t rsa -b 4096 -m pem -C "your_email@example.com"
```

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        MacOS often incorrectly creates an OpenSSH format certificate. For more details, see information on this <a href='https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key' target='_blank'><b>common problem</b></a>.
    </div>
    </div>
</div>
<br>

<img src='/wp-content/uploads/gij-example-linux-terminal-ssh-generate-pair.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For lost SSH passphrase in Linux, you will need to generate a new SSH key pair. There's no way to recover it.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        For MacOS, if you configured your SSH passphrase with the password manager (Keychain), you may be able to recover it via Keychain Access.
    </div>
    </div>
</div>
<br>

### Windows

For Windows, we recommend to use <a href='https://www.putty.org/' target='_blank'>PuTTY</a> and use PuTTYgen to generate key pair for your SSH git repository connection.

<img src='/wp-content/uploads/gij-puttygen-key-dlg.png' style='display:block;margin:25px auto;max-width:100%' />

<br>

1.  Launch **PuTTYgen** and refer to the above image for the rest of the steps on this section.

2.  Set the _**Type of key to generate**_ to **RSA**.

3.  Set the _**Number of bits in a generated key**_ to **4096**.

4.  Click **Generate**.

5.  Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.

6.  Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.

7.  Save your generated public and private keys to a file by clicking the respective options.

8.  Copy the generated key. This is the public key that will used on the SSH configuration page of your git host.

<br>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you lose your SSH key passphrase, recovering it is impossible. You will need to generate a new SSH key pair and a new passphrase instead.
    </div>
    </div>
</div>
<br>

## 3\. Add the public key to your git host.

1.  Login to your git host and go the SSH configuration page (for example, **Profile** ➜ **Settings** in GitLab or GitHub).

2.  Paste the generated public SSH key from PuTTYgen to the provided box.

3.  Add this key to complete setting up the public key for SSH git connection for your git host.

## 4\. Add the private key via Git Integration in Jira app.

For the private key, PuTTY creates it in its own ".ppk" format. To convert it to ".pem" format:

1.  On PuTTYgen window, go to menu **Conversions**.

2.  Select **Export OpenSSH key**.

Add/upload this file to Git Integration for Jira app ➜ SSH keys or when prompted in connecting SSH git repositories.

## Video Guide

Watch the video below to learn more details of the steps outlined above. As a bonus, the video also shows how to connect SSH git repositories to Jira and viewing commits and code diff in Jira issues.

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/migvqa03gw?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/migvqa03gw'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>
<br>

<p>&nbsp;</p>

## More How-to articles

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Working with Custom API Path](/git-integration-for-jira-data-center/Working-with-Custom-API-Path-gij-self-managed)

**Creating and configuring SSH keys (Windows/MacOS/Linux)** (this page)

[Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/Require-Personal-Access-Tokens-for-user-actions-(create-branch-pull-request)-gij-self-managed)

[Setting Project Permissions](/git-integration-for-jira-data-center/Setting-Project-Permissions-gij-self-managed)

[How to get a quote?](/git-integration-for-jira-data-center/How-to-get-a-quote-gij-self-managed)

[Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/Ways-to-Index-Git-Data-to-Jira-Issues-gij-self-managed)

[Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/Proxy-settings-on-adding-integrations-(except-AWS-CodeCommit)-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)


