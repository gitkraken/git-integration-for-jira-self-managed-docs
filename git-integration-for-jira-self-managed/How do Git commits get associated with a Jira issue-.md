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

