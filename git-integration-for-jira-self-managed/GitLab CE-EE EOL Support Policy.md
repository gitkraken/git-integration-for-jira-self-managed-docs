---

title: GitLab CE/EE EOL Support Policy
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
GitLab’s current policy is to support one stable release at any given time, but for medium-level security issues, GitLab may backport security fixes to the previous two monthly releases. For critical security issues, there is precedent to backport security fixes to even more monthly releases of GitLab. This decision is made on a case-by-case basis.

The patch releases **only include bug fixes** for the current stable released version of GitLab.

These two policies are in place because:

1.  GitLab has Community and Enterprise distributions, doubling the amount of work necessary to test/release the software.

2.  Backporting to more than one release creates a high development, quality assurance, and support cost.

3.  Supporting parallel version discourages incremental upgrades which over time accumulate in complexity and create upgrade challenges for all users. GitLab has a dedicated team ensuring that incremental upgrades (and installations) are as simple as possible.

4.  The number of changes created in the GitLab application is high, which contributes to backporting complexity to older releases. In several cases, backporting has to go through the same review process a new change goes through.

5.  Ensuring that tests pass on the older release is a considerable challenge in some cases, and as such is very time-consuming.


For more information, see [GitLab releases](https://about.gitlab.com/releases/categories/releases/).