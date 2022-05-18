---

title: How do Git commits get associated with a Jira issue?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
On every Git commit, make sure the message includes the exact issue ID at the beginning of the text. Git Integration for Jira app will automatically index new commits and associate the referenced issue.

To create a link between your Git commit and a Jira issue, developers must include the issue key into the commit comment.

Example git commit message:

"`PROJ-913 - Plugin version change from 2.6.7 to 2.6.8`"; where _**PROJ-913**_ is the issue key that links the commit message to the Jira issue.

If you want to enforce the commit with a hook, please install this [**Git commit hook script »**](/wiki/spaces/GIJDC/pages/92209994/Commit-msg+Hook).

*   Page:

    [How do Git commits get associated with a Jira issue?](/wiki/spaces/GIJDC/pages/2051571713)

*   Page:

    [How do I ensure people are following our organization's process for source code?](/wiki/spaces/GIJDC/pages/2051768321)

*   Page:

    [What will happen to Jira issue associations with commits if the Jira issue is moved to a new project?](/wiki/spaces/GIJDC/pages/2051014669)

*   Page:

    [What are developer licenses?](/wiki/spaces/GIJDC/pages/2051964929)

*   Page:

    [How to associate a commit, branch or pull request AFTER it has been created?](/wiki/spaces/GIJDC/pages/2062974977)