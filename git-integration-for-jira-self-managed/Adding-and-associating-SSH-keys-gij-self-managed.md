---

title: Adding and associating SSH keys
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<div class='embed-container embed-container--16-10'>
    <iframe width='709' height='443' src='https://fast.wistia.com/embed/iframe/0a1exzdgpc?videoFoam=true' frameborder='0' allowfullscreen ></iframe>
</div>

<div align='center'>
    <i>Right click <a href='https://bigbrassband.wistia.com/medias/0a1exzdgpc'><b>here</b></a> to open this video in a new browser tab for more viewing options.</i>
</div>
<br>

Limit the usage of the SSH key by associating them to selected repositories. Strictly map SSH keys to repositories via SSH Actions menu.

1.  On the SSH Keys page, click Actions ➜ **Associations** for the selected SSH key.

2.  The following screen is displayed:

    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396771/gitserver-assoc-ssh-keys(c).png?version=1&modificationDate=1630642805980&cacheVersion=1&api=v2)

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

1.  Configure a repository that requires an SSH key via [Using the Connect Repository wizard](/git-integration-for-jira-data-center/using-the-connect-repository-wizard-gij-self-managed/).

2.  Associate that SSH key with the currently configured repository via Manage git repositories ➜ **SSH keys** (sidebar).

3.  Add another repository that requires the same SSH key. You will be presented with the following screen:

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396771/connect-ssh-gitlab-repo(c).png?version=1&modificationDate=1630642806469&cacheVersion=1&api=v2&width=646&height=450)

4.  Select the SSH key that you have associated to the previously added repository from the **Existing key** list.

5.  Click **Next** to continue. Complete the wizard and add another repository as desired.


For third-party products or services (such as GitHub, GitLab, Bitbucket, etc.), register the PUBLIC KEY for target repository or in profile settings of your git account.

## Associating SSH for custom git servers

For custom git hosting servers, ask your administrator to check that the target keypair's PUBLIC KEY is added into the `authorized_keys` file of the git server.

For more information, see the following article [**Setting up Git on the Server**](https://git-scm.com/book/it/v2/Git-on-the-Server-Setting-Up-the-Server).

