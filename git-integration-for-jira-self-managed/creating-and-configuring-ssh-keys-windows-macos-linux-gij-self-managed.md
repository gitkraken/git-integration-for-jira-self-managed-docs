---

title: Creating and configuring SSH keys
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- how tos -->

**What's on this page:**
- [Introduction](#introduction)
- [Acquire SSH Git Repository URL](#acquire-ssh-git-repository-url)
- [Generate SSH key pair (public and private key)](#generate-ssh-key-pair-public-and-private-key)
- [Linux/MacOS](#linuxmacos)
- [Windows](#windows)
- [Add the public key to your git host](#add-the-public-key-to-your-git-host)
- [Add the private key via Git Integration in Jira app](#add-the-private-key-via-git-integration-in-jira-app)
- [Video Guide](#video-guide)
- [More How-to articles](#more-how-to-articles)

&nbsp;
* * *
&nbsp;

### Introduction

The Git Integration for Jira app supports SSH git repository connections via Connect Wizard or Git on the Add new integration panel.

As a summary, you need to perform the following tasks in order to successfully integrate your SSH git repositories with Jira:

*   Obtain SSH git repository URL from your git host repository configuration page

*   Generate SSH key pair (public and private key)

*   Add the public key to your git host SSH configuration

*   Add the private key by connecting your SSH git repositories via Git Integration for Jira app.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Native support for the edDSA SSH key format was introduced in Git Integration for Jira app version 4.0.3. However, edDSA won't work when reinstalling the app. A Jira restart would fix the issue. For the other workaround, see <a href='/git-integration-for-jira-data-center/edDSA-provider-not-supported-WARN-in-logs'>Can't add edDSA ssh key</a>.
    </div>
    </div>
</div>

&nbsp;

### Acquire SSH Git Repository URL

<img src='/wp-content/uploads/gij-gitserver-gitlab-example-acquire-ssh-home-repo.png' style='display:block;margin:25px auto;max-width:100%' />

Get the git clone SSH URL from the repository home of the git host that will be used for Jira integration. The above screen represents an example from GitLab.

&nbsp;

### Generate SSH key pair (public and private key)

Do note that when generating the key pair for use with Git Integration for Jira app, the following checklist must be considered:

*   The generated SSH key must not be created using the OpenSSH format. Instead, use the supported certificate format: RSA,

*   Add the private key to Git Integration app and set the public key to your git host.

*   The generated SSH key must use the OpenSSL PEM storage format.

For more information on SSH connection issues, see article [SSH key file format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed).

&nbsp;

### Linux/MacOS

On Linux and MacOS, perform this command in Terminal to generate an SSH key in RSA format:

```powershell
ssh-keygen -t rsa -b 4096 -m pem -C "your_email@example.com"
```

<div class="bbb-callout bbb--alert">
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

<img src='/wp-content/uploads/gij-example-linux-terminal-ssh-generate-pair.png' style='margin:25px auto;max-width:100%;display:block;' />

<br>

<div class="bbb-callout bbb--note">
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

&nbsp;

### Windows

For Windows, we recommend to use <a href='https://www.putty.org/' target='_blank'>PuTTY</a> and use PuTTYgen to generate key pair for your SSH git repository connection.

<img src='/wp-content/uploads/gij-puttygen-key-dlg.png' style='margin:25px auto;max-width:100%;display:block;' />

1.  Launch **PuTTYgen** and refer to the above image for the rest of the steps on this section.

2.  Set the _**Type of key to generate**_ to **RSA**.

3.  Set the _**Number of bits in a generated key**_ to **4096**.

4.  Click **Generate**.

5.  Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.

6.  Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.

7.  Save your generated public and private keys to a file by clicking the respective options.

8.  Copy the generated key. This is the public key that will used on the SSH configuration page of your git host.

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

&nbsp;

### Add the public key to your git host

1.  Login to your git host and go the SSH configuration page (for example, Profile ➜ **Settings** in GitLab or GitHub).

2.  Paste the generated public SSH key from PuTTYgen to the provided box.

3.  Add this key to complete setting up the public key for SSH git connection for your git host.

&nbsp;

### Add the private key via Git Integration in Jira app

For the private key, PuTTY creates it in its own ".ppk" format. To convert it to ".pem" format:

1.  On PuTTYgen window, go to menu **Conversions**.

2.  Select **Export OpenSSH key**.

Add/upload this file to Git Integration for Jira app ➜ SSH keys or when prompted in connecting SSH git repositories.

&nbsp;

### Video Guide

Watch the video below to learn more details of the steps outlined above. As a bonus, the video also shows how to connect SSH git repositories to Jira and viewing commits and code diff in Jira issues.

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/migvqa03gw?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://gitkraken.wistia.com/medias/migvqa03gw'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

### More How-to articles

[How to get a quote?](/git-integration-for-jira-data-center/how-to-get-a-quote-gij-self-managed/)

[Setting Project Permissions](/git-integration-for-jira-data-center/Setting-Project-Permissions-gij-self-managed)

[How to create a HAR file and send it to support for analysis](/git-integration-for-jira-data-center/how-to-create-a-har-file-and-send-it-to-support-for-analysis-gij-self-managed/)

[Working with Custom API Path](/git-integration-for-jira-data-center/Working-with-Custom-API-Path-gij-self-managed)

[Working with JMESPath Filters](/git-integration-for-jira-data-center/Working-with-JMESPath-Filters-gij-self-managed)

[Configure Source Code Diff Viewing](/git-integration-for-jira-data-center/configure-source-code-diff-viewing-gij-self-managed)

**Creating and configuring SSH keys (Windows/MacOS/Linux)** (this page)

[Require Personal Access Tokens for user actions (create branch/pull request)](/git-integration-for-jira-data-center/Require-Personal-Access-Tokens-for-user-actions-(create-branch-pull-request)-gij-self-managed)

[Ways to Index Git Data to Jira Issues](/git-integration-for-jira-data-center/Ways-to-Index-Git-Data-to-Jira-Issues-gij-self-managed)

[Proxy settings on adding integrations (except AWS CodeCommit)](/git-integration-for-jira-data-center/Proxy-settings-on-adding-integrations-(except-AWS-CodeCommit)-gij-self-managed)

[Creating Personal Access Tokens](/git-integration-for-jira-data-center/Creating-Personal-Access-Tokens-gij-self-managed)

