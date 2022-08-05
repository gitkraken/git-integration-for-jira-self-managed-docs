---

title: ScriptRunner - gijFacade getRepositories(String issueKey) example
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

# Example of a script using gitFacade.getRepositories(String issueKey)

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;

@PluginModule
GIJFacade gijFacade;

gijFacade.getRepositories("TST");
```
