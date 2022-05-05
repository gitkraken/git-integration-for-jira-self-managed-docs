---

title: "Dangerous use of multiple connections" error on local database
description:
taxonomy:
    category: git-integration-for-jira-self-managed

---

# "Dangerous use of multiple connections" error on local database

<https://bigbrassband.atlassian.net/wiki/spaces/GIJDC/pages/821919745>

* * *

## Problem

As Git Integration for Jira Server app uses the Jira database increasingly, it is to be expected that this error will be seen or encountered more often:

```java
2020-09-24 08:38:47,769+0200 Caesium-1-3 WARN   [c.a.jira.ofbiz.ConnectionPoolHealthSqlInterceptor] Dangerous use of multiple connections: taken => count=2; marks=[1-0]; pool=18/20
java.lang.AssertionError: Explicit stack trace requested
```

## Diagnosis

All database connections are handled internally by the Jira Active Objects (AO) library. While the Git Integration app accesses the database progressively more, the AO library will use more database connections proportional to the volume of database requests.

## Solution

The default value of **20** for database connections is sufficient for small Jira instances. For larger Jira instances, this value should be tuned based on Jira load, number of users, hardware performance and other factors.

More details may be found in the following articles:

*   [**Tuning Database Connections**](https://confluence.atlassian.com/adminjiraserver/tuning-database-connections-938846864.html)
    
*   [**Monitoring Database Connection Usage**](https://confluence.atlassian.com/adminjiraserver/monitoring-database-connection-usage-938847726.html)