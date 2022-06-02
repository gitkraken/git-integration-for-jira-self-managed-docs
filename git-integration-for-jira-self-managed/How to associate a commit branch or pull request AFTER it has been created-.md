---

title: How to associate a commit, branch or pull request AFTER it has been created?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
**For commits:** – these can be associated either via [manual association feature](/wiki/spaces/GITSERVER/pages/1923028970/Manually+link+git+commits+to+Jira+issues) of the Git Integration for Jira app or via Git Notes.
**For branches** – these cannot be re-associated after creation because git does not allow branches to be renamed.
**For pull/merge requests** – just editing the PR/MR titles to include the Jira issue and then perform reindex will associate the PR/MR to the specified Jira issue. Also, editing their descriptions will associate the PR/MR to the specified Jira issue as well.

### See next FAQs related to developer questions

*   [How do Git commits get associated with a Jira issue?](/wiki/spaces/GIJDC/pages/2051571713)

*   [How do I ensure people are following our organization's process for source code?](/wiki/spaces/GIJDC/pages/2051768321)

*   [What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?](/wiki/spaces/GIJDC/pages/2051014669)

*   [What are developer licenses?](/wiki/spaces/GIJDC/pages/2051964929)

*   [How to associate a commit, branch or pull request AFTER it has been created?](/wiki/spaces/GIJDC/pages/2062974977)