---

title: How do I setup GitLab Server to respond to incoming network API calls?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---
In order for GitLab to display correct repository clone links to your users it needs to know the URL under which it is reached by your users (e.g. `http://gitlab.example.com/`)

To reconfigure:

1.  Access the GitLab configuration file in `/etc/gitlab/gitlab.rb`. 

    ```java
    sudo vi /etc/gitlab/gitlab.rb
    ```

2.  Change the `external_url` value to your GitLab server URL. 

    ```java
    external_url "http://gitlab.example.com" #this is the default URL
    external_url "http://X.X.X.X.local/" #change it to your GitLab Server URL
    ```

3.  Run the **reconfigure** command to make the change take effect. 

    ```java
    sudo gitlab-ctl reconfigure
    ```



Read this [**GitLab documentation**](https://docs.gitlab.com/omnibus/settings/configuration.html#configuring-the-external-url-for-gitlab) to know more about configuring the external URL for GitLab.

You should be able to add the GitLab repositories via Git Integration for Jira app ➜ **Connect to Git Repository** / **Add New integration**.
