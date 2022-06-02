---

title: After upgrading Jira from 4.1.1 to 5.2.9, I get some errors "Folder ... FORNEOnlineSolver git doesn't exist". Where can I set the path correctly? Is there any properties file?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


Please visit Git Integration for Jira app config and check Git Repositories tab (_Jira dashboard menu **Git** ➜ **Manage repositories** ➜_ ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) _**Actions**_):

*   For integrations, go to ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Show integration repositories** ➜ click a repository to view the repository settings.
    
*   For repository connections, go to ![(blue star)](https://bigbrassband.atlassian.net/wiki/s/-1639011364/6452/8b4898d3c114827e64ec143b4fa79bb76a6cfa5b/_/images/icons/emoticons/star_blue.png) Actions ➜ **Edit repository settings**.
    

Check and verify the path to your configured repositories.

Also, an upgrade of Jira may lead to changing of user account used to run the service, which in turn, may result in lack of permissions.

