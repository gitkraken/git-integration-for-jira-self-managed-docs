---

title: Git Roll Up tab
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Git Roll Up tab

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398901/Git+Roll+Up+tab>

* * *

The Git Roll Up tab now allows users to view the code diff between the base and the compare versions.

Open an issue then go to the Git Roll Up tab to view commit statistics, diffs and related issues.

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398901/jira-issue-git-rollup-summary.png?version=1&modificationDate=1630642911973&cacheVersion=1&api=v2&width=680&height=505)

The **Summary** page shows statistical information of the first and last revision of the commits and the time since the last commit was made. A summary of the files, lines and the developers who made the changes in this range of commits are also displayed.

|     |
| --- |
| **Git Compare** |
| The git commit compare function (_Repository Browser - Compare_) is added into this tab:<br><br>*   To view a compare result, set the **base:** and the **compare:** dropdown selectors with different values.<br>    <br>*   The repository dropdown allows switching of context between repositories.  <br>    **Example:** `jira-git-plugin`<br>    <br>*   To swap the base and the compare selection, click **…** _(ellipsis button)_.<br>    <br>*   To open the context of the Git Roll Up issue tab to the Compare page in a new browser tab, click the adjacent pop-out icon.<br>    <br>*   To view the code diff of the compare result, click **Diff** on the left panel.<br>    <br>*   To view the commit statistics and summary of changes, click **Summary** on the left panel.<br>    <br>*   To view list of unique Jira issues related to commits, click **Issues** on the left panel.<br>    <br>    ![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930398901/jira-issue-git-rollup-issues(c).png?version=1&modificationDate=1630642912212&cacheVersion=1&api=v2)<br>    *   On the **Issues** tab, clicking the **View in Issue Navigator** text label will open the Search page with passed query of a list of Jira issues found based from the compare criteria.<br>        <br>    *   For example, the JQL will look like `issuekey in (GIT-1851, GIT-1159, GITCL-284, GITCL-254)`. |

INTRODUCED VERSION 2.10.3+  
The Git Roll Up issue tab will now find the best matching branch name using the Jira issue key to find it. For example, if you have a branch name of `v2.1-ABC-123`, that branch will be automatically selected when you open the Git Roll Up issue tab.

  
Sort the code statistics by clicking the respective **Sort** button then selecting the required sorting option.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930398901/git-rollup-01.png?version=1&modificationDate=1630642912699&cacheVersion=1&api=v2)

Select roll up options by clicking the respective **Rollup** button.

![](https://bigbrassband.atlassian.net/wiki/download/attachments/1930398901/git-rollup-02.png?version=1&modificationDate=1630642912929&cacheVersion=1&api=v2)

To view the code diff of the file, click the corresponding  filename on the **Files** summary table. A dialog will appear displaying the file diff between the first and last revisions of the commit.

[« JIra issue page (index)](/wiki/spaces/GIJDC/pages/1930398870/Jira+issue+page)

[Git Commits tab »](/wiki/spaces/GIJDC/pages/1930398950/Git+Commits+tab)

### More related topics about Jira issue page

*   Page:
    
    [Jira issue page](/wiki/spaces/GIJDC/pages/1930398870/Jira+issue+page) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git Roll Up tab](/wiki/spaces/GIJDC/pages/1930398901/Git+Roll+Up+tab) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git Commits tab](/wiki/spaces/GIJDC/pages/1930398950/Git+Commits+tab) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Code syntax highlighter](/wiki/spaces/GIJDC/pages/1930398989/Code+syntax+highlighter) (Git Integration for Jira Data Center)