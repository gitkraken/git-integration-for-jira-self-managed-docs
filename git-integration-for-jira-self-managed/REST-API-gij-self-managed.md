---

title: REST API
description:
taxonomy:
    category: git-integration-for-jira-data-center

---

Welcome to the Git Integration for Jira app REST API reference page index.

On this page, you will find the list of available REST APIs supported by the Git Integration for Jira app.  Click on a topic title to view its content or search through the related topics.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-bulkchg-icon.png' width=52 height=39 />

[**Bulk Change**](/git-integration-for-jira-data-center/bulk-change-gij-self-managed)

The bulk change API extends the possibility of importing and exporting repository configuration by automating the process via scripts.

*   [Bulk Export Configuration](/git-integration-for-jira-data-center/bulk-export-gij-self-managed)  –  The API returns a file with the plugin configuration.

*   [Bulk Import Configuration](/git-integration-for-jira-data-center/bulk-import-gij-self-managed)  –  Starts the process of importing configuration and returns the ID of the importing thread.

[Getting Bulk Import Information](/git-integration-for-jira-data-center/get-bulk-import-information-gij-self-managed)  –  Obtains information about the importing thread.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-repoapi-icon.png' width=48 height=48 />

[**Repository**](/git-integration-for-jira-data-center/repository-api-gij-self-managed)

The repository REST API allows query of the project repository list; as well as adding, updating and deleting repositories from the Git Integration app repository configuration.

*   [Retrieve Repository List](/git-integration-for-jira-data-center/retrieve-repository-list-gij-self-managed)  –  Retrieves list of repositories mapped to a given project.

*   [Add New Repository](/git-integration-for-jira-data-center/add-new-repository-gij-self-managed)  –  Creates new repository from the given settings.

*   [Update Existing Repository](/git-integration-for-jira-data-center/update-existing-repository-gij-self-managed)  –  Updates the existing repository from the given settings.

*   [Delete Existing Repository](/git-integration-for-jira-data-center/delete-existing-repository-gij-self-managed)  –  Deletes the existing repository from the Git Integration app repository configuration.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-reindexapi-icon.png' width=57 height=48 />

[**Reindex**](/git-integration-for-jira-data-center/reindex-api-gij-self-managed)

Call the Reindex REST API to have more control on indexing.

*   [Reindex POST](/git-integration-for-jira-data-center/reindex-post-api-gij-self-managed)  –  Starts the reindex process in a separate thread and returns the result immediately.

*   [Reindex GET](/git-integration-for-jira-data-center/reindex-get-api-gij-self-managed)  –  Use this method to track messages for a particular thread.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-commitsapi-icon.png' width=49 height=48 />

[**Commits**](/git-integration-for-jira-data-center/commits-api-gij-self-managed)

*   [Get Commits](/git-integration-for-jira-data-center/get-commits-gij-self-managed)  –  Call the Get Commits API to obtain commit information associated with an issue.

*   [showFiles Commits](/git-integration-for-jira-data-center/showfiles-gij-self-managed)  –  Extend the Commits API to review which files changed related to a specific Jira issue.

*   [Get Commit Issue Changes](/git-integration-for-jira-data-center/get-commit-issue-changes-gij-self-managed) - Returns the list of issues associated with the commit from the specified repository.

*   [Update Commit Issue Changes](/git-integration-for-jira-data-center/update-commit-issue-changes-gij-self-managed) - Updates the list of issues associated with the commit to the specified repository.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-branchesapi-icon.png' width=52 height=48 />

[**Branches**](/git-integration-for-jira-data-center/branches-api-gij-self-managed)

Gets list of branches associated to a Jira issue.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-tagsapi-icon.png' width=56 height=48 />

[**Tags**](/git-integration-for-jira-data-center/tags-api-gij-self-managed)

Returns several latest tags for the issue.  Tags are sorted in chronological order from newest to oldest.

&nbsp;
<hr>
&nbsp;

<img src='/wp-content/uploads/gij-bbb-repoapi-icon.png' width=48 height=48 />

[**Integration**](/git-integration-for-jira-data-center/integration-api-gij-self-managed)

The Integration API allows administrators to add or manage one or more repositories/integrations.

*   [Add New Integration](/git-integration-for-jira-data-center/add-new-integration-gij-self-managed)  –  Adds a new integration to the git configuration list via the API call.

*   [Add New Integration Type](/git-integration-for-jira-data-center/add-new-integration-type-api-examples-gij-self-managed)  –  Adds a new integration to the git configuration list via the API call using the supported integration types.

*   [Update Existing Integration](/git-integration-for-jira-data-center/update-existing-integration-gij-self-managed)  –  Updates the existing parameters of the specified integration.

*   [Remove Integration](/git-integration-for-jira-data-center/remove-integration-gij-self-managed)  –  Deletes the existing integration from the Git Integration for Jira app repository configuration.

*   [Retrieve an Integration](/git-integration-for-jira-data-center/retrieve-an-integration-gij-self-managed) – Retrieves the parameter details of an integration from the git repository configuration.

*   [Retrieve Integration List](/git-integration-for-jira-data-center/retrieve-integration-list-gij-self-managed) – Retrieves the list of integrations and their respective parameter details from the git repository configuration.

