---

title: Adding a private SSH key
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![Manage git integration for jira highlighting sidebar SSH keys menu item](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396698/gitserver-add-ssh-keys.png?version=1&modificationDate=1630642802720&cacheVersion=1&api=v2)

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>VERSION 4.0+</b> OpenSSH is now fully supported.
    </div>
    </div>
</div>

1.  From your Jira dashboard menu, go to Git ➜ **Manage repositories**. On the sidebar under _Git Integration for Jira_, select **SSH keys**.

2.  Click **Add SSH key**. The following screen is displayed:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396698/add-ssh-key-input-screen(c).png?version=1&modificationDate=1630642802480&cacheVersion=1&api=v2&width=374&height=400)

    Utilize the following options for adding the new SSH key.

    1.  _**Key name**_ – Enter a meaningful name for this private SSH key as required.

    2.  _**Private key**_ – This is the actual private SSH key. Upload the private key file via **Choose File** or paste the generated private key into the provided box.

    3.  _**Passphrase**_ – _Optional._ Enter the passphrase that was assigned to this private key.

3.  Click **Add** to complete this setup.


[Previous: Generating SSH keys](/git-integration-for-jira-self-managed/generating-ssh-keys)

[Next: Adding a public SSH key](/git-integration-for-jira-self-managed/adding-a-public-ssh-key)

