---

title: Pull request filters
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#FFF1B6; padding:1px 5px; color:#172A4C; border-radius:3px; margin: 0 5px; font-size: small;'>NEW FEATURE</b> <b style='background-color:#E2FCEF; padding:1px 5px; color:#006745; border-radius:3px; margin: 0 5px; font-size: small;'>VERSION 4.19+</b>

This feature allows administrators to hide pull requests and branches based on a filter/regex. The Git Integration for Jira app supports integration or repository level filter.

The PR filter is available on the following locations:

1.  **Integration Feature Settings page** – ![](/wp-content/uploads/actions-icon.png)&nbsp; Actions ➜ Edit integration feature settings

    ![Pull request filter location 1](/wp-content/uploads/gij-gitserver-pr-hide-filter-location-01.png)

2.  **Update Repository page (integration sub repository)** – ![](/wp-content/uploads/actions-icon.png)&nbsp; Actions ➜ Show integration repositories

    ![Pull request filter location 2](/wp-content/uploads/gij-gitserver-pr-hide-filter-location-02.png)

<div class="bbb-callout bbb--error">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The PR filter is not available on the following locations:
        <ul style='margin-bottom:0px'>
            <li>Update Repository page for plain repository – <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Edit repository settings.</li>
            <li>Update Repository page for repositories belonging to a tracked folder – <img src='/wp-content/uploads/actions-icon.png' /> Actions ➜ Edit repository settings.</li>
        </ul>
    </div>
    </div>
</div>

&nbsp;

### Basic regex examples

*   The `prHideFilter` will hide PR starting with word/phrase "\[mq-bot\]", e.g. "\[mq-bot\] This is a test Pull Request".

    `^[mq-bot].*`

*   The `prHideFilter` will hide PR starting with word/phrase "Test" or "test", e.g. "Test Pull Request".

    `^(Test|test).*`

&nbsp;

### More advanced examples

For the example list of PRs (or MRs): TEST-1 pr\_1, TEST-1 pr\_2, TEST-1 pr\_23, TEST-1 pr\_3, TEST-1 pr\_4 – the following expressions can be used:

<!-- md and char esc don't work on the regexp code preview therefore I'll have to use the html table here -->

<table>
    <thead style='text-align:left;'>
        <tr>
            <th>Action</th>
            <th>RegExp</th>
            <th>Hide result</th>
            <th>PR list result</th>
        </tr>
    </thead>
    <tbody style='text-align:left;'>
        <tr>
            <td width=38%>Hide all PRs</td>
            <td width=26%><code>.*</code></td>
            <td width=18%>all</td>
            <td width=18%><i>none</i></td>
        </tr>
        <tr>
            <td>Hide only <b>TEST-1 pr_1</b></td>
            <td><code>((^|, )(TEST-1 pr_1))+$</code></td>
            <td>TEST-1 pr_1</td>
            <td>TEST-1 pr_2<br>TEST-1 pr_23<br>TEST-1 pr_3<br>TEST-1 pr_4</td>
        </tr>
        <tr>
            <td>Hides anything that does NOT contain the <b>TEST-1 pr_2</b> phrase</td>
            <td><code>^((?!TEST-1 pr_2).)*$</code></td>
            <td>TEST-1 pr_1<br>TEST-1 pr_3<br>TEST-1 pr_4</td>
            <td>TEST-1 pr_2<br>TEST-1 pr_23</td>
        </tr>
        <tr>
            <td>Hide all PRs <b>BUT TEST-1 pr_2</b></td>
            <td><code>^((?!((^|, )(TEST-1 pr_2))+$).)*$</code></td>
            <td>TEST-1 pr_1<br>TEST-1 pr_23<br>TEST-1 pr_3<br>TEST-1 pr_4</td>
            <td>TEST-1 pr_2</td>
        </tr>
        <tr>
            <td>Hide some PRs: <b>TEST-1 pr_1</b>, <b>TEST-1 pr_2</b>, <b>TEST-1 pr_3</b></td>
            <td><code>((^|, )(TEST-1 pr_[1-3]))+$</code></td>
            <td>TEST-1 pr_1<br>TEST-1 pr_2<br>TEST-1 pr_3</td>
            <td>TEST-1 pr_23<br>TEST-1 pr_4</td>
        </tr>
    </tbody>
</table>

&nbsp;

### See more Git Integration for Jira app features

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

[Cancel indexing](/git-integration-for-jira-data-center/cancel-indexing-revision-indexing-gij-self-managed/) (Git Integration for Jira Data Center)

**Pull request filters** (this page)

[Tag filters](/git-integration-for-jira-data-center/tag-filters-gij-self-managed/) (Git Integration for Jira Data Center)

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

