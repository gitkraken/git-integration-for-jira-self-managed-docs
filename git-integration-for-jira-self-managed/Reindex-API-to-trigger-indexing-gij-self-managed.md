---

title: Reindex API to trigger indexing
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

<!-- getting started for git admins -->

Call the [Reindex REST API](/git-integration-for-jira-data-center/reindex-api-gij-self-managed/) to have more control on indexing.

## Reindex POST API

Use this method to start the reindex process in a separate thread.

**Example:**

```java
http://jira.yourorg.com/rest/gitplugin/1.0/index.json
```

## Reindex GET API

Use this method to track messages for a particular thread.

**Example:**

```java
http://jira.yourorg.com/rest/gitplugin/1.0/index.json?threadId=eafe58fc-d8de-42ff-8815-6fe5860b38d2
```

