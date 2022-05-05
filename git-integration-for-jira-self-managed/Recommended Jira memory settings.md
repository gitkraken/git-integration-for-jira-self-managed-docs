---

title: Recommended Jira memory settings
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Recommended Jira memory settings

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/873332818/Recommended+Jira+memory+settings>

* * *

This page is about how to configure/allocate memory to Jira to accommodate large repositories and avoid OutOfMemory exceptions.

The approximate plugin memory usage should be 2 times the size of the repository indexes.

The approximate plugin memory usage should be 4 times the size of the repository indexes during GC.

The Git Integration for Jira app uses the JGit library ([https://www.eclipse.org/jgit/](https://www.eclipse.org/jgit/)) to read git repositories. This library loads all index files into the memory. In our experience, it consumes memory about twice more than the size (in bytes) of these files. These indexes are internal structures of the git database and contain information about all objects in the git database.

The JGit library implementation loads all indexes into the memory to simplify and speed up navigation in the git database.

**For example:**  
If these repository indexes are 110 Mb then our plugin will require about 0.25 Gb memory during usual reindex and about 0.5 Gb memory (110 x 4) in peaks (i.e. when the Git GC procedure is running). It's only for this single repository.

When you connect several repositories, the required memory will be the sum of the required memory for each repository. Fortunately, that 4x memory in the peaks is required only for the biggest repository because Git GC is performed on a per-repository basis and only in one repository at a time.

For troubleshooting out of memory errors related to this issue, see [Avoid OutOfMemory exceptions by configuring or memory allocation with Jira to accommodate large repositories](/wiki/spaces/GIJDC/pages/873332786/Avoid+OutOfMemory+exceptions+by+configuring+or+memory+allocation+with+Jira+to+accommodate+large+repositories).