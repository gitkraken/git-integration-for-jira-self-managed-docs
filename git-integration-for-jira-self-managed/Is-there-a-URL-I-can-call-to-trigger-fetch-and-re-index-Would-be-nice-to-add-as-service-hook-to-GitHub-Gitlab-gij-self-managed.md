---

title: Is there a URL I can call to trigger fetch and re-index? Would be nice to add as service hook to GitHub/Gitlab.
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

Yes  –  the following url can be used:

```java
http://<server url>/secure/StartReindexGitRepositories.jspa?reindex=true
```

The reindex process won't start if reindex is already running.

