# Example of a script getting tags

```
import com.atlassian.jira.util.Function
import com.onresolve.scriptrunner.runner.customisers.WithPlugin
import com.onresolve.scriptrunner.runner.customisers.PluginModule
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.services.GIJFacade;
@WithPlugin("com.xiplink.jira.git.jira_git_plugin")
import com.bigbrassband.jira.git.rest.publicmodels.Tag;
import java.util.function.Function;
import java.util.stream.Collectors;

@PluginModule
GIJFacade gijFacade;

gijFacade.getTagsForIssue("TST-2")
    .stream()
    .map(new Function<Tag, String> () {
        public String apply(Tag tag) {
            return tag.name;
        }
    }).collect(Collectors.toList());

```
