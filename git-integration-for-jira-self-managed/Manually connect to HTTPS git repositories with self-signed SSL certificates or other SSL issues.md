---

title: Manually connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
When connecting to a private HTTPS git repository, a problem may be caused by a custom (self-signed) certificate. Make sure to install the latest JRE and then change the `JAVA_HOME` of Jira server.

If the above solution doesn't work, see below for the steps to workaround this issue:

1.  From your Jira Server, clone the repository manually using the git client.

    *   **Example:**

        ```java
        cd /jira/home
        cd data/git-plugin
        git clone --mirror https://my-self-signed-repo/project.git
        ```

2.  Make sure the Jira user has access to the folder above.

3.  Configure the repository to disable verification of the SSL certificate:

    *   Run `git config http.sslVerify false` in the repository folder.

        **Example:**

        ```java
        cd project.git
        git config http.sslVerify false
        ```

4.  Add repository via Connect wizard ➜ **Advanced Setup**.

5.  Set **Repository root** to the folder that was used in **step 1**.

6.  The clone will be kept up-to-date and the SSL verification issues will be ignored.


There are alternative solutions to make Java trust this certificate. Refer to the good articles from Atlassian which focuses on helping to resolve SSL Verification Issues:

1.  [**Unable to Connect to SSL Services due to PKIX Path Building Failed**](https://confluence.atlassian.com/kb/unable-to-connect-to-ssl-services-due-to-pkix-path-building-failed-779355358.html)

2.  [**Connecting to SSL services**](https://confluence.atlassian.com/jira/connecting-to-ssl-services-117455.html)


For related topics on connecting repositories from other git hosts, see [Integration Guides](/wiki/spaces/GIJDC/pages/92176395).

[« Automatically connect to HTTPS git repositories with self-signed SSL certificates or other SSL issues](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397370/%28GDC%29+Automatically+connect+to+HTTPS+git+repositories+with+self-signed+SSL+certificates+or+other+SSL+issues)

[Managing repository or integration configuration »](https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/1930397435/%28GDC%29+Managing+repository+or+integration+configuration)

