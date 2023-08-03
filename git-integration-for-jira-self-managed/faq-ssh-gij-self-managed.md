---

title: SSH FAQ
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

This page contains related questions on Git Integration for Jira app SSH connections in Jira.

Use the FAQ below to find answers to common questions. Feel free to contact our support team ([gijsupport@gitkraken.com](mailto:gijsupport@gitkraken.com?subject=Help%20on%20SSH%20issues%20-)) or visit our [support portal](https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support) if you don't see what you're looking for.

- [Creating and configuring SSH keys (Windows/MacOS/Linux)](#creating-and-configuring-ssh-keys-windowsmacoslinux)
    - [1\. Acquire SSH Git Repository URL](#1-acquire-ssh-git-repository-url)
    - [2\. Generate SSH key pair (public and private key)](#2-generate-ssh-key-pair-public-and-private-key)
        - [Linux/MacOs](#linuxmacos)
        - [Windows](#windows)
    - [3\. Add the public key to your git host.](#3-add-the-public-key-to-your-git-host)
    - [4\. Add the private key via Git Integration in Jira app.](#4-add-the-private-key-via-git-integration-in-jira-app)
    - [Video Guide](#video-guide)
- [Are passphrases supported on SSH keys?](#are-passphrases-supported-on-ssh-keys)
- [Does this app support authenticating to git repositories via SSH?](#does-this-app-support-authenticating-to-git-repositories-via-ssh)
- [How do you configure the SSH key used when adding a new project?](#how-do-you-configure-the-ssh-key-used-when-adding-a-new-project)
- [Why do I need to provide a PRIVATE KEY to the Git Integration for Jira app instead of a PUBLIC KEY?](#why-do-i-need-to-provide-a-private-key-to-the-git-integration-for-jira-app-instead-of-a-public-key)
- [How do I configure/connect an SSH remote git repository to Jira?](#how-do-i-configureconnect-an-ssh-remote-git-repository-to-jira)

&nbsp;
* * *
&nbsp;

#### Creating and configuring SSH keys (Windows/MacOS/Linux)

The Git Integration for Jira app supports SSH git repository connections via **Connect Wizard** or **Git** on the Add new integration panel.

As a summary, you need to perform the following tasks in order to successfully integrate your SSH git repositories with Jira:

*   Obtain SSH git repository URL from your git host repository configuration page

*   Generate SSH key pair (public and private key)

*   Add the public key to your git host SSH configuration

*   Add the private key by connecting your SSH git repositories via Git Integration for Jira app.

#### 1\. Acquire SSH Git Repository URL

![](/wp-content/uploads/gij-gitserver-acquire-ssh-git-repo-url.png)

Get the git clone SSH URL from the repository home of the git host that will be used for Jira integration. The above screen represents an example from GitLab.

#### 2\. Generate SSH key pair (public and private key)

Do note that when generating the key pair for use with Git Integration for Jira app, the following checklist must be considered:

*   The generated SSH key must not be created using the OpenSSH format. Instead, use the supported certificate format: RSA,

*   Add the private key to Git Integration app and set the public key to your git host.

*   The generated SSH key must use the OpenSSL PEM storage format.

    For more information on SSH connection issues, see article [SSH key format is invalid](/git-integration-for-jira-data-center/ssh-key-file-format-is-invalid-gij-self-managed).

<div id='linuxmacos'></div>

#### Linux/MacOs

On Linux and MacOS, perform this command in Terminal to generate an SSH key in RSA format:

```powershell
ssh-keygen -t rsa -b 4096 -m pem -C "your_email@example.com"
```

MacOS often incorrectly creates an OpenSSH format certificate. For more details, see information on this [**common problem**](https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key).

![](/wp-content/uploads/gij-gitserver-generate-ssh-key-pair-example.png)

For lost SSH passphrase in Linux, you will need to generate a new SSH key pair. There's no way to recover it.

For MacOS, if you configured your SSH passphrase with the password manager (Keychain), you may be able to recover it via Keychain Access.

#### Windows

For Windows, we recommend to use [**PuTTY**](https://www.putty.org/) and use PuTTYgen to generate key pair for your SSH git repository connection.

<img src='/wp-content/uploads/gij-puttygen-key-dlg.png' width=479 height=471 style='display:block;margin:25px auto;max-width:100%' />

1.  Launch **PuTTYgen** and refer to the above image for the rest of the steps on this section.

2.  Set the _**Type of key to generate**_ to **RSA**.

3.  Set the _**Number of bits in a generated key**_ to **4096**.

4.  Click **Generate**.

5.  Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.

6.  Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.

7.  Save your generated public and private keys to a file by clicking the respective options.

8.  Copy the generated key. This is the public key that will used on the SSH configuration page of your git host.

9. If you lose your SSH key passphrase, recovering it is impossible. You will need to generate a new SSH key pair and a new passphrase instead.

#### 3\. Add the public key to your git host.

*  Login to your git host and go the SSH configuration page (_for example, **Profile**➜ **Settings** in GitLab or GitHub_).

*  Paste the generated public SSH key from PuTTYgen to the provided box.

*  Add this key to complete setting up the public key for SSH git connection for your git host.

#### 4\. Add the private key via Git Integration in Jira app. 
For the private key, PuTTY creates it in its own ".ppk" format. To convert it to ".pem" format:

*  On PuTTYgen window, go to menu **Conversions**.

*  Select **Export OpenSSH key**.

*  Add/upload this file to Git Integration for Jira app ➜ SSH keys or when prompted in connecting SSH git repositories.

#### Video Guide

Watch the video below to learn more details of the steps outlined above. As a bonus, the video also shows how to connect SSH git repositories to Jira and viewing commits and code diff in Jira issues. 

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/migvqa03gw?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/migvqa03gw'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

#### Are passphrases supported on SSH keys?

Passphrases are now supported since v2.x.x of the Git Integration for Jira app.

#### Does this app support authenticating to git repositories via SSH?

Yes.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 4.0+</b><br>
        OpenSSH is now fully supported.
    </div>
    </div>
</div>

#### How do you configure the SSH key used when adding a new project?

SSH keys should be in **.ssh** folder located in user home (user which is used to run jira).

SSH keys with and without passphrases are supported.

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/qmumdo048n?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/qmumdo048n'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

&nbsp;

#### Why do I need to provide a PRIVATE KEY to the Git Integration for Jira app instead of a PUBLIC KEY?

The PRIVATE KEY is needed by the SSH client, which is the Jira server, to connect to the Git server via SSH.

#### How do I configure/connect an SSH remote git repository to Jira?

In Jira, use the **Connect to Git Repository** wizard to configure SSH integration with any remote git repositories.

1.  Go to Jira dashboard menu Git ➜ **Manage repositories**. _(Alternatively, go to Jira Dashboard menu Jira Administration ➜ Applications)._ The manage git repositories page is displayed.

2.  Click **Connect to Git Repository**. The **Connect to Git Repository** wizard appears.

3.  Enter the **Repository location** of your SSH git server. Click **Next**.

4.  Upload the private key or paste it on the provided field. Click **Next**.

5.  Enter **Passphrase** (if the SSH has one). Click **Next**.

6.  The wizard will start cloning the selected repository. When the process is complete, the Permissions dialog is displayed.

7.  Leave settings as is and click **Next**.

8.  Click **Finish** to complete the setup. The repository is added to the repositories list.


Here's a video to guide you step-by-step as stated above:

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/qmumdo048n?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Watch how to add an SSH Git repository. Right click <a href='https://bigbrassband.wistia.com/medias/qmumdo048n'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>

