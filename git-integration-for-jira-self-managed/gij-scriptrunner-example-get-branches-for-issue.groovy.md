---

title: ScriptRunner - Get branches associated with an issue example
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

# Example of a script returning branches associated with an issue

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;

@PluginModule
GIJFacade gijFacade;

gijFacade.getBranchesForIssue("TST-3");
```
