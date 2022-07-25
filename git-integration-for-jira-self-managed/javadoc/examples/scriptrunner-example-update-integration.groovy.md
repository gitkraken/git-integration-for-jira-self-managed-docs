# Example of a script updating an integration

```
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.integration.IntegrationType;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.integration.IntegrationRequest;


@PluginModule
GIJFacade gijFacade;

int REPO_ID = 26;
IntegrationRequest newIntegration = new IntegrationRequest();
newIntegration.setDisplayName("new name gitlab");
gijFacade.updateIntegration(REOP_ID, newIntegration);
```
