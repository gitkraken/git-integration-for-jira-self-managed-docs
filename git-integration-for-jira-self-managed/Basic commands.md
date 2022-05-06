---

title: Basic commands
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Basic commands

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398422/Basic+commands>

* * *

There are smart commits commands that you can use in your commit messages. Read on to learn more details on each smart commit command and how they work.

# #comment

This command works both in Jira Server/Cloud.

The `#comment` command will add a comment to a Jira issue.

**Syntax: ISSUE\_KEY** **#comment** `[your comment text]`

|     |
| --- |
| **Examples:** |
| **GIT-264** **#comment** `Resolved conflicts.` |
| **GIT-1720** **#comment** `Plugin version change from 2.8.2 to 2.8.3. Build number change from 69 to 70.` |
| The above examples will add the specified comment text against the Jira issues. |
| The committers’ email address in the git configuration must match with the email address of the corresponding Jira user (or vice versa) to comment on issues. |

# #time

This command works both in Jira Server/Cloud.

The `#time` command will record time tracking information against a Jira issue.

**Syntax:** **ISSUE\_KEY** **#time** \[Some amount in Jira time syntax\] `[Your worklog comment text]`

|     |
| --- |
| **Examples:** |
| **GIT-264** **#time** 1w 6d 13h 52m `Total work logged.` |
| **GIT-1720** **#time** 1h 20m `Merged to master. Released to marketplace.` |
| The above examples will add the respective time and worklog comment text against the Jira issues. |
| The Jira time tracking feature allows users to log the length of time spent working on issues. Jira administrators must have enabled this feature for this smart commit to work. |

# #<transition-name>

This command works both in Jira Server/Cloud.

The `#<transition-name>` command will move the Jira issue to a particular workflow state.

The Jira user must have the appropriate project permissions to be able to transition issues.

**Syntax:** **ISSUE\_KEY** **#<transition-name>** `[Your commit comment text]`

|     |
| --- |
| **Examples:** |
| **GIT-264** **#code-review** `For review.` |
| **GIT-1720** **#close** `Closing ticket.` **#comment** `Tasks completed.` |
| The first example will transition the Jira issue to the specified workflow state and adds the comment message to the commit.<br><br>The second example will transition the Jira issue to the specified workflow state, adds the comment “_**Closing ticket**”**.**_ to the Comment tab and adds the specified comment, “_**Task completed.**_” to the mentioned Jira issue.<br><br>**With Example #2**  <br>For Jira Server/DC, only the mentioned `#comment` text is added to the **Commits** tab. |

For more information on transitions and workflow names and how they work, see [**Workflow Transitions**](https://bigbrassband.com/git-integration-for-jira/documentation/smart-commits.html#sc_wkflow).

# #assign

INTRODUCED VERSION 2.9.7+

This command works both in Jira Server/Cloud.

The `#assign` command will assign the particular issue to the specified Jira user. This command works in Jira Server/Cloud.

**Syntax:** **ISSUE\_KEY** **#assign** `[Jira username or email of Jira user]`

|     |
| --- |
| **Examples:** |
| **GIT-1925** **#assign** `johnsmith` |
| **GIT-1961** **#assign** `johnsmith@example.com` |

# #fixversion

INTRODUCED VERSION 2.9.7+

This command only works in Jira Server. It does not work in Jira Cloud.

The `#fixversion` command will add a Fix Version/s details tag to the specified issue.

**Syntax: ISSUE\_KEY #fixversion** `[project version]`

|     |
| --- |
| **Example:** |
| **GIT-1628** **#fixversion** `2.9.6` |
| **GIT-1628** **#fixversion** `2.9.5` **#fixversion** `2.9.6` |
| The first example adds fix version tag **2.9.6** to the issue, `GIT-1628`.<br><br>The second example adds fix version tags **2.9.5** and **2.9.6** to the issue, `GIT-1628`.<br><br>If there was an initial Fix Version tag on the specified issue, a `#fixversion` command will append the new Fix Version tag to it. |
| **For instance:**<br><br>The Fix Version tag, `2.9.4`, already exists in issue **GIT-1254**.<br><br>Performing the smart commit, **GIT-1254** **#fixversion** `2.9.5`, will give a result of:<br><br>```java<br>Fix Version/s: 2.9.4, 2.9.5<br>``` |

# #affectsversion

INTRODUCED VERSION 2.9.7+

This command only works in Jira Server. It does not work in Jira Cloud.

The `#affectsversion` command will add an Affect Version/s details tag to the specified issue.

**Syntax: ISSUE\_KEY #affectsversion** `[project version]`

|     |
| --- |
| **Example:** |
| **GIT-1582** **#affectsversion** `2.9.6` |
| The `#affectsversion` command works the same way as `#fixversion`. However, it appends Affect Version/s tag instead to the specified issue. |

# #label

This command works both in Jira Server/Cloud.

VERSION 2.12.6+ Available in Jira Cloud  
VERSION 3.5+ Available in Jira Server

The `#label` command will add a new label to a Jira issue. If more than one Jira issue is referenced, the labels are added to all mentioned Jira issues. Multiple labels can be created by putting spaces between words.

**Syntax: ISSUE\_KEY(S) #label** `[label1] .. [labeln]`

|     |
| --- |
| **Examples:** |
| **GITCL-443** **#label** `bucketbreakfix` `bucketenhancement` |
| **GITCL-443 GITCL-247 GITCL-214** **#label** [_admin@example.com_](mailto:admin@example.com) [_user1@example.com_](mailto:user1@example.com) requested-feature new-feature **#comment** `Return email when implemented` |

[« Smart commits (index)](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits)

[Advanced examples »](/wiki/spaces/GIJDC/pages/1930398446/Advanced+examples)

### More related topics about smart commits

*   Page:
    
    [Smart commits](/wiki/spaces/GIJDC/pages/1930398395/Smart+commits) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Basic commands](/wiki/spaces/GIJDC/pages/1930398422/Basic+commands) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Workflow transitions](/wiki/spaces/GIJDC/pages/1930398464/Workflow+transitions) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Advanced examples](/wiki/spaces/GIJDC/pages/1930398446/Advanced+examples) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Viewing workflows](/wiki/spaces/GIJDC/pages/1930398494/Viewing+workflows) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Smart commits helper](/wiki/spaces/GIJDC/pages/1930398529/Smart+commits+helper) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Smart commits General setting](/wiki/spaces/GIJDC/pages/1930398554/Smart+commits+General+setting) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Scripting (Jira git workflow hooks)](/wiki/spaces/GIJDC/pages/1930398579) (Git Integration for Jira Data Center)