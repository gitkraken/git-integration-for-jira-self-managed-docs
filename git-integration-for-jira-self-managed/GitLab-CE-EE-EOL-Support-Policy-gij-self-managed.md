---

title: GitLab CE/EE EOL Support Policy
description: "Understand GitLab's release support and security backport policy for self-managed GitLab CE and EE."
product: Git Integration for Jira Data Center
feature: Policies (EOL / SLA)
content_type: policy
audience: admin
plan_required: [all]
deployment: Jira Data Center
git_hosts: [gitlab-self-managed]
role_required: [all]
version_required: all
status: GA
last_verified: 2022-11
llms_include: true
tags: [gitlab ce/ee, support policy, security backports, patch releases]
taxonomy:
    category: git-integration-for-jira-data-center

custom_fields:
    nav_category: "git-services-support-page"
    nav_label: "GitLab CE/EE EOL Support Policy"
    nav_order: 20
    nav_parent: "git-services-support-page"
    page_type: "content"
    git_hosts: ["gitlab-self-managed"]
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

