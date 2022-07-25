# Example of a script pinging reindex status. gijFacade.doReindexSynchronized(repoId) does similar thing.

```
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.IndexStatusResponse;

@PluginModule
GIJFacade gijFacade;

int REPO_ID = 1;
String threadId = gijFacade.doReindex(REPO_ID);

boolean isFinished = false;
while (!isFinished) {
    Thread.sleep(200);
    IndexStatusResponse res = gijFacade.getReindexStatus(threadId);
    isFinished = res.finished;
    log.error(res.toString() + " " + res.getMessages().last().toString());
}
```
