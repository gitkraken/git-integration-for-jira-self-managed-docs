---

title: Removing SSH keys
description: Delete an SSH key from the app configuration and learn what happens to repositories that referenced it.
product: Git Integration for Jira Data Center
feature: SSH Keys
content_type: how-to
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [generic]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-06
llms_include: true
tags: [ssh keys, delete key, remove key, common keys]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "documentation-gij-self-managed"
    nav_label: "Removing SSH keys"
    nav_order: 60
    nav_parent: "working-with-ssh-keys-gij-self-managed"
    page_type: "content"
---

SSH keys cannot be modified or updated. To change the keys, remove and add them again.

To delete the SSH key from the app configuration, click Actions ➜ **Delete**.

<img src='/wp-content/uploads/gij-ssh-addkey-list-del-key.png' style='display:block;margin:25px auto;max-width:100%' />

&nbsp;

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If the key is deleted, all repository references will also be removed. Repositories that don't have the key associated to them will use the common keys by default.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Adding and associating SSH keys](/git-integration-for-jira-data-center/adding-and-associating-ssh-keys-gij-self-managed)

[**Next:** Reconfigure Git repositories and SSH keys](/git-integration-for-jira-data-center/reconfigure-git-repositories-and-ssh-keys-gij-self-managed)

&nbsp;

### More on Working with SSH keys

[Working with SSH keys (index)](/git-integration-for-jira-data-center/working-with-ssh-keys-gij-self-managed)

[Generating SSH keys](/git-integration-for-jira-data-center/generating-ssh-keys-gij-self-managed)

[Adding a private SSH key](/git-integration-for-jira-data-center/adding-a-private-ssh-key-gij-self-managed)

[Adding a public SSH Key](/git-integration-for-jira-data-center/adding-a-public-ssh-key-gij-self-managed)

[SSH keys configuration](/git-integration-for-jira-data-center/ssh-keys-configuration-gij-self-managed)

[Adding and associating SSH keys](/git-integration-for-jira-data-center/adding-and-associating-ssh-keys-gij-self-managed)

**Removing SSH keys** (this page)

[Reconfigure Git repositories and SSH keys](/git-integration-for-jira-data-center/reconfigure-git-repositories-and-ssh-keys-gij-self-managed)


