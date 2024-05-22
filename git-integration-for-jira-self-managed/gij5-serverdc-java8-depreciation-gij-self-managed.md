---

title: Java 8 deprecation with Git Integration for Jira v5.0
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The document explains the importance of updating the Java platform to a newer version. It emphasizes the reasons behind our decision to make this move, which includes prioritizing security, enhancing performance, and ensuring compatibility improvements. Updating Java is crucial for maintaining a secure and efficient software environment.

The Git Integration for Jira v5.0 app (GIJ) utilizes various third-party libraries to improve its functionality, perfornance and security. It is strongly advised that Jira administrators consider upgrading to Java 9 or a more recent version of Java on the machine running Jira.

Here is a comprehensive list of reasons why it would be beneficial for GIJ v5.0 to discontinue support for Java 8:

*   GIJ follows Atlassian's guidelines to maintain compatibility with its platform and we encourage Jira administrators to upgrade to the latest Java platform for better security and performance.

*   GIJ uses some other third party tools that requires at least Java 9 or later in order to use their latest iterations. These tools empower us to conduct compatibility and performance testing, among other functions.

&nbsp;

### Which Jira self-hosted instances are affected?

Atlassian supports Java 17 since Jira 9.5. If you are using previous versions of Jira, official support for Java 11 started from Jira 8.2. For more information, see [Administering Jira applications support - Upgrade matrix](https://confluence.atlassian.com/adminjiraserver/upgrade-matrix-966063322.html).

| Jira version | Supports Java version |
|:-------------|:----------------------|
| 9.5 and newer | Java 17 and newer    |
| 8.2 up to 9.4 | Java 11 and later    |
| 8.1 and older | Java 8 (deprecated)  |

&nbsp;

### What do I need to do if I'm running Jira Server or Data Center product on Java 8?

There are three ways:

*   <u>Upgrade to a product version that supports OpenJDK (Recommended):</u>
    Every Server and Data Center product now includes a feature version that is compatible with OpenJDK and will continue to do so. If you prefer not to acquire an Oracle subscription, you have the option to upgrade to one of the product versions that are designed to run on OpenJDK. It's important to note that certain product versions supporting OpenJDK do not come bundled with installers. In these instances, it is essential to manually install OpenJDK.

*   <u>Stay on an old version of Java:</u>
    We will continue to support any customer using Java 8. However, running on this version will leave you vulnerable to any Java security issues.

*   <u>Use Oracle Java SE instead:</u>
    If you want to continue to get updates and security patches beyond this point, you'll need to purchase an Oracle Java SE subscription.

&nbsp;

### How do I migrate from Java 8 to a newer version?

For related information and resources about Java 8 upgrade and migration, see the following links below:

*   [Cam I migrate our Jira server type 8.20.12 version to Open or Adoptium OpenJDK Java 11 JDK8 / 11?](https://community.atlassian.com/t5/Jira-questions/Can-I-migrate-our-JIRA-server-type-8-20-12-version-to-Open-or/qaq-p/2603916)

*   [How to change the Java version used by Jira | Atlassian Documentation](https://confluence.atlassian.com/jirakb/how-to-change-the-java-version-used-by-jira-765594330.html)

*   [Java 11 / OpenJDK support update for Server and Data Center products](https://community.atlassian.com/t5/Agile-articles/Java-11-OpenJDK-support-update-for-Server-and-Data-Center/ba-p/967836)

*   [Oracle JDK Migration Guide](https://docs.oracle.com/en/java/javase/21/migrate/migrating-jdk-8-later-jdk-releases.html#GUID-7BB28E4D-99B3-4078-BDC4-FC24180CE82B)

*   [How to quickly switch between Java 11, Java 8 and OpenJDK versions](https://developer.atlassian.com/server/framework/atlassian-sdk/how-to-quickly-switch-between-installed-java-versions-in-terminal/)

