---

title: Increasing timeout threshold for large repositories while doing a Git pull
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
For this workaround to work, the user must have an access to a Jira hosting instance:

1.  Login to the hosting server.

2.  Create a new directory in the path different from the `JIRA HOME` directory. For example, `~/Image-repo/`

3.  Go to a directory and perform a clone of a repository:

    ```powershell
    git clone --mirror git@gitserver.com:repo/url.git  **1
    ```

    Or use the generic clone:

    ```powershell
    git clone git@gitserver.com:repo/url.git  **2
    ```

    ^1^ Modify the git repository URL to the correct one.<br>
    ^2^ Using the generic clone may take a bit longer and requires more disk space to store.

4.  For `~/Image-repo/` directory, give read and write permissions to the same user running Jira.
    For example, to make the user named _user_ be an owner of a folder, perform the following command:

    ```powershell
    sudo chown user ~/Image-repo
    ```

5.  Using the local path, connect the repository via the [Git Integration for Jira app Advanced setup wizard](/git-integration-for-jira-self-managed/connecting-a-repository-via-advanced-setup/). Use the correct local path for the Git for Jira app to successfully detect the repository.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396447/connect-git-repo-advanced-local-path(c).png?version=1&modificationDate=1630642794200&cacheVersion=1&api=v2&width=646&height=549)
6.  Click **Detect** to specify the origin value.

7.  Configure other settings if required. Click **Add** to proceed.


The repository is added and indexing should work.

In **VERSION 2.12.0** of the Git Integration for Jira app, the General setting for **Git operations timeout** was implemented.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396447/image-20210304-084400.png?version=1&modificationDate=1630642794438&cacheVersion=1&api=v2)

This setting affects how long will Git Integration for Jira app waits for connections performed during git clone and git fetch. BigBrassBand recommends to increase the time value if you have large repositories, and in some cases, connecting to them mostly results in timeout.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        If you have several large repositories and have a problem with exceeded timeout, we recommend that you use our <a href='/git-integration-for-jira-self-managed/working-with-tracked-folders/'>Tracked folders</a> feature to scan local folders at once and import repositories automatically.
    </div>
    </div>
</div>

