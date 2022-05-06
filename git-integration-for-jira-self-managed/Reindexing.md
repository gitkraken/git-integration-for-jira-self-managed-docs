---

title: Reindexing
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Reindexing

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930399289/Reindexing>

* * *

**Permissions**  
You must be a member of the **jira-developers** _group_ to start reindex.

Synchronization between the repository and app will start automatically. However, reindexing may be required to manually start the synchronization process.

## Getting started

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399289/gitserver-gitmgr-reindex-all-reindex-actions.png?version=1&modificationDate=1630642930639&cacheVersion=1&api=v2)

There are two ways to do this:

1.  To start update of all repositories, go to the **Git Integration for Jira** app git configuration page then click **Reindex All** button. Once synchronization is started, the progress will be displayed on this tab.
    
2.  If a specific repository or integration needs to be synchronized, click the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** icon then **Reindex**.
    

|     |
| --- |
| JIRA SERVER DATA CENTER |
| Click the view ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) icon to see the reindex progress of the selected repository. |

**Initial Synchronization**  
Git log entries may not immediately appear when you open _**Git Commits**_ tab right after the app installation. You need to wait until the revision indexer job completes the initial synchronization.

**Reindex API**  
For advanced administrators who want to have more control on reindex, see the [Git Integration for Jira Reindex API](/wiki/spaces/GIJDC/pages/380699270/Reindex+API).

**Scheduler**  
As of Jira 6.3.10+, Atlassian added the **Scheduler Administration** (_Administration_ ➜ _System_ ➜ _Scheduler Details_) page. This page displays the properties of the Jira internal scheduler, the scheduled jobs and their triggers.

The Repository Reindex (_**GitRevisionIndexerJob**_) can be configured in the [General settings](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398111/General+settings) page of the Git Integration for Jira app.

## Last indexed revision

The Git Integration for Jira app stores the ID of the last indexed commit for each branch. This ID is used to limit the processed data upon reindex or update. This way, only new commits will be indexed on the next synchronization.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930399289/gitserver-gitmgr-actions-reset-index.png?version=1&modificationDate=1630642930870&cacheVersion=1&api=v2)

On the Manage git repositories page, click ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) **Actions** then **Reset index** to reset the _**Last**_ _**Indexed**_ date. Perform this process whenever the Git Integration for Jira app is updated or re-installed.

## Reindex and updatedDate filter

The Git Integration for Jira app automatically changes the **updatedDate** of an issue when a Git commit is added to an issue upon reindex. When the reindex encounters a commit previously modified by the user relating to an issue, that issue will be updated.

You can enable or disable this setting in the [Git Integration for Jira app - General Settings](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398111/General+settings) page ➜ **Jira Issue Updates**.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399289/gitserver-gencfg-last-updated-field.png?version=1&modificationDate=1630642931102&cacheVersion=1&api=v2&width=557&height=386)

As of **v2.5.16+**, the Git Integration for Jira app updates the **"updatedDate"** field whenever a commit is made.

## Indexing errors

Starting v3.6+ of the Git Integration for Jira app, indexer will show an error message on the Jira issue ➜ Git Commits tab.

### Jira Server

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930399289/git-server-indexing-error-sample.png?version=1&modificationDate=1630642930175&cacheVersion=1&api=v2&width=442&height=131)

Cancelling indexing from the Git Integration admin interface is not currently possible. See [workaround in the Known issues page](https://bigbrassband.atlassian.net/wiki/spaces/GITSERVER/pages/591986701/Known+Issues#Fully-Cancelling-an-Ongoing-Indexing-is-Not-Possible).

[« Jira project page](/wiki/spaces/GIJDC/pages/1930399252/Jira+project+page)

[JQL searching »](/wiki/spaces/GIJDC/pages/1930399338/JQL+searching)