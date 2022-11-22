---

title: Adding and associating SSH keys
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/0a1exzdgpc?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center' style='margin-top:10px'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/0a1exzdgpc'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>
<br>

Limit the usage of the SSH key by associating them to selected repositories. Strictly map SSH keys to repositories via SSH Actions menu.

1.  On the SSH Keys page, click ![](/wp-content/uploads/actions-icon.png) Actions ➜ **Associations** for the selected SSH key.

2.  The following screen is displayed:

    ![](/wp-content/uploads/gij-gitserver-assoc-ssh-keys-c.png)

    Mark the required repository or repositories to associate the SSH key.

4.  Clicking the **Select All** text label marks all repositories that will be associated to this SSH key.

5.  Clicking the **Select None** text label deselects all repositories.

6.  Click **Save** to save the settings.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If an SSH key is strictly associated with some repository, that SSH key is an associated key.
    </div>
    </div>
</div>
<br>

## Associating SSH keys for multiple repositories

If you have multiple repositories that uses the same SSH key, configure them via Git Integration app by doing the following steps:

1.  Configure a repository that requires an SSH key via [Using the Connect Repository wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed).

2.  Associate that SSH key with the currently configured repository via Manage git repositories ➜ **SSH keys** (sidebar).

3.  Add another repository that requires the same SSH key. You will be presented with the following screen:

    ![](/wp-content/uploads/gij-connect-ssh-gitlab-repo-c.png)

4.  Select the SSH key that you have associated to the previously added repository from the **Existing key** list.

5.  Click **Next** to continue. Complete the wizard and add another repository as desired.


For third-party products or services (such as GitHub, GitLab, Bitbucket, etc.), register the PUBLIC KEY for target repository or in profile settings of your git account.

## Associating SSH for custom git servers

For custom git hosting servers, ask your administrator to check that the target keypair's PUBLIC KEY is added into the `authorized_keys` file of the git server.

For more information, see the following article <a href='https://git-scm.com/book/it/v2/Git-on-the-Server-Setting-Up-the-Server' target='_blank'><b>Setting up Git on the Server</b></a>.

<br>
<br>

[**Prev:** SSH keys configuration](/git-integration-for-jira-data-center/ssh-keys-configuration-gij-self-managed)

[**Next:** Removing SSH keys](/git-integration-for-jira-data-center/removing-ssh-keys-gij-self-managed)

<br>
<br>
<hr>
<br>
<br>

## More on Working with SSH keys

[Working with SSH keys (index)](/git-integration-for-jira-data-center/working-with-ssh-keys-gij-self-managed)

[Generating SSH keys](/git-integration-for-jira-data-center/generating-ssh-keys-gij-self-managed)

[Adding a private SSH key](/git-integration-for-jira-data-center/adding-a-private-ssh-key-gij-self-managed)

[Adding a public SSH Key](/git-integration-for-jira-data-center/adding-a-public-ssh-key-gij-self-managed)

[SSH keys configuration](/git-integration-for-jira-data-center/ssh-keys-configuration-gij-self-managed)

**Adding and associating SSH keys** (this page)

[Removing SSH keys](/git-integration-for-jira-data-center/removing-ssh-keys-gij-self-managed)

[Reconfigure Git repositories and SSH keys](/git-integration-for-jira-data-center/reconfigure-git-repositories-and-ssh-keys-gij-self-managed)

