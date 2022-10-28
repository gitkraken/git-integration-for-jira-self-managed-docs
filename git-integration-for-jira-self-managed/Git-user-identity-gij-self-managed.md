---

title: Git user identity
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

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

<br>

Then every commit is supported by the configured user information.

Hosting services _(like GitHub and BitBucket, for example)_ try to match these data in commits with a particular account:

*   **If the email is unknown, it just displays the name from the commit.**
    If there is no Jira user associated with the email, the Git Integration for Jira app will use the author's name from the commit and displays this name without any associated links.

    ![](/wp-content/uploads/gij-git-user-non-matching-email.png)

*   **If an email is configured in the local repository, the account is detected and will be displayed.**
    The Git Integration for Jira app will use the email from a commit and will search for a Jira user using this email. If the Jira user is found, the associated link to his Jira profile is displayed with the accompanying Jira avatar beside the name.

    ![](/wp-content/uploads/gij-git-user-matching-email.png)

<p></p>

<br>
<br>

[**Prev:** Viewing commit code diffs](/git-integration-for-jira-data-center/viewing-commit-code-diffs-gij-self-managed)

[**Next:** Jira user information card](/git-integration-for-jira-data-center/jira-user-information-card-gij-self-managed)


