---

title: Glossary and terms
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
### Git

Git is a term used for version control system to easily track changes in one or more of files. Git is a source code repository where developers keep track of their source code using Git.

### Branch

Branch is a temporary copy of source code for a single purpose like adding a particular feature or fixing a bug.

### Merge

Merge is safely moving the changes from one branch back to another – usually, merge to master.

### Jira Server

Jira Server is a self-hosted Jira Software which runs centrally on your own server; be it hosted by AWS or other hosting services.

### Jira Cloud

Jira Cloud is a part of the Cloud service hosted by Atlassian and sells them as a subscription service.

### Issue Key

The issue key is a combination of project key and issue number. For example, the project key is called `TEST` and there's an issue `#123` in the `TEST` project. The resulting issue key would be `TEST-123`. Include the issue key in the commit message so that the pushed commits will be associated to that issue and can be viewed inside Jira.

### Remote repository

Remote repository is the central hosting used by your team for pushing commits and pulling updates.

### Local repository clone 

Clone of remote repository is located on the same server as your Jira service. It is cached locally for performance reasons and queried every time the list of git commits is displayed.

### Lucene indexes 

Lucene is an index service within your Jira instance. It ships with Jira and Git Integration for Jira app also makes use of it. The Git Integration app keeps a separate index stored in ‘`home/caches/indexes/plugins/jira-git-revisions`’.

This database stores information about all commits _(comment, author, etc)_ as well as the branch name which the commit belongs to.

### GitRevisionIndexerJob 

Revision indexer is the background job that is running within your Jira instance. This background job is executed every several minutes _(delay is configurable in the Jira services configuration screen)_.

For every configured repository, this process do the following:

*   Updates the local clone of repository

*   Updates the lucene indexes with commits added recently


Due to the async structure of the Git Integration for Jira app, commits that have been registered with index become visible after the revision indexer job has been executed. To show commits immediately, you have to start the reindex manually.

[« Localization support](/wiki/spaces/GIJDC/pages/1930399433/Localization+support)

[Licensing notice »](/wiki/spaces/GIJDC/pages/1930399465/Licensing+notice)