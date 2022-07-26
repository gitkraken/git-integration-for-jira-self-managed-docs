---

title: Class IntegrationRequest
description:
taxonomy:
    category: git-integration-for-jira-data-center

---


* Package [com.bigbrassband.jira.git.rest.integration](README.html)
*  *[Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)*  > [IntegrationRequest](IntegrationRequest-gij-self-managed)

This is a POJO object containing an integration properties/settings.


## Summary
#### Constructors
| Visibility | Signature |
| --- | --- |
| `public` | [IntegrationRequest](#integrationrequest)() |
| `public` | [IntegrationRequest](#integrationrequestintegrationtype-string-string-string)(*[IntegrationType](../../services/integration/IntegrationType-gij-self-managed)* type,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  origin,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  pat,  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  displayName) |

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
| `public`  *[Boolean](https://docs.oracle.com/javase/8/docs/api/java/lang/Boolean.html)*  | [getGlobal](#getglobal)() |
| `public`  *[Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html)*  | [getMaxMinsToCommitEmail](#getmaxminstocommitemail)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getOrigin](#getorigin)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getPassword](#getpassword)() |
| `public`  *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  | [getPat](#getpat)() |
| `public`  *[Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html)* < *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)* > | [getProjectMappingIds](#getprojectmappingids)() |
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
| `public` `void` | [initPassword](#initpasswordstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  password) |
| `public` `void` | [initPat](#initpatstring)( *[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)*  pat) |
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
| `public` `void` | [setProjectMappingIds](#setprojectmappingidsset)( *[Set](https://docs.oracle.com/javase/8/docs/api/java/util/Set.html)* < *[Long](https://docs.oracle.com/javase/8/docs/api/java/lang/Long.html)* > projectMappingIds) |
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
Returns JMESPath Filter property of the Integration.



## getApiPath()
Returns Custom API Path property of the Integration.



## getAwsRegion()
Returns AWS region property. It is used for AWS integrations only.



## getDisableSslVerification()
Returns SSL Verify setting.



## getDisabled()
Returns whether the Integration is disabled.



## getDisplayName()
Returns the Display Name of the Integration.



## getFolderDepth()
Returns Folder Depth property. Is used for tracked folders only.



## getGitViewerEnabled()
Returns whether Repository Browser feature is enabled.
 <br>
 For more information, see section, [Repository Browser](/git-integration-for-jira-data-center/repository-browser-gij-self-managed).



## getGlobal()
Returns whether the integration repositories are visible for all projects.



## getMaxMinsToCommitEmail()
Returns the property "Max commit age in minutes" value.



## getOrigin()
Returns the Origin of the Integration.



## getPassword()
Returns password encrypted.



## getPat()
Returns PAT encrypted.



## getProjectMappingIds()
Returns numeric projects IDs associated with the repository.



## getRefSpecChanges()




## getRefSpecCustom()




## getRefSpecNotes()




## getRequireUserPat()
Returns value of Require User PAT property.



## getRevisionIndexing()




## getSendCommitEmails()
Returns the property "Send email notifications" value.



## getSmartCommitsEnabled()
Returns whether smart commits processing for the integration repositories is enabled.



## getSourcesDiffViewEnabled()




## getTagsFilter()




## getTfsCollection()
Returns TFS Collection property. It is used for Microsoft integrations only.



## getTrustFolderStat()




## getType()
Returns type of the Integration.



## getUsername()
Returns username for the git host.



## initPassword(String)
Sets password as is. Use the method when none encryption is required.
 <br>
 GIJFacade requires an IntegrationRequest with an encrypted password, so use setPassword() instead of initPassword().

### **Parameters**
* `password`: password



## initPat(String)
Sets PAT as is. Use the method when none encryption is required.
 br>
 GIJFacade requires an IntegrationRequest with an encrypted PAT, so use setPat() instead of initPat().

### **Parameters**
* `pat`: 



## setApiFilter(String)
Sets JMESPath Filter property.
 It is a [**JMESPath**](http://jmespath.org/) filter expression. The expression will be used to filter API results such as repository names, etc.
 For more information, see article [Working with JMESPath filters](/git-integration-for-jira-data-center/working-with-jmespath-filters-gij-self-managed/).

 GIJFacade.createIntegration(): Optional.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `apiFilter`: new JMESPath Filter



## setApiPath(String)
Sets Custom API Path property. The integration will use the relative REST API path starting with "/"
 to retrieve the list of tracked repositories.
 For more information, see [Working with Custom API path](/git-integration-for-jira-data-center/working-with-custom-api-path-gij-self-managed/)

 GIJFacade.createIntegration(): Optional.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `apiPath`: 



## setAwsRegion(String)
Sets AWS region; where CodeCommit repositories are located.
 The list of regions with their names can be found [here](https://docs.aws.amazon.com/codecommit/latest/userguide/regions.html).

 Supported regions:

 * us-east-1
 * us-east-2
 * us-west-1
 * us-west-2
 * ap-south-1
 * ap-northeast-2
 * ap-southeast-1
 * ap-southeast-2
 * ap-northeast-1
 * ca-central-1
 * eu-central-1
 * eu-west-1
 * eu-west-2
 * eu-west-3
 * eu-north-1
 * me-south-1
 * sa-east-1

 GIJFacade.createIntegration(): Optional. Required for AWS Integration creation.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `awsRegion`: 



## setDisableSslVerification(Boolean)
Sets SSL Verify setting.

 The SSL Verify setting is set to Enabled by default. If set to disabled, the Git Integration for Jira app will
 ignore verification of SSL certificates when connecting to a git server.

 GIJFacade.createIntegration(): Optional. The default value for this setting is *false*.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `disableSslVerification`: 



## setDisabled(Boolean)
Sets the disabled flag for the Integration.

 Set the repository status to updated (enabled) or disabled.  If left blank, the default setting for this field is *false*.

 GIJFacade.createIntegration(): Optional. The default value is *false*
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `disabled`: the new value of 'disabled' flag



## setDisplayName(String)
Sets the Display Name of the Integration.
 This is the name that will appear in the Git Integration for Jira app repositories list.

 GIJFacade.createIntegration(): Optional. Is autogenerated by default.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `displayName`: the new display name



## setFolderDepth(Integer)
Sets Folder Depth property. Is used for tracked folders only.

 GIJFacade.createIntegration(): Optional. The default value is 1.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `folderDepth`: 



## setGitViewerEnabled(Boolean)
Enables or disables Repository Browser feature.

 GIJFacade.createIntegration(): Optional. Is true by default.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `gitViewerEnabled`: new value for "Repository Browser" parameter



## setGlobal(Boolean)
If set to true, the projectMappingIds parameter is ignored. Otherwise, the projectMappingIds parameter value(s) are applied.

### **Parameters**
* `global`: new value for "Associate with all projects" property



## setMaxMinsToCommitEmail(Integer)
Sets the property "Max commit age in minutes" for the Integration. Email notification for commits

 GIJFacade.createIntegration(): Optional. The default value is 1440 minutes.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `maxMinsToCommitEmail`: the new value of 'Max commit age in minutes' property



## setOrigin(String)
Sets the Origin of the Integration.
 This is the URL to the hosted git service used on the project.

 For example, you might host your repository on GitHub, Beanstalk or your own server.

 GIJFacade.createIntegration(): Required.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `origin`: the new origin.



## setPassword(String)
Sets new password for the git host. Leave blank and use PAT if 2FA is enabled on the git server.

 The IN password will be encrypted.
 Use initPassword() when none encryption is required.
 <br>
 GIJFacade requires an IntegrationRequest with an encrypted password, so use setPassword() instead of initPassword().

### **Parameters**
* `password`: new password



## setPat(String)
Sets the PAT (personal access token) to be used to connect the Integration. The IN PAT will be encrypted.
 Use initPat() when none encryption is required.
 <br>
 GIJFacade requires an IntegrationRequest with an encrypted PAT, so use setPat() instead of initPat().

### **Parameters**
* `pat`: pat



## setProjectMappingIds(Set<Long>)
Sets numeric projects IDs associated with the repository.

 This field accepts list of comma separated project IDs for project mapping. Trailing spaces are ignored
 _(equivalent to unchecking the_ *Associate to All Projects* _checkbox in the Advanced Setup dialog)_.
 <br>
 _Example:_ `“projectMappingIds”: [10000,10100]`

 GIJFacade.createIntegration(): Optional.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `projectMappingIds`: new list of projects associated with the repository



## setRefSpecChanges(Boolean)




## setRefSpecCustom(String)




## setRefSpecNotes(Boolean)




## setRequireUserPat(Boolean)
Setting this parameter to true will require users to specify their own PAT for branch and pull/merge request management.

 GIJFacade.createIntegration(): Optional. Is false by default.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `requireUserPat`: new value for "Require User PAT" parameter



## setRevisionIndexing(Boolean)




## setSendCommitEmails(Boolean)
Sets the property "Send email notifications" for the Integration.

 GIJFacade.createIntegration(): Optional. The default value is *false*???
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `sendCommitEmails`: the new value of 'Send email notifications' property



## setSmartCommitsEnabled(Boolean)
Enables or disables smart commits processing.
 <br><br>
 GIJFacade.createIntegration(): Optional. Is true by default.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `smartCommitsEnabled`: new value for "Smart Commits" parameter



## setSourcesDiffViewEnabled(Boolean)




## setTagsFilter(String)




## setTfsCollection(String)
Sets TFS Collection property. It is used for Microsoft integrations only.

 GIJFacade.createIntegration(): Optional.
 <br>
 GIJFacade.updateIntegration(): Optional.

### **Parameters**
* `tfsCollection`: new collection



## setTrustFolderStat(Boolean)




## setType(String)
Sets type of the Integration. Available values are the following:

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

 GIJFacade.createIntegration(): Required.
 <br>
 GIJFacade.updateIntegration(): is not allowed to be changed.

### **Parameters**
* `type`: type of a new integration



## setUsername(String)
Sets as username for the git host. Leave blank and use PAT if 2FA is enabled on the git server.

### **Parameters**
* `username`: 




