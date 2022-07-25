# Example of a script connecting to an integration

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

IntegrationRequest newIntegration = new IntegrationRequest(IntegrationType.GITLAB, null, null/*don't pass pat here*/, "My GitLab Integration");
newIntegration.setPat("yourPat");
newIntegration.setApiFilter("[?contains(name, 'test')]");
gijFacade.createIntegration(newIntegration);
```
