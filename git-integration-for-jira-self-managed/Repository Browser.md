---

title: Repository Browser
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Repository Browser

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser>

* * *

The **Repository Browser** allows users to view git repositories of configured projects via the **Git** menu on the Jira dashboard or on the **Applications** sidebar.

## Getting started

**Permissions**  
Users must have the **View Development Tools** _project permission_ in order to gain access to the Repository Browser. For more information on assigning Jira permissions, see [**Managing Permissions in Jira**](https://confluence.atlassian.com/display/Jira/Managing+Global+Permissions).

**Git menu**  
After installing the Git Integration for Jira app, the **Git** dropdown menu is added to the dashboard.

The **Git** header is hidden for all users if there are no repositories with Repository Browser enabled for that user. The Git Integration for Jira app will always show the **Git** header to Jira administrators.

The **Git** header is visible to other users who have repositories with Repository Browser enabled and have no history of using the Repository Browser _(for example - no previously viewed or repositories set as favorite)._

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398598/gitserver-gitmenu-repo-browser.png?version=1&modificationDate=1639221831233&cacheVersion=1&api=v2&width=163&height=111)

## Repository list

Available git repositories of configured projects are displayed.

![Repository browser screen showing list of connected repositories, recent issue, last updated by, last commit and personal access (if require PAT setting is enabled).](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398598/gitserver-repo-browser-view.png?version=1&modificationDate=1630642896363&cacheVersion=1&api=v2&width=680&height=404)

*   Use the search bar to search and filter the Repositories list.
    
*   On the list table, you will see git repositories, recent issues updated by the user, and the last commits made.
    
*   The personal access token configuration column (_Pers. Access_) displays the PAT setup option if require user pat setting is enabled). Click the ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) edit icon to setup PAT to allow branch and PR/MR creation functions via [Jira Git integration development panel](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel). The adjacent checkmark indicates a PAT has already been configured.
    
*   On the bottom left of the list, the view options control how many rows the list will display. The default view is 10 rows. Larger row view affects page loading time.
    
*   On the right of the view options are the pagination options. Use the controls to navigate through the page list.
    

##   
Repository view

Click a git repository under Git repository column to browse its contents and switch to repository view. For example:

![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398598/repo-browser-repo-view(c).png?version=1&modificationDate=1630642897794&cacheVersion=1&api=v2&width=646&height=365)

*   Clicking **Repositories** at the top right of the screen will open the git app repositories page.
    
*   Select a branch from the dropdown list to browse repository contents for that branch _(default view is master branch)_.
    
*   Click a folder to view its contents. Click a file to view its code diff.
    
*   Click on an issue link under **Commit message** to view that ticket.
    
*   Click on the  **Latest commit: UUID** link to view code diff for that commit.
    
*   Click on an item link under **Latest commit** _column_ to view code diff for that particular commit.
    
*   Clicking on the **Repositories** button at the top right of the page returns the view to the Repository Browser.
    

**Commit revisions**  
The revisions of the commits are displayed on the Repository Browser in addition to branches and tags. See [Repository Browser - Git Commits tab](/wiki/spaces/GIJDC/pages/1930398681/Viewing+list+of+commits+in+Repository+Browser) for detailed information.

If the selected path is a _**root**_ of the repository and no files are present, a message will be displayed instead of an empty file list.

**Administration**  
Administrators can turn off the Repository Browser via ![(blue star)](/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit repository settings** in the Git Integration for Jira app configuration.

**Sort header**  
The displayed repositories can be sorted by clicking the corresponding list header. The Git Integration for Jira app will remember the sorting choice per user.

[« Smart commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits)

[Viewing list of commits via Repository Browser »](/wiki/spaces/GIJDC/pages/1930398681/Viewing+list+of+commits+in+Repository+Browser)

### More related topics about Repository Browser

*   Page:
    
    [Repository Browser](/wiki/spaces/GIJDC/pages/1930398598/Repository+Browser) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Viewing list of commits in Repository Browser](/wiki/spaces/GIJDC/pages/1930398681/Viewing+list+of+commits+in+Repository+Browser) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Comparing branches/tags in Repository Browser](/wiki/spaces/GIJDC/pages/1930398705) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Enable/disable Repository Browser via git repository configuration page](/wiki/spaces/GIJDC/pages/1930398739) (Git Integration for Jira Data Center)