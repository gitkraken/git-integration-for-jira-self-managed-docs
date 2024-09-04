---

title: Tag filters
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- FEATURES -->

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b> <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.19+</b>

This feature allows administrators to use tag filters to define which tags are only displayed in the Git integration developer panel.

The tag filter is available on the following locations:

1.  **Integration Feature Settings page** – ![](/wp-content/uploads/actions-icon.png)&nbsp; Actions ➜ Edit integration feature settings

    ![Pull request filter location 1](/wp-content/uploads/gij-gitserver-tags-filters-feature-location-01.png)

2.  **Update Repository page (integration sub repository)** – ![](/wp-content/uploads/actions-icon.png)&nbsp; Actions ➜ Show integration repositories

    ![Pull request filter location 2](/wp-content/uploads/gij-gitserver-tags-filters-feature-location-02.png)

&nbsp;

### Basic regex examples

*   The below example will show tags starting with word/phrase "\[version-1\]", e.g. "\[version-1\] This is a test tag".

    `^(version\-1).*`

*   The below example will show tags starting with word/phrase "Release" or "release", e.g. "Release sprint 1.0.9".

    `^(Release|release).*`

&nbsp;

### More advanced examples

For the example list of tags: release-1, release-2, release-2.3, release-3, release-4 – the following expressions can be used:

<!-- lots of esc chars that don't display well in markdown mode so had to use the html table here -->

<table>
    <thead style='text-align:left;'>
        <tr>
            <th>Action</th>
            <th>RegExp</th>
            <th>Hide result</th>
            <th>Tags list result</th>
        </tr>
    </thead>
    <tbody style='text-align:left;'>
        <tr>
            <td width=38%>Show all tags</td>
            <td width=26%><code>.*</code></td>
            <td width=18%>none</td>
            <td width=18%>release-1<br>release-2<br>release-2.3<br>release-3<br>release-4</td>
        </tr>
        <tr>
            <td>Show only <b>release-1</b></td>
            <td><code>((^|, )(release-1))+$</code></td>
            <td>release-2<br>release-2.3<br>release-3<br>release-4</td>
            <td>release-1</td>
        </tr>
        <tr>
            <td>Shows anything that does <b>NOT</b> contain the <b>release-2</b> phrase</td>
            <td><code>^((?!release-2).)*$</code></td>
            <td>release-2<br>release-2.3</td>
            <td>release-1<br>release-3<br>release-4</td>
        </tr>
        <tr>
            <td>Show all tags <b>BUT release-2</b></td>
            <td><code>^((?!((^|, )(release-2))+$).)*$</code></td>
            <td>release-2</td>
            <td>release-1<br>release-2.3<br>release-3<br>release-4</td>
        </tr>
        <tr>
            <td>Show some tags: <b>release-1</b>, <b>release-2</b>, <b>release-3</b></td>
            <td><code>((^|, )(release-[1-3]))+$</code></td>
            <td>release-2.3<br>release-4</td>
            <td>release-1<br>release-2<br>release-3</td>
        </tr>
    </tbody>
</table>

&nbsp;

### See more Git Integration for Jira app features

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

[Cancel indexing](/git-integration-for-jira-data-center/cancel-indexing-revision-indexing-gij-self-managed/) (Git Integration for Jira Data Center)

[Pull request filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed/) (Git Integration for Jira Data Center)

**Tag filters** (this page)

[Indexing queue viewer](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/) (Git Integration for Jira Data Center)

[Deep linking feature](/git-integration-for-jira-data-center/deeplinking-feature-gij-self-managed/) (Git Integration for Jira Data Center)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + ScriptRunner](/git-integration-for-jira-data-center/gij-plus-scriptrunner-gij-self-managed/) (Git Integration for Jira Data Center)

[Git Integration + Jira Automation](/git-integration-for-jira-data-center/git-integration-plus-jira-automation-gij-self-managed/) (Git Integration for Jira Data Center)

[Enforced git permissions for Jira users – Features](/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed/) (Git Integration for Jira Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/shared-reindex-queue-between-dc-nodes-gij-self-managed/) (Git Integration for Jira Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed/) (Git Integration for Jira Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/) (Git Integration for Jira Data Center)

[Issue Git integration panel – Features](/git-integration-for-jira-data-center/issue-git-integration-panel-gij-self-managed/) (Git Integration for Jira Data Center)

