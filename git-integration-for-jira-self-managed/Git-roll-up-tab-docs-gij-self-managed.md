---

title: Git Roll Up tab - Jira issue page
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<!-- jira issue page - git roll up tab documentation -->

The Git Roll Up tab now allows users to view the code diff between the base and the compare versions.

Open an issue then go to the Git Roll Up tab to view commit statistics, diffs and related issues.

<img src='/wp-content/uploads/gij-jira-issue-git-rollup-summary.png' width=680 height=505 style='display:block;margin:25px auto;max-width:100%' />

The **Summary** page shows statistical information of the first and last revision of the commits and the time since the last commit was made. A summary of the files, lines and the developers who made the changes in this range of commits are also displayed.

&nbsp;

### Git Compare

The git commit compare function (_Repository Browser - Compare_) is added into this tab:

*   To view a compare result, set the **base:** and the **compare:** dropdown selectors with different values.

*   The repository dropdown allows switching of context between repositories.<br>
**Example:** `jira-git-plugin`

*   To swap the base and the compare selection, click **…** _(ellipsis button)_.

*   To open the context of the Git Roll Up issue tab to the Compare page in a new browser tab, click the adjacent pop-out icon.

*   To view the code diff of the compare result, click **Diff** on the left panel.

*   To view the commit statistics and summary of changes, click **Summary** on the left panel.

*   To view list of unique Jira issues related to commits, click **Issues** on the left panel.

    ![](/wp-content/uploads/gij-jira-issue-git-rollup-issues-c.png)

*   On the **Issues** tab, clicking the **View in Issue Navigator** text label will open the Search page with passed query of a list of Jira issues found based from the compare criteria.

*   For example, the JQL will look like `issuekey in (GIT-1851, GIT-1159, GITCL-284, GITCL-254)`.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Roll Up issue tab will find the best matching branch name using the Jira issue key to find it. For example, if you have a branch name of <code>v2.1-ABC-123</code>, that branch will be automatically selected when you open the Git Roll Up issue tab.
    </div>
    </div>
</div>
<br>

Sort the code statistics by clicking the respective **Sort** button then selecting the required sorting option.

<img src='/wp-content/uploads/gij-git-rollup-01.png' style='margin:25px auto;max-width:100%;display:block;' />

&nbsp;

Select roll up options by clicking the respective **Rollup** button.

<img src='/wp-content/uploads/gij-git-rollup-02.png' style='margin:25px auto;max-width:100%;display:block;' />

<br>

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        To view the code diff of the file, click the corresponding  filename on the <b>Files</b> summary table. A dialog will appear displaying the file diff between the first and last revisions of the commit.
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Jira issue page](/git-integration-for-jira-data-center/jira-issue-page-gij-self-managed)

[**Next:** Git Commits tab](/git-integration-for-jira-data-center/git-commits-tab-gij-self-managed)


