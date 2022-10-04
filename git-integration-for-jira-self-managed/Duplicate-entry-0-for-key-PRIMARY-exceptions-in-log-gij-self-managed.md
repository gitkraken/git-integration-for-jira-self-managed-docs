---

title: Duplicate entry 0 for key PRIMARY exceptions in log
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

## Problem

After Jira installation or configuration changes - the following errors appear. Errors/failures in the Git Integration for Jira application are seen sporadically.

## Diagnosis

Jira admins will see a message similar to the one below in the Jira log: /application-logs/atlassian-jira.log:

```java
2014-06-23 10:14:00,319 http-bio-8080-exec-25 ERROR xxx 614x203x2 p1s16e xxx.xxx.xxx.xxx /rest/activityplugin/1.0/usersettings [common.error.jersey.ThrowableExceptionMapper] Uncaught exception thrown by REST service
com.atlassian.activeobjects.internal.ActiveObjectsSqlException: There was a SQL exception thrown by the Active Objects library:
Database:
	- name:MySQL
	- version:5.1.54-rel12.5-log
	- minor version:1
	- major version:5
Driver:
	- name:MySQL-AB JDBC Driver
	- version:mysql-connector-java-5.1.10 ( Revision: ${svn.Revision} )
com.mysql.jdbc.exceptions.jdbc4.MySQLIntegrityConstraintViolationException: Duplicate entry '0' for key 'PRIMARY'
	at com.atlassian.activeobjects.internal.EntityManagedActiveObjects.create(EntityManagedActiveObjects.java:107)
	at com.atlassian.activeobjects.osgi.DelegatingActiveObjects.create(DelegatingActiveObjects.java:63)  <+3>
	at java.lang.reflect.Method.invoke(Unknown Source)
	(...)
	at java.lang.Thread.run(Unknown Source)
Caused by: com.mysql.jdbc.exceptions.jdbc4.MySQLIntegrityConstraintViolationException: Duplicate entry '0' for key 'PRIMARY'
	at sun.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
	(...)
	at com.atlassian.activeobjects.internal.EntityManagedActiveObjects.create(EntityManagedActiveObjects.java:103)
	... 194 more
```

## Cause

In MySQL configuration (my.ini (Windows) or my.cnf (Unix)), parameter of sql_mode is set to  NO_AUTO_VALUE_ON_ZERO.

## Solution

1.  Uninstall the Git Integration for Jira app.
2.  Remove all Git Integration for Jira app tables.
3.  Stop Jira.
4.  Stop MySQL.
5.  Edit the **my.cnf** file (often named **my.ini** on Windows operating systems or **my.cnf** on UNIX operating systems) in your MySQL server.
6.  Remove `NO_AUTO_VALUE_ON_ZERO` from sql_mode.
7.  Start MySQL.
8.  Start Jira.
9.  Install the Git Integration for Jira app.

For more information - see Atlassian help article about [Duplicate entry 0 for key PRIMARY exceptions in log](https://confluence.atlassian.com/jirakb/duplicate-entry-0-for-key-primary-exceptions-in-log-646251198.html).

<br>

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>Contact Us</b><br>
        If you still have a question - reach out to our <a href='https://help.gitkraken.com/git-integration-for-jira-data-center/gij-self-hosted-contact-support/'>Support Desk</a> or email us at <a href='gijsupport@bigbrassband.com'>gijsupport@bigbrassband.com</a>.
    </div>
    </div>
</div>
<br>

