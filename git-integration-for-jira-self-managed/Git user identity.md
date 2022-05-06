---

title: Git user identity
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# Git user identity

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930398801/Git+user+identity>

* * *

A git user can identify himself on his local computer using the following commands:

```powershell
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

  
Or, for specific repository:

```powershell
$ git config user.name "John Doe"
$ git config user.email johndoe@example.com
```

  
Then every commit is supported by the configured user information.

Hosting services _(like GitHub and BitBucket, for example)_ try to match these data in commits with a particular account:

*   **If the email is unknown, it just displays the name from the commit.**  
    If there is no Jira user associated with the email, the Git Integration for Jira app will use the author's name from the commit and displays this name without any associated links.
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398801/git-user-non-matching-email.png?version=1&modificationDate=1630642907189&cacheVersion=1&api=v2&width=544&height=87)
*   **If an email is configured in the local repository, the account is detected and will be displayed.**  
    The Git Integration for Jira app will use the email from a commit and will search for a Jira user using this email. If the Jira user is found, the associated link to his Jira profile is displayed with the accompanying Jira avatar beside the name.  
    
    ![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1930398801/image-20210728-082525.png?version=1&modificationDate=1630642906952&cacheVersion=1&api=v2&width=421&height=69)

[« Viewing commit code diffs](/wiki/spaces/GIJDC/pages/1930398768/Viewing+commit+code+diffs)

[Jira user information card »](/wiki/spaces/GIJDC/pages/1930398841/Jira+user+information+card)