---

title: Jira issue page - Code syntax highlighter
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The code diff dialog view has been improved. The Git Integration for Jira app uses the correct syntax highlighting when viewing the code diff of the file based on its file extension:

| File Extension | Language ID |
| :--- | :--- |
| **css** | CSS |
| **js** | Javascript |
| **cpp** | C++ |
| **cs** | C#  |
| **sh** | Bash |
| **java** | Java |
| **sql** | SQL |
| **py** | Phyton |
| **rb** | Ruby |
| **php, phtml, php3, php4, php5** | PHP |
| **html, html, xhtml, xml** | Markup |
| **c, h, m, mm, pl, pm** | CLike |

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        There is no language auto-detection in the diff dialog. The detection is based on file extension.
    </div>
    </div>
</div>
<br>

<div class="bbb-callout bbb--alert">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        This feature will only display properly on browsers supported by Atlassian for specific versions of Jira:
        <ul style='margin-bottom:0px'>
            <li><a href="https://confluence.atlassian.com/adminjiraserver0900/supported-platforms-1142254604.html" target="_blank">Jira 9.x supported platforms</a></li>
            <li><a href="https://confluence.atlassian.com/adminjiraserver080/supported-platforms-967896891.html" target="_blank">Jira 8.x supported platforms</a></li>
        </ul>
    </div>
    </div>
</div>

&nbsp;
* * *

[**Prev:** Git Commits tab](/git-integration-for-jira-data-center/git-commits-tab-gij-self-managed)

[**Next:** Jira Git integration development panel](/git-integration-for-jira-data-center/jira-git-integration-development-panel-gij-self-managed)


