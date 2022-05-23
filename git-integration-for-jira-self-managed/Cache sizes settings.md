---

title: Cache sizes settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
These settings are part of the [**General Settings**](/git-integration-for-jira-self-managed/General-Settings) configuration page.

VERSION 4.0.1+ This setting group is now moved to the **Advanced settings** in General settings.

## What is revision cache size?

It displays how many commits/revisions are stored in the memory. The cache size is measured per piece where the approximate revision size is 256 bytes. For instance, there are 4000 revisions per 1 Mb. Set the revision cache size value to 4000 to allocate 1Mb of heap for the cache.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1207828850/gitserver-gencfg-cache-sizes-new.png?version=1&modificationDate=1640601505018&cacheVersion=1&api=v2&width=680&height=290)

The above settings are the sizes of their respective memory cache. Higher values can affect the performance of the retrieved revisions from Git.

## Revision cache size

_Required._  This is the number of revisions that will be kept as cache in memory for quick retrieval – per piece is 256 bytes. The default value for this setting is **180,000**. (approx. ~44Mb)

## Branch cache size

_Required._  This is the number of branches that will be kept as cache in memory for quick retrieval --per piece is 500 bytes. The default value for this setting is **28,000**. (approx. ~13Mb+)

## Tags cache size

_Required._  This is the number of tags that will be kept in cache memory for quick retrieval – per piece is 1000Kb.  The default value for this setting is **500**. (approx. ~488Mb+)

* * *

## Where do I start on how to get the best value setting?

Calculating for the most desirable value depends on the following factors such as how many issues are currently active; and how many commits are associated with the active issues on average. For example, if you have 100 active issues and multiply it by 10 commits per issue, you’ll get around 1000 commits. This is considered a minimal amount.

```java
100 active issues x 10 (average commits per issue) ≈ 1000 commits
```

When the Git Integration for Jira app can’t find a commit in the internal cache, it will start reading for commits from the disk. Read operations finish much quicker when performed from the memory compared to when reading from the disk.

