---

title: Git Commits tab
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
The Git Commits tab shows commit information such as commit authors, date of commit, commit messages, access to view code diffs, commit id and view full commit.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398950/gitserver-git-commits-tab-enum(feb2022).png?version=2&modificationDate=1645415299981&cacheVersion=1&api=v2&width=680&height=238)


Open an issue then go to the _**Git Commits**_ tab to view commit information:

|     |     |     |
| --- | --- | --- |
| **Pointer** | **Information** | **Description** |
| **1** | **Repository/Indexed** | Name of the repository _(as in app config)_ and date of last synchronization with remote repository. |
| **2** | **Author/Committer** | User who performed the commit. Hover the mouse pointer on the name to view user card. |
| **3** | **Issue key/Commit message** | This is the Jira issue with the corresponding commit message. |
| **4** | **Repository name and Branch name** | This is the name of the repository the commit has been made. Click to browse this repository via Repository Browser.<br><br>Adjacent to the repository name is the Git branch name. Click to view this branch via Repository Browser. |
| **5** | **Commit UUID** | UUID of the commit and git host link. Click the UUID to view the code diffs for this commit. Click the git host link to view this commit via the git host server. |
| **6** | **Open in GitKraken** | Opens and view this commit via the GitKraken client app. |
| **7** | **Commit indicator** | This is the commit indicator. Smart commit errors are also indicated here, if encountered. |
| **8** | **View full commit** | Click the **View Full Commit** button to view the full code diff for the selected commit. |
| **9** | **Web links** | These are clickable web links that will open the selected file code diff directly to git host portal in a new browser window/tab. |
| **10** | **Files changed** | List of files affected by the commit. Click the file or git host link to view code diff of this commit.<br><br>![Git commit traffic light example](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398950/traffic-light-example.png?version=2&modificationDate=1639995867373&cacheVersion=1&api=v2&width=117&height=16)<br><br>The traffic light indicator shows the added/modified/deleted lines from the file code diffs. |

View the whole commit code diff information by clicking the **View full commit** button to the right of the commit message.

View code diff information of the particular file by clicking the filename for each file adjacent to the rollup counter markers.

[« Git Roll Up tab](/wiki/spaces/GIJDC/pages/1930398901/Git+Roll+Up+tab)

[Code syntax highlighter »](/wiki/spaces/GIJDC/pages/1930398989/Code+syntax+highlighter)
