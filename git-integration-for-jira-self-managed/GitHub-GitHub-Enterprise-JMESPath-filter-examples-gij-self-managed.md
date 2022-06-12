---

title: GitHub.com | GitHub Enterprise JMESPath filter examples
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
![](https://bigbrassband.atlassian.net/wiki/download/thumbnails/1353482464/github-mobile-customv4.png?version=1&modificationDate=1615470904035&cacheVersion=1&api=v2&width=226&height=53)

An optional JMESPath filter can be configured when adding GitHub integration or repositories.

1. **Contains (include)**

    ```java
    [?contains(name, 'git')]
    ```

    This is a filter based on the text in the repository name. It will list repositories with names that contain the word `'git'`. Do note that the declared string format is case-sensitive.

2. **Starts with or ends with**

    ```java
    [?starts_with(name, 'git') \| ends_with(name, 'test')]
    ```

    Lists repositories with names that starts with `'git'` or ends with `'test'`.

3. **Contains (exclude)**

    ```java
    [?(!contains(name, 'firstword'))]

    [?(!contains(name, 'firstword')) \| (!contains(name, 'secondword'))]
    ```

    1 – Lists repositories with names that either do not contain the word `'firstword'`.

    2 – Lists repositories with names that either do not contain the words `‘firstword’` OR `‘secondword’`.

    <div class="bbb-callout bbb--note">
      <div class="irow">
        <div class="ilogobox">
          <span class="logoimg"></span>
        </div>
        <div class="imsgbox">
          The <code>!condition</code> must be wrapped in a parenthesis so it won’t invert the whole expression.
        </div>
      </div>
    </div>

