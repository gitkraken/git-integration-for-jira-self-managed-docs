---

title: Code syntax highlighter
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Code syntax highlighter

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398989/Code+syntax+highlighter>

* * *

As of **v2.5.5** of the Git Integration for Jira app, the code diff dialog view is improved. The Git Integration for Jira app uses the correct syntax highlighting when viewing the code diff of the file based on its file extension:

|     |     |
| --- | --- |
| **File Extension** | **Language ID** |
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

There is no language auto-detection in the diff dialog. The detection is based on file extension.

This feature will only display properly on browsers supported by Atlassian for specific versions of Jira:

*   [**Jira 6.3 supported platforms**](https://confluence.atlassian.com/jira063/supported-platforms-683541780.html)
    
*   [**Jira 7.x supported platforms**](https://confluence.atlassian.com/adminjiraserver0713/supported-platforms-964983071.html)
    
*   [**Jira 8.x supported platforms**](https://confluence.atlassian.com/adminjiraserver/supported-platforms-938846830.html)
    

[« Git Commits tab](/wiki/spaces/GIJDC/pages/1930398950/Git+Commits+tab)

[Jira Git integration development panel »](/wiki/spaces/GIJDC/pages/1930399012/Jira+Git+integration+development+panel)

### More related topics about Jira issue page

*   Page:
    
    [Jira issue page](/wiki/spaces/GIJDC/pages/1930398870/Jira+issue+page) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git Roll Up tab](/wiki/spaces/GIJDC/pages/1930398901/Git+Roll+Up+tab) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Git Commits tab](/wiki/spaces/GIJDC/pages/1930398950/Git+Commits+tab) (Git Integration for Jira Data Center)
    
*   Page:
    
    [Code syntax highlighter](/wiki/spaces/GIJDC/pages/1930398989/Code+syntax+highlighter) (Git Integration for Jira Data Center)