---

title: Java 8 deprecation with Git Integration for Jira v5.0
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

The document explains the importance of updating the Java platform to a newer version. It emphasizes the reasons behind our decision to make this move, which includes prioritizing security, enhancing performance, and ensuring compatibility improvements. Updating Java is crucial for maintaining a secure and efficient software environment.

The Git Integration for Jira v5.0 app (GIJ) utilizes various third-party libraries to improve its functionality, perfornance and security. It is strongly advised that Jira administrators consider upgrading to Java 9 or a more recent version of Java on the machine running Jira.

Here is a comprehensive list of reasons why it would be beneficial for GIJ v5.0 to discontinue support for Java 8:

*   GIJ will be able to maintain compatibility with Jira if it uses the latest Amazon AWS SDK – which requires at least Java 9. We have made the decision to refrain from using the old AWS SDK due to concerns that it may be flagged by Atlassian for security vulnerabilities.

*   GIJ uses jgit and version 6.6.1+ fixes some vulnerabilities from the older jgit versions and this requires at least Java 11.

*   GIJ uses `java-modularity-excluded` profile in pom.xml and we will remove it when we stop support for Java 8.

*   GIJ uses the maven plugin – version 4.9.9 is the latest version for Java 8; version 7.0.0 requires at least Java 11 for Jira compatibility.

*   GIJ uses some other third party tools that requires at least Java 9 or later in order to use their latest iterations. These tools empower us to conduct compatibility and performance testing, among other functions.

### Which Jira self-hosted instances are affected?

<div class="bbb-callout bbb--info">
    <div class="irow">
    <div class="ilogobox">
        <span class="logoimg"></span>
    </div>
    <div class="imsgbox">
        <b>From Atlassian:</b><br>
        "We're planning to stop supporting Java 8 in upcoming releases. You can use it with Jira 9.7 until we announce the deprecation of Java 8."
    </div>
    </div>
</div>

If you are using Jira 9.8 or later, please note that GIJ v5.0 requires at least Java 9 or a newer version.

### What do I need to do if I'm running Jira Server or Data Center product on Java 8?

There are three ways:

*   <u>Upgrade to a product version that supports OpenJDK (Recommended):</u>
    Every Server and Data Center product now includes a feature version that is compatible with OpenJDK and will continue to do so. If you prefer not to acquire an Oracle subscription, you have the option to upgrade to one of the product versions that are designed to run on OpenJDK. It's important to note that certain product versions supporting OpenJDK do not come bundled with installers. In these instances, it is essential to manually install OpenJDK.

*   <u>Stay on an old version of Java:</u>
    We will continue to support any customer using Java 8. However, running on this version will leave you vulnerable to any Java security issues.

*   <u>Use Oracle Java SE instead:</u>
    If you want to continue to get updates and security patches beyond this point, you'll need to purchase an Oracle Java SE subscription.

How do I migrate from Java 8 to a newer version?

For related information and resources about Java 8 upgrade and migration, see the following links below:

*   [Cam I migrate our Jira server type 8.20.12 version to Open or Adoptium OpenJDK Java 11 JDK8 / 11?](https://community.atlassian.com/t5/Jira-questions/Can-I-migrate-our-JIRA-server-type-8-20-12-version-to-Open-or/qaq-p/2603916)

*   [How to change the Java version used by Jira | Atlassian Documentation](https://confluence.atlassian.com/jirakb/how-to-change-the-java-version-used-by-jira-765594330.html)

*   [Java 11 / OpenJDK support update for Server and Data Center products](https://community.atlassian.com/t5/Agile-articles/Java-11-OpenJDK-support-update-for-Server-and-Data-Center/ba-p/967836)

*   [Oracle JDK Migration Guide](https://docs.oracle.com/en/java/javase/21/migrate/migrating-jdk-8-later-jdk-releases.html#GUID-7BB28E4D-99B3-4078-BDC4-FC24180CE82B)

*   [How to quickly switch between Java 11, Java 8 and OpenJDK versions](https://developer.atlassian.com/server/framework/atlassian-sdk/how-to-quickly-switch-between-installed-java-versions-in-terminal/)

