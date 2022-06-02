---

title: Microsoft | VSTS | TFS | Azure Repos JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1352663519/azure2.png?version=1&modificationDate=1615471241670&cacheVersion=1&api=v2&width=340&height=57)

An optional JMESPath filter can be configured when adding Azure Repos integration or repositories.

|     |
| --- |
| **1\. Contains (include)** |
| ```java<br>value[?contains(name, 'example')]\| {value:@}<br>``` |
| This is a filter based on the text in the repository name. It will list repositories with names containing `'example'`. Do note that the declared string format is case-sensitive. |

|     |
| --- |
| **2\. Contains (exclude)** |
| ```java<br>value[?(!contains(name, 'Test'))]\| {value:@}<br>``` |
| The '**!**' expression removes all repositories with `'test'` in the repository name. |

|     |
| --- |
| **3\. Starts with or ends with** |
| ```java<br>value[?starts_with(name, 'git') \| ends_with(name, 'test')]\| {value:@}<br>``` |
| Lists repositories with names that starts with `'git'` or ends with `'test'`. |
| **Other examples**<br><br>```java<br>value[?contains(project.state, 'wellFormed')]\| {value:@}<br>value[?contains(project.name, 'test2')]\| {value:@}<br>value[?contains(project.visibility, 'private')]\| {value:@}<br>value[?contains(project.visibility, 'public')]\| {value:@}<br><br>```<br><br>1.  Displays repositories from projects where its state is _completely created and ready to use_.<br>    <br>2.  List all repositories from project named "_**test2**_".<br>    <br>3.  Displays all private repositories.<br>    <br>4.  Displays all public repositories. |

