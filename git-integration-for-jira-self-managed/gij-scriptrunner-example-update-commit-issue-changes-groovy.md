# Example of a script updating commit issues associations

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.IssuesAssociationRequest;

@PluginModule
GIJFacade gijFacade;

int REPO_ID = 1;
gijFacade.updateCommitIssueChanges(REPO_ID, "ec43e12cda0fa4f021d4dead8eadb8781efbb4b0", new IssuesAssociationRequest().addLink("TST-6"));
```
