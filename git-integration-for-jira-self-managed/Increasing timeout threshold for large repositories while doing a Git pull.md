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

    ```java
    git clone --mirror git@gitserver.com:repo/url.git  **1
    ```

    Or use the generic clone:

    ```java
    git clone git@gitserver.com:repo/url.git  **2
    ```

    1 Modify the git repository URL to the correct one.
    2 Using the generic clone may take a bit longer and requires more disk space to store.

4.  For `~/Image-repo/` directory, give read and write permissions to the same user running Jira.
    For example, to make the user named _user_ be an owner of a folder, perform the following command:

    ```java
    sudo chown user ~/Image-repo
    ```

5.  Using the local path, connect the repository via the [Git Integration for Jira app Advanced setup wizard](/wiki/spaces/GIJDC/pages/1930397180/Connecting+a+repository+via+Advanced+setup). Use the correct local path for the Git for Jira app to successfully detect the repository.

    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930396447/connect-git-repo-advanced-local-path(c).png?version=1&modificationDate=1630642794200&cacheVersion=1&api=v2&width=646&height=549)
6.  Click **Detect** to specify the origin value.

7.  Configure other settings if required. Click **Add** to proceed.


The repository is added and indexing should work.

In VERSION 2.12.0 of the Git Integration for Jira app, the General setting for **Git operations timeout** was implemented.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930396447/image-20210304-084400.png?version=1&modificationDate=1630642794438&cacheVersion=1&api=v2)

This setting affects how long will Git Integration for Jira app waits for connections performed during git clone and git fetch. BigBrassBand recommends to increase the time value if you have large repositories, and in some cases, connecting to them mostly results in timeout.

If you have several large repositories and have a problem with exceeded timeout, we recommend that you use our [Tracked folders](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders) feature to scan local folders at once and import repositories automatically.

[« Setting up webhooks](/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks)

[Working with Tracked folders »](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders)

### More related topics about getting started for git admins

*   Page:

    [Setup GitLab Server to respond to incoming network API calls](/wiki/spaces/GIJDC/pages/1930396193/Setup+GitLab+Server+to+respond+to+incoming+network+API+calls) (Git Integration for Jira Data Center)

*   Page:

    [New GitLab v10+ authentication](/wiki/spaces/GIJDC/pages/1930396211) (Git Integration for Jira Data Center)

*   Page:

    [General settings: Improving Jira performance](/wiki/spaces/GIJDC/pages/1930396229/General+settings%3A+Improving+Jira+performance) (Git Integration for Jira Data Center)

*   Page:

    [Adding a repository hosted on Windows Servers or Windows Network Share (Admins)](/wiki/spaces/GIJDC/pages/1930396287) (Git Integration for Jira Data Center)

*   Page:

    [Setting up repository root not located in Jira Home directory (Admins)](/wiki/spaces/GIJDC/pages/1930396317) (Git Integration for Jira Data Center)

*   Page:

    [Recommended reindex interval setting](/wiki/spaces/GIJDC/pages/1930396353/Recommended+reindex+interval+setting) (Git Integration for Jira Data Center)

*   Page:

    [Reindex API to trigger indexing](/wiki/spaces/GIJDC/pages/1930396333/Reindex+API+to+trigger+indexing) (Git Integration for Jira Data Center)

*   Page:

    [Setting up web linking](/wiki/spaces/GIJDC/pages/1930396395/Setting+up+web+linking) (Git Integration for Jira Data Center)

*   Page:

    [Setting up webhooks](/wiki/spaces/GIJDC/pages/1930396415/Setting+up+webhooks) (Git Integration for Jira Data Center)

*   Page:

    [Increasing timeout threshold for large repositories while doing a Git pull](/wiki/spaces/GIJDC/pages/1930396447/Increasing+timeout+threshold+for+large+repositories+while+doing+a+Git+pull) (Git Integration for Jira Data Center)

*   Page:

    [Working with Tracked folders](/wiki/spaces/GIJDC/pages/1930396479/Working+with+Tracked+folders) (Git Integration for Jira Data Center)

*   Page:

    [Recommended upgrade method for Git Integration for Jira](/wiki/spaces/GIJDC/pages/1930396509/Recommended+upgrade+method+for+Git+Integration+for+Jira) (Git Integration for Jira Data Center)

*   Page:

    [Discard cloned files in Jira Home directory (General setting)](/wiki/spaces/GIJDC/pages/1930396547) (Git Integration for Jira Data Center)