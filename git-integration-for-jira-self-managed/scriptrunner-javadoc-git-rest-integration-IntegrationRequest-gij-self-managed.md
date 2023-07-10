---

title: ScriptRunner - Javadocs - Class IntegrationRequest
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

* Package [com.bigbrassband.jira.git.rest.integration](#)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  \> [IntegrationRequest](#) (This page)

This is a POJO object containing an integration properties/settings.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [IntegrationRequest](#integrationrequest)() |
| `public` | [IntegrationRequest](#integrationrequestintegrationtype-string-string-string)(*[IntegrationType](/git-integration-for-jira-data-center/scriptrunner-javadoc-git-services-integration-IntegrationType-gij-self-managed/)* type,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  origin,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  pat,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  displayName) |

#### Methods
| Type and modifiers | Method signature |
| --- | --- |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getApiFilter](#getapifilter)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getApiPath](#getapipath)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getAwsRegion](#getawsregion)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getDisableSslVerification](#getdisablesslverification)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getDisabled](#getdisabled)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getDisplayName](#getdisplayname)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getFolderDepth](#getfolderdepth)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getGitViewerEnabled](#getgitviewerenabled)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppClientId](#getgithubappclientid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppClientSecret](#getgithubappclientsecret)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppHtmlUrl](#getgithubapphtmlurl)() |
| `public`  *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)*  | [getGithubAppId](#getgithubappid)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getGithubAppInstallationId](#getgithubappinstallationid)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppName](#getgithubappname)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppOrg](#getgithubapporg)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppPem](#getgithubapppem)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppSecret](#getgithubappsecret)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppSlug](#getgithubappslug)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getGithubAppSuspended](#getgithubappsuspended)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGithubAppWebhookSecret](#getgithubappwebhooksecret)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getGlobal](#getglobal)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getGroup](#getgroup)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getMaxMinsToCommitEmail](#getmaxminstocommitemail)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getOrigin](#getorigin)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getPassword](#getpassword)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getPat](#getpat)() |
| `public` *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getPrHideFilter](#getprhidefilter)() |
| `public`  *[Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html)* \< *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)* \> | [getProjectMappingIds](#getprojectmappingids)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getRefSpecChanges](#getrefspecchanges)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getRefSpecCustom](#getrefspeccustom)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getRefSpecNotes](#getrefspecnotes)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getRequireUserPat](#getrequireuserpat)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getRevisionIndexing](#getrevisionindexing)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getSendCommitEmails](#getsendcommitemails)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getSmartCommitsEnabled](#getsmartcommitsenabled)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getSourcesDiffViewEnabled](#getsourcesdiffviewenabled)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getTagsFilter](#gettagsfilter)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getTfsCollection](#gettfscollection)() |
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getTrustFolderStat](#gettrustfolderstat)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getType](#gettype)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getUsername](#getusername)() |
| `public` `void` | [setApiFilter](#setapifilterstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  apiFilter) |
| `public` `void` | [setApiPath](#setapipathstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  apiPath) |
| `public` `void` | [setAwsRegion](#setawsregionstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  awsRegion) |
| `public` `void` | [setDisableSslVerification](#setdisablesslverificationboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  disableSslVerification) |
| `public` `void` | [setDisabled](#setdisabledboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  disabled) |
| `public` `void` | [setDisplayName](#setdisplaynamestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  displayName) |
| `public` `void` | [setFolderDepth](#setfolderdepthinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  folderDepth) |
| `public` `void` | [setGitViewerEnabled](#setgitviewerenabledboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  gitViewerEnabled) |
| `public` `void` | [setGlobal](#setglobalboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  global) |
| `public` `void` | [setMaxMinsToCommitEmail](#setmaxminstocommitemailinteger)( *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  maxMinsToCommitEmail) |
| `public` `void` | [setOrigin](#setoriginstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  origin) |
| `public` `void` | [setPassword](#setpasswordstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  password) |
| `public` `void` | [setPat](#setpatstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  pat) |
| `public` `void` | [setPrHideFilter](#setprhidefilterstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)* prHideFilter) |
| `public` `void` | [setProjectMappingIds](#setprojectmappingidsset)( *[Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html)* \< *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)* \> projectMappingIds) |
| `public` `void` | [setRefSpecChanges](#setrefspecchangesboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  refSpecChanges) |
| `public` `void` | [setRefSpecCustom](#setrefspeccustomstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  refSpecCustom) |
| `public` `void` | [setRefSpecNotes](#setrefspecnotesboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  refSpecNotes) |
| `public` `void` | [setRequireUserPat](#setrequireuserpatboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  requireUserPat) |
| `public` `void` | [setRevisionIndexing](#setrevisionindexingboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  revisionIndexing) |
| `public` `void` | [setSendCommitEmails](#setsendcommitemailsboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  sendCommitEmails) |
| `public` `void` | [setSmartCommitsEnabled](#setsmartcommitsenabledboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  smartCommitsEnabled) |
| `public` `void` | [setSourcesDiffViewEnabled](#setsourcesdiffviewenabledboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  sourcesDiffViewEnabled) |
| `public` `void` | [setTagsFilter](#settagsfilterstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  tagsFilter) |
| `public` `void` | [setTfsCollection](#settfscollectionstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  tfsCollection) |
| `public` `void` | [setTrustFolderStat](#settrustfolderstatboolean)( *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  trustFolderStat) |
| `public` `void` | [setType](#settypestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  type) |
| `public` `void` | [setUsername](#setusernamestring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  username) |



# Constructors
## IntegrationRequest()




## IntegrationRequest(IntegrationType, String, String, String)



# Methods
## getApiFilter()
Returns the JMESPath Filter property of the integration.



## getApiPath()
Returns the Custom API Path property of the integration.



## getAwsRegion()
Returns the AWS region property. Used for AWS integrations only.



## getDisableSslVerification()
Returns the SSL Verify setting.



## getDisabled()
Returns the whether the integration is disabled.



## getDisplayName()
Returns the display name of the integration.



## getFolderDepth()
Returns the Folder Depth property. Used for tracked folders only.



## getGitViewerEnabled()
Returns whether Repository Browser feature is enabled (true) or not (false).<br>
For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed/).




## getGithubAppClientId()




## getGithubAppClientSecret()




## getGithubAppHtmlUrl()




## getGithubAppId()




## getGithubAppInstallationId()




## getGithubAppName()




## getGithubAppOrg()




## getGithubAppPem()




## getGithubAppSecret()




## getGithubAppSlug()




## getGithubAppSuspended()




## getGithubAppWebhookSecret()




## getGlobal()
Returns whether the integration repositories are visible for all projects.



## getMaxMinsToCommitEmail()
Returns the property "Max commit age in minutes" value.



## getOrigin()
Returns the Origin of the integration.



## getPassword()
Returns password.



## getPat()
Returns PAT.



## getPrHideFilter()
Returns the regexp string of the pull request filter.



## getProjectMappingIds()
Returns the numeric projects IDs associated with the repository.



## getRefSpecChanges()




## getRefSpecCustom()




## getRefSpecNotes()




## getRequireUserPat()
Returns the value of the Require User PAT property.



## getRevisionIndexing()




## getSendCommitEmails()
Returns the property "Send email notifications" value.



## getSmartCommitsEnabled()
Returns whether smart commits processing for the integration repositories is enabled (true) or not (false).



## getSourcesDiffViewEnabled()




## getTagsFilter()




## getTfsCollection()
Returns the TFS Collection property. Used for Microsoft integrations only.



## getTrustFolderStat()




## getType()
Returns the type of the integration.



## getUsername()
Returns the username for the git host.



## setApiFilter(String)
Sets the JMESPath Filter property.
It is a [**JMESPath**](http://jmespath.org/) filter expression. The expression will be used to filter API results such as repository names, etc.<br>
For more information, see article [Working with JMESPath filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed/).

`GIJFacade.createIntegration()`: Optional.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `apiFilter`: new JMESPath Filter



## setApiPath(String)
Sets Custom API Path property. The integration will use the relative REST API path starting with "/" to retrieve the list of tracked repositories.<br>
For more information, see [Working with Custom API path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed/)

`GIJFacade.createIntegration()`: Optional.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `apiPath`: 



## setAwsRegion(String)
Sets AWS region; where CodeCommit repositories are located. The list of regions with their names can be found [here](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).

 Supported regions:

* us-east-1
* us-east-2
* us-west-1
* us-west-2
* af-south-1
* ap-east-1
* ap-south-1
* ap-south-2
* ap-northeast-3
* ap-northeast-2
* ap-southeast-1
* ap-southeast-3
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-central-2
* eu-west-1
* eu-west-2
* eu-west-3
* eu-south-1
* eu-south-2
* eu-north-1
* me-central-1
* me-south-1
* sa-east-1

`GIJFacade.createIntegration()`: Optional. Required for AWS integration creation.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `awsRegion`: 



## setDisableSslVerification(Boolean)
Sets SSL Verify setting.

The SSL Verify setting is set to `Enabled` by default. If set to `Disabled`, the Git Integration for Jira app will ignore verification of SSL certificates when connecting to a git server.

`GIJFacade.createIntegration()`: Optional. The default value for this setting is _**false**_.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `disableSslVerification`: 



## setDisabled(Boolean)
Sets the disabled flag for the integration.

Set the repository status to updated (enabled) or disabled. If left blank, the default setting for this field is _**false**_.

`GIJFacade.createIntegration()`: Optional. The default value is _**false**_
<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `disabled`: the new value of 'disabled' flag



## setDisplayName(String)
Sets the display name of the integration.<br>
This is the name that will appear in the Git Integration for Jira app repositories list.

`GIJFacade.createIntegration()`: Optional. Autogenerated by default.
<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `displayName`: the new display name



## setFolderDepth(Integer)
Sets Folder Depth property. Used for tracked folders only.

`GIJFacade.createIntegration()`: Optional. The default value is 1.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `folderDepth`: 



## setGitViewerEnabled(Boolean)
Enables or disables Repository Browser feature.

 `GIJFacade.createIntegration()`: Optional. Is true by default.<br>
 `GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `gitViewerEnabled`: new value for "Repository Browser" parameter



## setGlobal(Boolean)
If set to true, the projectMappingIds parameter is ignored. Otherwise, the projectMappingIds parameter value(s) are applied.


### **Parameters**
* `global`: new value for "Associate with all projects" property



## setMaxMinsToCommitEmail(Integer)
Sets the property "Max commit age in minutes" for the integration email notification for commits.

 `GIJFacade.createIntegration()`: Optional. The default value is **1440 minutes**.<br>
 `GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `maxMinsToCommitEmail`: the new value of 'Max commit age in minutes' property



## setOrigin(String)
Sets the Origin of the integration.<br>
This is the URL to the hosted git service used on the project.

For example, you might host your repository on GitHub, Beanstalk or your own server.

`GIJFacade.createIntegration()`: Required.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `origin`: the new origin.



## setPassword(String)



## setPat(String)



## setPrHideFilter(String)
Set the regexp for the pull request filter.



## setProjectMappingIds(Set\<Long\>)
Sets numeric projects IDs associated with the repository.

This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored _(equivalent to unchecking the_ *Associate to All Projects* _checkbox in the Advanced Setup dialog)_.

_Example:_ `“projectMappingIds”: [10000,10100]`

`GIJFacade.createIntegration()`: Optional.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `projectMappingIds`: new list of projects associated with the repository



## setRefSpecChanges(Boolean)




## setRefSpecCustom(String)




## setRefSpecNotes(Boolean)




## setRequireUserPat(Boolean)
Setting this parameter to true will require users to specify their own PAT for branch and pull/merge request management.

`GIJFacade.createIntegration()`: Optional. Is false by default.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `requireUserPat`: new value for "Require User PAT" parameter



## setRevisionIndexing(Boolean)




## setSendCommitEmails(Boolean)
Sets the property "Send email notifications" for the integration.

`GIJFacade.createIntegration()`: Optional. The default value is _**false**_.<br>
 `GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `sendCommitEmails`: the new value of 'Send email notifications' property



## setSmartCommitsEnabled(Boolean)
Enables or disables smart commits processing.

`GIJFacade.createIntegration()`: Optional. Is true by default.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `smartCommitsEnabled`: new value for "Smart Commits" parameter



## setSourcesDiffViewEnabled(Boolean)




## setTagsFilter(String)




## setTfsCollection(String)
Sets TFS Collection property. Used for Microsoft integrations only.

`GIJFacade.createIntegration()`: Optional.<br>
`GIJFacade.updateIntegration()`: Optional.

### **Parameters**
* `tfsCollection`: new collection



## setTrustFolderStat(Boolean)




## setType(String)
Sets type of the integration. Available values are the following:

 * GITHUB - integration with Github.com
 * GITHUB_SERVER - integration with GitHub Enterprise
 * GITLAB - integration with GitLab.com
 * GITLAB_SERVER - integration with GitLab Server (CE/EE) (APIv4)
 * GITLAB_SERVER_LEGACY - integration with GitLab Server (CE/EE) Legacy (APIv3)
 * FILESPACE - integration for a tracked folder
 * AZURE_DEVOPS - integration with Azure DevOps Repos
 * VSTS - integration with Visual Studio Team Services (VSTS)
 * AZURE - integration with Azure DevOps Server
 * TFS_SERVER - integration with Team Foundation Server (TFS)
 * AWS - integration with AWS CodeCommit
 * GERRIT - integration with Gerrit Code Review

`GIJFacade.createIntegration()`: Required.<br>
`GIJFacade.updateIntegration()`: is not allowed to be changed.

### **Parameters**
* `type`: type of a new integration



## setUsername(String)
Sets as username for the git host. Leave blank and use PAT if 2FA is enabled on the git server.

### **Parameters**
* `username`: 



