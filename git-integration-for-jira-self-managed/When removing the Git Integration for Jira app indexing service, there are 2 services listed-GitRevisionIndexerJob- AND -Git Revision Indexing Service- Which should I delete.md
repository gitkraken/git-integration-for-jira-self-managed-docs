---

title: When removing the Git Integration for Jira app indexing service, there are 2 services listed - "GitRevisionIndexerJob" AND "Git Revision Indexing Service". Which should I delete?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

GitRevisionIndexerJob is the correct one. Keep that job.

Git Revision Indexing Service is an old job and should be removed.

