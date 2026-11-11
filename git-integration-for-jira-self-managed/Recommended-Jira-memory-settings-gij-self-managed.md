---

title: Recommended Jira memory settings - Administration
description: "Estimate how much memory to allocate to Jira for large repositories, based on JGit index sizes, to avoid OutOfMemory errors."
product: Git Integration for Jira Data Center
feature: Performance and Memory
content_type: reference
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [n/a]
role_required: [Jira Administrator]
version_required: all
status: GA
last_verified: 2023-08
llms_include: true
tags: [memory settings, jgit, repository indexes, outofmemory, garbage collection]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "administration-gij-self-managed"
    nav_label: "Recommended Jira memory settings – Administration"
    nav_order: 80
    nav_parent: "administration-gij-self-managed"
    page_type: "content"
    card_icon: "gauge"
    card_color: "amber"
    card_description: "Estimate how much memory to allocate to Jira for large repositories, based on JGit index sizes, to avoid OutOfMemory errors"
---

<!-- ADMINISTRATION -->

This page is about how to configure/allocate memory to Jira to accommodate large repositories and avoid OutOfMemory exceptions.

> **Tip:** The approximate plugin memory usage should be 2 times the size of the repository indexes.
> <div class='nextpara' style='margin-bottom:-10px'>During GC, the approximate plugin memory usage should be 4 times the size of the repository indexes.</div>

The Git Integration for Jira app uses the JGit library ([https://www.eclipse.org/jgit/](https://www.eclipse.org/jgit/)) to read git repositories. This library loads all index files into the memory. In our experience, it consumes memory about twice more than the size (in bytes) of these files. These indexes are internal structures of the git database and contain information about all objects in the git database.

The JGit library implementation loads all indexes into the memory to simplify and speed up navigation in the git database.

> **Info:** <b>For example:</b><br>
> If these repository indexes are 110 Mb then our plugin will require about 0.25 Gb memory during usual reindex and about 0.5 Gb memory (110 x 4) in peaks (i.e. when the Git GC procedure is running). It's only for this single repository.

When you connect several repositories, the required memory will be the sum of the required memory for each repository. Fortunately, that 4x memory in the peaks is required only for the biggest repository because Git GC is performed on a per-repository basis and only in one repository at a time.

For troubleshooting out of memory errors related to this issue, see [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/git-integration-for-jira-data-center/avoid-outofmemory-exceptions-by-configuring-or-memory-allocation-with-jira-to-accommodate-large-repositories-gij-self-managed).

&nbsp;

## More related Administration articles

[General settings](/git-integration-for-jira-data-center/general-settings-gij-self-managed)

[Upgrades and migrations within same servver](/git-integration-for-jira-data-center/upgrades-and-migrations-within-same-server-gij-self-managed)

[Migration to another server](/git-integration-for-jira-data-center/migration-to-another-server-gij-self-managed)

[Scheduling jobs](/git-integration-for-jira-data-center/scheduling-jobs-gij-self-managed)

**Recommended Jira memory settings** (this page)

[Plugin Data Storage](/git-integration-for-jira-data-center/plugin-data-storage-gij-self-managed)

[Indexing queue explainer](/git-integration-for-jira-data-center/indexing-queue-explainer-gij-self-managed)

