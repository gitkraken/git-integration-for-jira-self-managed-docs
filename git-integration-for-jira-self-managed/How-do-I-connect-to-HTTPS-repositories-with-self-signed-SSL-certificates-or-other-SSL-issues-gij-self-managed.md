---

title: How do I connect to HTTPS repositories with self signed SSL certificates or other SSL issues?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
This problem may be caused by a custom (a self-signed) certificate. Make sure to install the latest JRE and then change the `JAVA_HOME` of Jira server.

The above solution should work, otherwise, see below for the steps to workaround this issue:

1.  From your Jira Data Center, clone the repository manually using the git client.

    **Example:**

    ```java
    cd /jira/home
    cd data/git-plugin
    git clone --mirror https://my-self-signed-repo/project.git
    ```

2.  Make sure that the Jira user has access to the folder above.

3.  Configure the repository to disable verification of the SSL certificate.

    **Example:**

    ```java
    cd project.git
    git config http.sslVerify false
    ```

4.  Run  `git config http.sslVerify false` in the repository folder.

5.  From your browser, log into Jira and go to Jira dashboard menu Git ➜ **Manage repositories**. The manage git repositories configuration page is displayed.

6.  Click **Connect to Git Repository** then [_Advanced setup_](/git-integration-for-jira-self-managed/connecting-a-repository-via-advanced-setup-gij-self-managed).

7.  For the _Display Name_, enter a description of the Git repository.

8.  For the _Repository Root_, enter the full path to the Git repository that you have cloned. Considering the example in **step 1**, it will be similar to `/jira/home/data/git-plugin/project.git`.

9.   Click the **Detect** button next to the _Repository Origin_.

10.  Click **Add** to add this repository to the Git repository configuration list.


The clone will be kept up-to-date and the SSL verification issues will be ignored.

There are alternative solutions to make Java trust this certificate.  Please refer to the following articles from Atlassian which focuses on helping to resolve SSL Verification Issues:

*   [**Unable to Connect to SSL Services due to PKIX Path Building Failed**](https://confluence.atlassian.com/kb/unable-to-connect-to-ssl-services-due-to-pkix-path-building-failed-779355358.html)

*   [**Connecting to SSL services**](https://confluence.atlassian.com/jira/connecting-to-ssl-services-117455.html)


If the problem persist, please [send us a support zip](/git-integration-for-jira-self-managed/how-to-create-the-support-zip-file-gij-self-managed) to give us a better view of the issue.

