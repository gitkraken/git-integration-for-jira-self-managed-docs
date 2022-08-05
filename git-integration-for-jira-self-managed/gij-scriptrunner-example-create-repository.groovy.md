---

title: ScriptRunner - Connecting to a single repository example
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

# Example of a script connecting to a plain repository

```groovy
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.Repository;

String PRIVATE_ORIGIN = "https://yourhost/yourorganization/yourPrivateRepo.git";
String USERNAME = "yourUsername";
String PAT = "yourPATpIf6MNLQd4JqS09CnksaAe2Pnqy0hwCZD"

@PluginModule
GIJFacade gijFacade;

Repository newRepoParams = new Repository();
newRepoParams.setOrigin(PRIVATE_ORIGIN);
newRepoParams.setGitViewerEnabled(true);
newRepoParams.setUsername(USERNAME);
newRepoParams.setPat(PAT);

gijFacade.createRepository(newRepoParams);
```
