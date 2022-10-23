---

title: Working with SSH keys
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
SSH keys are required in order to provide secure connection with the remote git host. The Git Integration for Jira app uses one set of keys for accessing all configured repositories.

<div class="bbb-callout bbb--info">
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
<br>

Follow this guide if you are one of the users who are limited to or wanted to use SSH to securely connect to your git repositories.

## Introduction

There are two options available for specifying SSH keys:

*   **SSH keys stored on server filesystem**. The keys are located in the home folder of the user which account is used to run Jira. This option provides better compatibility with installation of the previous versions of the Git Integration app. _This option does not support passphrases._

*   **SSH keys are stored in the app configuration.** The keys are added using the Git Integration app configuration. _This option supports passphrases._

<div class="bbb-callout bbb--note">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      Features such as branch and pull/merge request creation is only available to repositories/git hosts that were connected via the Auto-connect integration.
    </div>
  </div>
</div>

<div class="bbb-callout bbb--tip">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      <b>Jira Data Center</b><br>
      In case of Jira DC with multiple nodes, the SSH keys stored on server filesystem must be the same on all nodes.
    </div>
  </div>
</div>
<br>

## Getting started

Before connecting repositories via SSH, users are required to generate SSH keys for use with the remote git host (_public key_) and for Git Integration app in Jira (_private key_).

Generated SSH keys always come in pair. (**Example:** `id_rsa.pub` and `id_rsa`)

For establishing safety connection with SSH, upload a **public key** to the SSH server and set the **private key** to the SSH client.

In this case, the SSH server is the Git server and the SSH client is the Jira server. Therefore:

*   Git server — public key

*   Jira server — private key (_Git Integration for Jira sidebar ➜ SSH Keys_)

<div class="bbb-callout bbb--alert">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      The developer's local system should not have the same private key.
    </div>
  </div>
</div>

<div class="bbb-callout bbb--note">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        Note that Git Integration for Jira app SSH key:
        <ul>
          <li><b>VERSION 4.0+</b> now fully supports OpenSSH format.</li>
          <li>must be the private key.</li>
          <li>must use the supported certificate format: RSA.</li>
          <li>must use the supported storage format: OpenSSL PEM.</li>
        </li>
        For more information, see troubleshooting article <a href='/git-intengration-for-jira-data-center/SSH-key-file-format-is-invalid-gij-self-managed'>SSH key format is invalid</a>.
    </div>
  </div>
</div>
<br>

* * *

## Windows

For Windows, we recommend to use <a href='https://www.putty.org/'><b>PuTTY</b></a> and use PuTTYgen to generate public and private SSH keys.

<img src='/wp-content/uploads/gij-puttygen-key-dlg.png' width=442 height=434 style='display:block;margin:25px auto;max-width:100%' />

1. Launch **PuTTYgen** and refer to the above image for the rest of the steps on this section.

2. Set _**Type of key to generate**_ to **RSA**.

3. Set _**Number of bits in a generated key**_ to **4096**.

4. Click **Generate**.

5. Follow screen instructions such as moving your mouse pointer on random locations on the blank area of the PuTTYgen dialog. Do this until the progress bar completely fills up and the SSH key pair is generated.

6. Entering a **Passphrase** for the generated key is optional but will ensure a more secure connection.

7. Save your generated public and private key to a file by clicking the respective options.

8. Copy the generated key. This is the public key that you will be using on the SSH configuration page of your git host.

9. For the private key, see the note below.

<br>

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        PuTTY creates a private key in its own ".ppk" format. To convert it to ".pem", the user should do the <b>Conversions</b> ➜ <b>Export OpenSSH key</b> menu option in PuTTYgen. Add/upload this file to Git Integration for Jira app ➜ <b>SSH keys</b> or when prompted on connecting SSH git repositories in Jira via Connect Git Repository wizard.
    </div>
    </div>
</div>

You can also use the git bash command line to generate SSH key pair. For detailed information, see <a href='https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key'><b>Generate SSH via Git bash</b></a>.

Read on the section [Generating SSH keys](/git-integration-for-jira-dta-center/generating-ssh-keys-gij-self-managed) and follow specific information for the git host and platform that you use.

## Linux/MacOS

On Linux and MacOS, this generates an SSH key in RSA format:

```powershell
ssh-keygen -t rsa -b 4096 -m pem -C "your_email@example.com"
```

MacOS often incorrectly creates an OpenSSH format certificate. For more details, see information on this <a href='https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key'><b>common problem</b></a>.

<br>
<br>

[**Prev:** Getting started for Git administrators](/git-integration-for-jira-data-center/Getting-started-for-Git-administrators-gij-self-managed)

[**Next:** Genenerating SSH keys](/git-integration-for-jira-data-center/generating-ssh-keys-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

[Generating SSH keys](/git-integration-for-jira-data-center/generating-ssh-keys-gij-self-managed)

[Adding a private SSH key](/git-integration-for-jira-data-center/adding-a-private-ssh-key-gij-self-managed)

[Adding a public SSH Key](/git-integration-for-jira-data-center/adding-a-public-ssh-key-gij-self-managed)

[SSH keys configuration](/git-integration-for-jira-data-center/ssh-keys-configuration-gij-self-managed)

[Adding and associating SSH keys](/git-integration-for-jira-data-center/adding-and-associating-ssh-keys-gij-self-managed)

[Removing SSH keys](/git-integration-for-jira-data-center/removing-ssh-keys-gij-self-managed)

[Reconfigure Git repositories and SSH keys](/git-integration-for-jira-data-center/reconfigure-git-repositories-and-ssh-keys-gij-self-managed)


