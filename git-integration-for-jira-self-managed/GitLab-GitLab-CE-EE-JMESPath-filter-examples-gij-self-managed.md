---

title: GitLab.com | GitLab CE/EE JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

![](/wp-content/uploads/gitlab-mobile-custom1.png)

<br>

An optional JMESPath filter can be configured when adding GitLab integration or repositories.

<br>

## 1\. Contains (include)

`[?contains(name, 'git') || contains(name, 'Slap') || contains(name, 'est')]`

This is a filter based on the text in the repository name. It will list repositories that contains the specified names. Do note that the declared string format is case-sensitive.

## 2\. Contains (exclude)

```
[?(!contains(tag_list, 'largemedia'))]

[?(!contains(name, 'firstword'))]

[?(!contains(name, 'firstword')) && (!contains(name, 'secondword'))]
```

**1** – Blacklists project tag.

**2** – Lists repositories with names that either do not contain the word `'firstword'`.

**3** – Lists repositories with names that either do not contain the words `'firstword'` OR `'secondword'`.

## 3\. Tags

`[?contains(tag_list, 'largemedia')]`

Whitelists project tag.

<div class="bbb-callout bbb--note">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Note</b><br>
        GitLab refers to <b><i>project tags</i></b> as tags in the API and in some places in the UI but the actual setting is called <b>Topics</b>.
    </div>
    </div>
</div>
<br>


## 4\. Starts with or ends with

`[?starts_with(name, 'git') || ends_with(name, 'test')]`

Lists repositories with names that starts with `'git'` or ends with `'test'`.

## 5\. Exclude projects without repositories

`[?!empty_repo]`

Lists only repositories from projects that have existing repositories.

<hr>

## More articles on JMESPath filter examples

[GitHub.com \| GitHub Enterprise JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-GitHub-Enterprise-JMESPath-filter-examples-gij-self-managed)

**GitLab.com \| GitLab CE/EE JMESPath filter examples** (this page)

[Microsoft \| VSTS \| TFS \| Azure Repos JMESPath filter examples](/git-integration-for-jira-data-center/Microsoft-VSTS-TFS-Azure-Repos-JMESPath-filter-examples-gij-self-managed)

[Tracked Folders JMESPath filter examples](/git-integration-for-jira-data-center/Tracked-Folders-JMESPath-filter-examples-gij-self-managed)

[Gerrit JMESPath filter examples](/git-integration-for-jira-data-center/Gerrit-JMESPath-filter-examples-gij-self-managed)

[GitHub App JMESPath filter examples](/git-integration-for-jira-data-center/GitHub-App-JMESPath-filter-examples-gij-self-managed)

<br>
<hr>

<!-- FOOTNOTE -->
<br>
<br>
<div style='border-top: 1px solid #456; width: 40%; padding-bottom: 12px'></div>
<div style='font-size: 12px;'>
    <sup>1</sup> <i>Logo owned by <a href='https://gitlab.com/' target='_blank'>GitLab Inc</a> used under <a href='https://creativecommons.org/licenses/by-nc-sa/4.0/' target='_blank'>license</a>.
    <p>&nbsp;&nbsp;All product names, logos, and brands are property of their respective owners.<p><i>
</div>

