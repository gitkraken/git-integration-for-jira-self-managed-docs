---

title: Smart commits -- Basic commands
description:
taxonomy:
    category: git-integration-for-jira-data-center

---
There are smart commits commands that you can use in your commit messages. Read on to learn more details on each smart commit command and how they work.

## \#comment

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command works both in Jira Server/Cloud.
    </div>
    </div>
</div>

The `#comment` command will add a comment to a Jira issue.

**Syntax: ISSUE\_KEY** **#comment** `[your comment text]`

| **Examples:** |
| :--- |
| **GIT-264** **#comment** `Resolved conflicts.`<br>**GIT-1720** **#comment** `Plugin version change from 2.8.2 to 2.8.3. Build number change from 69 to 70.`<br> |

The above examples will add the specified comment text against the Jira issues.

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The committers’ email address in the git configuration must match with the email address of the corresponding Jira user (or vice versa) to comment on issues.
    </div>
    </div>
</div>

## \#time

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command works both in Jira Server/Cloud.
    </div>
    </div>
</div>

The `#time` command will record time tracking information against a Jira issue.

**Syntax:** **ISSUE\_KEY** **#time** \[Some amount in Jira time syntax\] `[Your worklog comment text]`

| **Examples:** |
| :--- |
| **GIT-264** **#time** 1w 6d 13h 52m `Total work logged.`<br>**GIT-1720** **#time** 1h 20m `Merged to master. Released to marketplace.` |

The above examples will add the respective time and worklog comment text against the Jira issues.

<div class="bbb-callout bbb--tip">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Jira time tracking feature allows users to log the length of time spent working on issues. Jira administrators must have enabled this feature for this smart commit to work.
    </div>
    </div>
</div>

## \#\<transition-name\>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command works both in Jira Server/Cloud.
    </div>
    </div>
</div>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        The Jira user must have the appropriate project permissions to be able to transition issues.
    </div>
    </div>
</div>

The `#<transition-name>` command will move the Jira issue to a particular workflow state.

**Syntax:** **ISSUE\_KEY** **#\<transition-name\>** `[Your commit comment text]`

| **Examples:**    |
| :--- |
| **GIT-264** **#code-review** `For review.`<br>**GIT-1720** **#close** `Closing ticket.` **#comment** `Tasks completed.` |

* The first example will transition the Jira issue to the specified workflow state and adds the comment message to the commit.
* The second example will transition the Jira issue to the specified workflow state, adds the comment "_**Closing ticket**_" to the Comment tab and adds the specified comment, "_**Task completed**_", to the mentioned Jira issue.

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>With Example #2</b><br>For Jira Server/DC, only the mentioned <code>#comment</code> text is added to the <b>Commits</b> tab.
    </div>
    </div>
</div>

For more information on transitions and workflow names and how they work, see [Workflow Transitions](#).

## \#assign

**INTRODUCED v2.9.7+**

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command works both in Jira Server/Cloud.
    </div>
    </div>
</div>

The `#assign` command will assign the particular issue to the specified Jira user.

**Syntax:** **ISSUE\_KEY** **#assign** `[Jira username or email of Jira user]`

| **Examples:** |
| :--- |
| **GIT-1925** **#assign** `johnsmith`<br>**GIT-1961** **#assign** `johnsmith@example.com` |

## \#fixversion

INTRODUCED v2.9.7+

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command only works in Jira Server. It does not work in Jira Cloud.
    </div>
    </div>
</div>

The `#fixversion` command will add a Fix Version/s details tag to the specified issue.

**Syntax: ISSUE\_KEY \#fixversion** `[project version]`

| **Example:** |
| :--- |
| **GIT-1628** **#fixversion** `2.9.6`<br>**GIT-1628** **#fixversion** `2.9.5` **#fixversion** `2.9.6` |

* The first example adds fix version tag **2.9.6** to the issue, `GIT-1628`.
* The second example adds fix version tags **2.9.5** and **2.9.6** to the issue, `GIT-1628`.<br>If there was an initial Fix Version tag on the specified issue, a `#fixversion` command will append the new Fix Version tag to it.  <br><br>**For instance:**<br>The Fix Version tag, `2.9.4`, already exists in issue **GIT-1254**.<br>Performing the smart commit, **GIT-1254** **#fixversion** `2.9.5`, will give a result of:<br>
  * ```Fix Version/s: 2.9.4, 2.9.5```

## \#affectsversion

INTRODUCED v2.9.7+

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command only works in Jira Server. It does not work in Jira Cloud
    </div>
    </div>
</div>

The `#affectsversion` command will add an Affect Version/s details tag to the specified issue.

**Syntax: ISSUE\_KEY \#affectsversion** `[project version]`

| **Example:** |
| :--- |
| **GIT-1582** **#affectsversion** `2.9.6` |

The `#affectsversion` command works the same way as `#fixversion`. However, it appends Affect Version/s tag instead to the specified issue.

# \#label

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This command works both in Jira Server/Cloud.
    </div>
    </div>
</div>

Already available in Jira Cloud
**v3.5+** Available in Jira Server

The `#label` command will add a new label to a Jira issue. If more than one Jira issue is referenced, the labels are added to all mentioned Jira issues. Multiple labels can be created by putting spaces between words.

**Syntax: ISSUE\_KEY(S) \#label** `[label1] .. [labeln]`

| **Examples:** |
| :--- |
| **GITCL-443** **#label** `bucketbreakfix` `bucketenhancement`<br>**GITCL-443 GITCL-247 GITCL-214** **#label** `admin@example.com` `user1@example.com` requested-feature new-feature **#comment** `Return email when implemented` |

