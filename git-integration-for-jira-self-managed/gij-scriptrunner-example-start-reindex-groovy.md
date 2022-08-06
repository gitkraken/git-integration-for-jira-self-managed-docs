# Example of a script starting reindex of a repository

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.IndexStatusResponse;

@PluginModule
GIJFacade gijFacade;

int REPO_ID = 1;
gijFacade.doReindex(REPO_ID);
```
