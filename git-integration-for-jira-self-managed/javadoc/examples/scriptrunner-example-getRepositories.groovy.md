```
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;

@PluginModule
GIJFacade gijFacade;

gijFacade.getRepositories();
```
