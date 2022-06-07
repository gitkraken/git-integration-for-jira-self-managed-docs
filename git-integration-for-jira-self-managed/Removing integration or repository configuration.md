---

title: Removing integration or repository configuration
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
Delete a repository or integration if it isn't needed or is broken in the Git Integration for Jira app configuration list.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930397738/gitserver-remove-repo.png?version=1&modificationDate=1630642856115&cacheVersion=1&api=v2&width=680&height=398)

1.  Go to the **Manage Git repositories** page for your Jira instance (_Jira dashboard menu Git ➜ Manage repositories_).

2.  **INTEGRATION**
    Click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Remove integration** for the selected integration configuration.
    
    **REPOSITORY** Click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Remove repository** for the selected repository configuration.

    **TRACKED FOLDER** Click <img src='https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/a51a7674-8d5d-4495-a2d2-a67c090f5c3b/32x32/2699.png' width=20 height=20 /> Actions ➜ **Remove tracked folder** for the selected tracked folder configuration.

3.  The confirmation screen is displayed.
    Uncheck the **Also remove cloned Git repository files...** option to retain git repository files in the displayed path or leave it checked to also delete the repository files from the displayed path.

4.  Click **Delete** to remove the repository. Click **Cancel** to abort this process.

