---

title: Javadocs example - Create a new pull/merge request
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.scriptrunner.models.PullRequest;


@PluginModule
GIJFacade gijFacade;

int REPO_ID = 2;
gijFacade.createPullRequest(REPO_ID, "TST-4-branch", "main", "Title - Test PR to be closed", "TST-4");
```
