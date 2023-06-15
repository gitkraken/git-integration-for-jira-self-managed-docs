---

title: Comparing branches/tags in Repository Browser
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

<b style='background-color:#DEEAFE; padding:1px 5px; color:#0C42A3; border-radius:3px; margin: 0 5px; font-size: small;'>ALSO IN JIRA CLOUD</b>

On the Repository Browser, click the **Compare** page tab.

![](/wp-content/uploads/gij-gitserver-repo-browser-compare-issues.png)

<Br>

On this page, two branches from the current repository can be compared.

A diff between the _**base**_ branch and the _**compare**_ branch is displayed:

To view desired results, use the following selection scenarios:

*   select **master** as compare; select the most recent branch as compare.

*   select **master** as compare; select a tag with a version release.

*   select different branches as base and compare. (Example: `TYT-212` against `TYT-316`)

&nbsp;

### Functions

Click **…** to swap the base and the compare selection.

The **Summary** page displays the _**Commits**_, _**Aggregated Lines by Developers**_ and _**Files**_. Click on a file to view its code diff.

Click **Commits** on the sidebar to view the list of commits resulting from this compare. The adjacent figure indicates the number of commits associated to this compare.

Click **Diff** on the sidebar to view code diffs of the selected range of commits with the path and name of the affected files.

Click **Issues** on the sidebar to view list of unique Jira issues related to commits.

On the **Issues** page, clicking the **View in Issue Navigator** text label will open the Search page with passed query of a list of Jira issues found based from the compare criteria.

*   For example, the JQL will look like `issuekey in (GIT-1851, GIT-1159, GITCL-284, GITCL-254)`.

&nbsp;
* * *

[Viewing list of commits in Repository Browser](/git-integration-for-jira-data-center/viewing-list-of-commits-in-repository-browser-gij-self-managed)

[Enable/disable Repository Browser via git repository configuration page](/git-integration-for-jira-data-center/enable-disable-repository-browser-via-git-repository-configuration-page-gij-self-managed)


