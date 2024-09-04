---

title: Git Integration + ScriptRunner
description: 
taxonomy:
    category: git-integration-for-jira-data-center

---

[ScriptRunner for Jira Data Center/Server](https://marketplace.atlassian.com/apps/6820/scriptrunner-for-jira?hosting=datacenter&tab=overview) is an app available on the Atlassian Marketplace that allows you to extend Jira functionality through the use of built-in and custom groovy scripts. It provides administrators with an in-line editor where you can write groovy scripts.

These scripts can be scheduled as a job or to be run on an issue transition within Jira workflows or etc. Out-of-the-box, you can find several built-in scripts ready to go, or you may try some recipes to start using a bit of groovy for custom scripts.

&nbsp;

### Available APIs

Which APIs or functions can be used while creating these scripts? See [ScriptRunner API quick reference](https://scriptrunner.adaptavist.com/latest/jira/behaviours-api-quickref.html) at Adaptavist.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Git Integration for Jira app provides additional Java API (<a href='/git-integration-for-jira-data-center/scriptrunner-javadoc-git-services-GIJFacade-gij-self-managed'>GIJFacade interface</a>) allowing you to operate with git information. The API is close to <a href='/git-integration-for-jira-data-center/REST-API-gij-self-managed'>Git Integration for Jira REST API</a> and provides similar functionality (and more):<br>
        <ul>
            <li><b>Repositories</b> - get list of repositories connected, create/delete/update a repository</li>
            <li><b>Integrations</b> - get list of integrations connected, create/delete/update an integration</li>
            <li><b>Reindex</b> - start a reindex of repository/integration, check whether the reindex is finished</li>
            <li><b>Commits</b> - get commits associated with an issue, change a commit issue association</li>
            <li><b>Branches</b> - get branches associated with an issue, create/delete branch</li>
            <li><b>Tags</b> - get tags associated with an issue</li>
        </ul>
    </div>
    </div>
</div>

<br>

A singleton implementing [GIJFacade interface](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-services-GIJFacade-gij-self-managed) is the main object having methods for all the above cases.

&nbsp;

### Feature use case examples

*   The API allows you to write a script for re-associating git commits from one issue to another. With this script, you won't have to click each git commit and manually re-assign it to another issue.

*   Use a script to create a pull request if an issue has been moved to `CODE REVIEW` status.

&nbsp;

### Tutorial

Follow the order of steps below:

- [Available APIs](#available-apis)
- [Feature use case examples](#feature-use-case-examples)
- [Tutorial](#tutorial)
- [Getting started with ScriptRunner plugin](#getting-started-with-scriptrunner-plugin)
- [Example 1: How to create a simple script?](#example-1-how-to-create-a-simple-script)
- [Example 2: How to log?](#example-2-how-to-log)
- [Example 3: How to log more than a brief information?](#example-3-how-to-log-more-than-a-brief-information)
  - [So how does it work?](#so-how-does-it-work)
- [Example 4: Move an issue in "IN PROGRESS" status when at least one git commit exists](#example-4-move-an-issue-in-in-progress-status-when-at-least-one-git-commit-exists)
- [How to integrate the code into workflow? How to customize it by dynamic IN issueKey parameter?](#how-to-integrate-the-code-into-workflow-how-to-customize-it-by-dynamic-in-issuekey-parameter)
- [Let's test it](#lets-test-it)
- [See more Git Integration for Jira app features](#see-more-git-integration-for-jira-app-features)

For more example scripts, see GIJFacade [JavaDocs](/git-integration-for-jira-data-center/ScriptRunner-javadoc-git-services-GIJFacade-gij-self-managed).

&nbsp;

### Getting started with ScriptRunner plugin

For Jira Server/Data Center, you will need to download and install ScriptRunner plugin from the Atlassian Marketplace.
No further GIJ configuration is required.

**Downloading the app**

1.  Go to [ScriptRunner for Jira](https://marketplace.atlassian.com/apps/6820/scriptrunner-for-jira?tab=overview&hosting=server) at Atlassian Marketplace and start the free trial or buy it now.

2.  Login to your Atlassian account when prompted and generate a new license for the trial.

3.  **IMPORTANT!** Make sure to copy your license and save it.

4.  Click **Download** to download the app to your local system.

<br>

**Installing the app**

<b style='color: #63B9CC'>REQUIRES ADMIN ACCESS</b>

1.  On your Jira Server/Data Center instance, navigate to Manage apps (Jira settings ➜ Manage apps ➜ **Manage apps**).

    ![](/wp-content/uploads/gij-jira-admin-cfg-manage-apps-upload-app-sel-c.png)

2.  Click **Upload app** and locate the downloaded ScriptRunner JAR file.

3.  After the installation, look under the User-installed apps and open the **ScriptRunner for Jira** tab.

4.  Paste the license key into the provided box then click **Update**.

&nbsp;

### Example 1: How to create a simple script?

<b style='color: #63B9CC'>REQUIRES ADMIN ACCESS</b>

Preconditions:
*   GIJ plugin is installed.
*   One or more repository is connected.
*   A Jira issue (e.g. TST-4) having git commits association in the Git Commits issue tab.
  
If one of the above conditions is not met, the script will return an empty list.

  ![](/wp-content/uploads/gijfacade-issue-with-commits.png)

<br>

Steps:
*   Open ScriptRunner console (Jira settings ➜ Manage apps ➜ ScriptRunner **Console**). Here you can experiment with scripts, debug scripts, and execute scripts.

    ![](/wp-content/uploads/gijfacade-empty-console.png)

<br>

*   Input the next code:

    ```groovy
    import com.onresolve.scriptrunner.runner.customisers.WithPlugin
    import com.onresolve.scriptrunner.runner.customisers.PluginModule
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.services.GIJFacade;

    @PluginModule
    GIJFacade gijFacade;

    gijFacade.getCommitsForIssue("TST-4");
    ```

*   Press the "Run" button

    ![](/wp-content/uploads/gijfacade-getCommitsForIssue-1.png)

*   A result of the last operation is displayed at the bottom in "Result" tab.
  
    In our case the last operation is `gijFacade.getCommitsForIssue("TST-4");` so the tab displays a list of commits associated with issue "TST-4.
  
<div class="bbb-callout bbb--info">
  <div class="irow">
    <div class="ilogobox">
      <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
      Please be aware that a brief information of the objects are logged by default. For instance, each commit object in the list contains much more information about a commit which can be acquired programmatically. See <a href='/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-Commit-gij-self-managed/'>Commit</a> class javadocs to find a full list of information provided.
    </div>
  </div>
</div>

&nbsp;
  
### Example 2: How to log?

*   Pay close attention to the "Logs" tab at the bottom. There can be a lot of logs while there is only one result.
  
    Use `log.warn("Your message")` to log something.
  
*   Do a log for commits and number of changed files. Enter the following script in the ScriptRunner console:
  
    ```groovy
    import com.onresolve.scriptrunner.runner.customisers.WithPlugin
    import com.onresolve.scriptrunner.runner.customisers.PluginModule
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.services.GIJFacade;
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.rest.publicmodels.Commit;
    import java.util.function.Consumer;

    @PluginModule
    GIJFacade gijFacade;

    gijFacade.getCommitsForIssue("TST-4", true)
        .stream()
        .forEach(new Consumer<Commit>() {
            @Override
            public void accept(Commit commit) {
                log.warn("commit " + commit.getCommitId());
                log.warn("\\t number of files changed - " +commit.getFiles().size());
            }
        }
    );
    ```

*   Click the "Run" button.

*   Switch to the "Logs" tab.

    ![](/wp-content/uploads/gijfacade-scriptrunner-logs-tab.png)

&nbsp;

### Example 3: How to log more than a brief information?

*   As mentioned above, a commit is logged using brief information by default.
  
    For example, files are not logged but are present in commit objects when you retrieve them with help of `gijFacade.getCommitsForIssue("TST-4", true)`.
  
    Refer to [Commit JavaDocs](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-rest-publicmodels-Commit-gij-self-managed) and log commits with files in a nice-looking format. Enter the following script in the ScriptRunner console:
  
    ```groovy
    import com.onresolve.scriptrunner.runner.customisers.WithPlugin
    import com.onresolve.scriptrunner.runner.customisers.PluginModule
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.services.GIJFacade;
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.rest.publicmodels.Commit;
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.rest.publicmodels.Commit.ShortFileInfo;
    import java.util.function.Consumer;

    @PluginModule
    GIJFacade gijFacade;

    gijFacade.getCommitsForIssue("TST-4", true)
        .stream()
        .forEach(new Consumer<Commit>() {
            @Override
            public void accept(Commit commit) {
                log.warn(commit.getCommitId());
                commit.getFiles()
                    .stream()
                    .forEach(new Consumer<ShortFileInfo>() {
                        @Override
                        public void accept(ShortFileInfo file) {
                            log.warn("\\t\\t" + file.getPath());
                        }
                    });
            }
        }
    );
    ```

*   Switch to the "Logs" tab. Here you can see the commits with files. It now looks great when viewed.
  
    ![](/wp-content/uploads/gijfacade-example-with-commits-and-files.png)

&nbsp;

#### So how does it work?

Looking back at the original script, see how it was changed:

*   We've added more imports to avoid compilation error

*   We've called `gijFacade.getCommitsForIssue("TST-4", true)` instead of `gijFacade.getCommitsForIssue("TST-4")`. Otherwise, the list of files will be empty.

*   We've looped throughout the commits:

    ```groovy
    gijFacade.getCommitsForIssue("TST-4", true)
        .stream()
        .forEach(new Consumer<Commit>() {
            @Override
            public void accept(Commit commit) {        
                log.warn(commit.getCommitId());
                ...
            }
        }
    );
    ```

*   and then, looped throughout the files belonging to each commit:

    ```groovy
    ...
        commit.getFiles()
        .stream()
        .forEach(new Consumer<ShortFileInfo>() {
            @Override
            public void accept(ShortFileInfo file) {
                log.warn("\\t\\t" + file.getPath());
            }
        });
    ...
    ```

&nbsp;

### Example 4: Move an issue in "IN PROGRESS" status when at least one git commit exists

Let's write, debug a code and detect whether an issue has at least one git commit:

*   Open ScriptRunner console (Jira settings ➜ Manage apps ➜ ScriptRunner **Console**).

*   Use the next code:

    ```groovy
    import com.onresolve.scriptrunner.runner.customisers.WithPlugin
    import com.onresolve.scriptrunner.runner.customisers.PluginModule
    @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
    import com.bigbrassband.jira.git.services.GIJFacade;

    @PluginModule
    GIJFacade gijFacade;

    String issueKey = "TST-4";
    !gijFacade.getCommitsForIssue(issueKey).isEmpty();
    ```

*   Click **Run**.
  
*   Open **Result** tab.
  
    `Result: "true"`
  
*   Assign a Jira issue key value to the `String issueKey` variable. For example: `String issueKey = "TST-4";` The above code will return `true` if the Jira issue has git commits and `false` if it doesn't.

&nbsp;

### How to integrate the code into workflow? How to customize it by dynamic IN issueKey parameter?
  
The steps below demonstrate the general rule of using gijFacade in ScriptRunner features:

*   Create a `ScriptRunner Listener` which will be triggered by adding a comment to an issue. If the issue has git commits, the listener will transition the issue to the `IN PROGRESS` status.

    *   Open ScriptRunner Listeners (Jira settings ➜ Manage apps ➜ ScriptRunner **Listeners**).

        ![](/wp-content/uploads/gijfacade-scriptrunner-listeners.png)

    *   Click **Create Listener**.

    *   Find and choose **Fast-track transition an issue**.

        ![](/wp-content/uploads/gijfacade-scriptrunner-transition-listener.png)

    *   Set up the new listener.

        ![](/wp-content/uploads/gijfacade-scriptrunner-listener-settings.png)

    *   Set **Event** to `Issue Commented`.

    *   Use the following code into the **Condition** field:  

        ```groovy
        import com.onresolve.scriptrunner.runner.customisers.WithPlugin
        import com.onresolve.scriptrunner.runner.customisers.PluginModule
        @WithPlugin("com.xiplink.jira.git.jira_git_plugin")
        import com.bigbrassband.jira.git.services.GIJFacade;

        @PluginModule
        GIJFacade gijFacade;

        String issueKey = issue.key;
        !gijFacade.getCommitsForIssue(issueKey).isEmpty();
        ```

    *   Set **Action** to `Start Progress`.

    *   Under **Transition Options** -- tick on the following:

        *   `Skip Permissions`, 
        *   `Skip Validators`, 
        *   `Skip Conditions` (just in case)
<br><br>

    *   Click **Add**.

&nbsp;

### Let's test it

1.   Open the TST-4 Jira issue, which is in `OPEN` status and has associated git commits.

2.   Add comment `Some comment`.

<br>

**Result:**<br>
The Jira issue status becomes `IN PROGRESS` because it has git commits.

&nbsp;

### See more Git Integration for Jira app features

[Manager permissions](/git-integration-for-jira-data-center/manager-permissions-gij-self-managed) (Git Integration for Jira Data Center)

[Cancel indexing](/git-integration-for-jira-data-center/cancel-indexing-revision-indexing-gij-self-managed/) (Git Integration for Jira Data Center)

[Pull request filters](/git-integration-for-jira-data-center/pull-request-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Tag filters](/git-integration-for-jira-data-center/tag-filters-gij-self-managed/) (Git Integration for Jira Data Center)

[Indexing queue viewer](/git-integration-for-jira-data-center/indexing-queue-viewer-gij-self-managed/) (Git Integration for Jira Data Center)

[Deep linking feature](/git-integration-for-jira-data-center/deeplinking-feature-gij-self-managed/) (Git Integration for Jira Data Center)

[GitHub App integration](/git-integration-for-jira-data-center/github-app-integration-gij-self-managed/) (Git Integration for Jira Data Center)

**Git Integration + ScriptRunner** (this page)

[Git Integration + Jira Automation](/git-integration-for-jira-data-center/git-integration-plus-jira-automation-gij-self-managed/) (Git Integration for Jira Data Center)

[Enforced git permissions for Jira users – Features](/git-integration-for-jira-data-center/enforced-git-permissions-for-jira-users-gij-self-managed/) (Git Integration for Jira Data Center)

[Shared reindex queue between DC nodes](/git-integration-for-jira-data-center/shared-reindex-queue-between-dc-nodes-gij-self-managed/) (Git Integration for Jira Data Center)

[Smart commits overview](/git-integration-for-jira-data-center/smart-commits-overview-gij-self-managed/) (Git Integration for Jira Data Center)

[Associate Pull/Merge Requests to Issues Based on Commits](/git-integration-for-jira-data-center/associate-pull-merge-requests-to-issues-based-on-commits-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating branches](/git-integration-for-jira-data-center/creating-branches-gij-self-managed/) (Git Integration for Jira Data Center)

[Creating pull/merge requests](/git-integration-for-jira-data-center/creating-pull-merge-requests-gij-self-managed/) (Git Integration for Jira Data Center)

[Issue Git integration panel – Features](/git-integration-for-jira-data-center/issue-git-integration-panel-gij-self-managed/) (Git Integration for Jira Data Center)

