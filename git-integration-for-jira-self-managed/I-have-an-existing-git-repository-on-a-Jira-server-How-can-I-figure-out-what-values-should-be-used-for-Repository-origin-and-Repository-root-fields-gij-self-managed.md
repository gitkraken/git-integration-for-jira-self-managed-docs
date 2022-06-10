---

title: I have an existing git repository on a Jira server. How can I figure out what values should be used for Repository origin and Repository root fields?
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---


1.  Change current directory to the folder where repository is located.
    
2.  Run `pwd`.
    
3.  Response should go to **Repository root** field.
    
4.  Run `git remote show origin`.
    
5.  Find origin URL in the command response.
    
6.  Set this value for **Repository origin** field.
    