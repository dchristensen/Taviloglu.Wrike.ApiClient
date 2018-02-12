# Taviloglu.Wrike.ApiClient
C# Wrapper for Wrike v3 Rest API

## Usage
Create your Wrike Client wtih your permanent token and just call the function you need.
```csharp
//create client
var bearerToken = "your_permanent_token";
var wrikeClient = new WrikeClient(bearerToken);

//get the list of custom fields
//https://developers.wrike.com/documentation/api/methods/query-custom-fields
var customFields = await wrikeClient.CustomFields.GetAsync();

//create new custom field
//https://developers.wrike.com/documentation/api/methods/create-custom-field
var newCustomField = new WrikeCustomField
{
    AccountId = "IEABX2HE",
    Title = "Sinan's custom field",
    Type = WrikeCustomFieldType.Duration
};
var field = await wrikeClient.CustomFields.CreateAsync(newCustomField);
```

## Implemented Methods 29%

<table class="tableizer-table">
<thead><tr class="tableizer-firstrow"><th>Mehod</th><th>IsImplemented</th><th>Group</th></tr></thead><tbody>
<tr>
                <td>[GET] /contacts</td>
                <td>&nbsp;</td>
                <td rowspan="4">Contacts</td>
            </tr>
            <tr>
                <td>[GET] /accounts/{accountId}/contacts</td>
                <td>&nbsp;</td>
            </tr>
            <tr>
                <td>[GET] /contacts/{contactId},{contactId},... - up to 100 IDs</td>
                <td>&nbsp;</td>
            </tr>
            <tr>
                <td>[PUT] /contacts/{contactId}</td>
                <td>&nbsp;</td>
            </tr>
 
 <tr><td>[GET] /users/{userId}</td><td>1</td><td rowspan="2">Users</td></tr>
 <tr><td>[PUT] /users/{userId}</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /groups/{groupId}</td><td>&nbsp;</td><td rowspan="5">Groups</td></tr>
 <tr><td>[GET] /accounts/{accountId}/groups</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /accounts/{accountId}/groups</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /groups/{groupId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /groups/{groupId}</td><td>1</td></tr>
 
 <tr><td>[GET] /accounts/{accountId}/invitations</td><td>&nbsp;</td><td rowspan="4">Invitations</td></tr>
 <tr><td>[POST] /accounts/{accountId}/invitations</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /invitations/{invitationId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /invitations/{invitationId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /accounts</td><td>&nbsp;</td><td rowspan="3">Accounts</td></tr>
 <tr><td>[GET] /accounts/{accountId}</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /accounts/{accountId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /accounts/{accountId}/workflows</td><td>&nbsp;</td><td rowspan="3">Workflows</td></tr>
 <tr><td>[POST] /accounts/{accountId}/workflows</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /workflows/{workflowId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /customfields</td><td>1</td><td rowspan="5">Custom Fields</td></tr>
 <tr><td>[GET] /accounts/{accountId}/customfields</td><td>1</td></tr>
 <tr><td>[GET] /customfields/{customfieldId},{customfieldId},... - up to 100 Ids</td><td>1</td></tr>
 <tr><td>[POST] /accounts/{accountId}/customfields</td><td>1</td></tr>
 <tr><td>[PUT] /customfields/{customfieldId}</td><td>1</td></tr>
 
 <tr><td>[GET] /folders</td><td>1</td><td rowspan="8">Folders & Projects</td></tr>
 <tr><td>[GET] /accounts/{accountId}/folders</td><td>1</td></tr>
 <tr><td>[GET] /folders/{folderId}/folders</td><td>1</td></tr>
 <tr><td>[GET] /folders/{folderId},{folderId},... - up to 100 IDs</td><td>1</td></tr>
 <tr><td>[POST] /folders/{folderId}/folders</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /copy_folder/{folderId}</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /folders/{folderId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /folders/{folderId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /tasks</td><td>1</td><td rowspan="7">Tasks</td></tr>
 <tr><td>[GET] /accounts/{accountId}/tasks</td><td>1</td></tr>
 <tr><td>[GET] /folders/{folderId}/tasks</td><td>1</td></tr>
 <tr><td>[GET] /tasks/{taskId},{taskId},... - up to 100 IDs</td><td>1</td></tr>
 <tr><td>[POST] /folders/{folderId}/tasks</td><td>1</td></tr>
 <tr><td>[PUT] /tasks/{taskId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /tasks/{taskId}</td><td>1</td></tr>
 
 <tr><td>[GET] /comments</td><td>&nbsp;</td><td rowspan="9">Comments</td></tr>
 <tr><td>[GET] /accounts/{accountId}/comments</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /folders/{folderId}/comments</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /tasks/{taskId}/comments</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /comments/{commentId},{commentId},... - up to 100 Ids</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /folders/{folderId}/comments</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /tasks/{taskId}/comments</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /comments/{commentId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /comments/{commentId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /tasks/{taskId}/dependencies</td><td>&nbsp;</td><td rowspan="5">Dependencies</td></tr>
 <tr><td>[GET] /dependencies/{dependencyId},{dependencyId},... - up to 100 IDs</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /tasks/{taskId}/dependencies</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /dependencies/{dependencyId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /dependencies/{dependencyId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /timelogs</td><td>&nbsp;</td><td rowspan="9">Timelogs</td></tr>
 <tr><td>[GET] /contacts/{contactId}/timelogs</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /accounts/{accountId}/timelogs</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /folders/{folderId}/timelogs</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /tasks/{taskId}/timelogs</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /timelogs/{timelogId}</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /tasks/{taskId}/timelogs</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /timelogs/{timelogId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /timelogs/{timelogId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /accounts/{accountId}/attachments</td><td>&nbsp;</td><td rowspan="11">Attachments</td></tr>
 <tr><td>[GET] /folders/{folderId}/attachments </td><td>&nbsp;</td></tr>
 <tr><td>[GET] /tasks/{taskId}/attachments</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /attachments/{attachmentId}</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /attachments/{attachmentId}/download</td><td>&nbsp;</td></tr>
 <tr><td>[GET] /attachments/{attachmentId}/preview </td><td>&nbsp;</td></tr>
 <tr><td>[GET] /attachments/{attachmentId}/url</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /folders/{folderId}/attachments</td><td>&nbsp;</td></tr>
 <tr><td>[POST] /tasks/{taskId}/attachments</td><td>&nbsp;</td></tr>
 <tr><td>[PUT] /attachments/{attachmentId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /attachments/{attachmentId}</td><td>&nbsp;</td></tr>
 
 <tr><td>[GET] /version</td><td>1</td><td>Version</td></tr>
 
 <tr><td>[GET] /ids</td><td>&nbsp;</td><td>Ids</td></tr>
 
 <tr><td>[GET] /colors</td><td>1</td><td>Colors</td></tr>
 
 <tr><td>[POST] /folders/{folderId}/webhooks</td><td>&nbsp;</td><td rowspan="7">Webhooks</td></tr>
 <tr><td>[POST] /accounts/{accountId}/webhooks</td><td>1</td></tr>
 <tr><td>[GET] /webhooks</td><td>1</td></tr>
 <tr><td>[GET] /accounts/{accountId}/webhooks</td><td>1</td></tr>
 <tr><td>[GET] /webhooks/{webhookId},{webhookId}</td><td>1</td></tr>
 <tr><td>[PUT] /webhooks/{webhookId}</td><td>&nbsp;</td></tr>
 <tr><td>[DELETE] /webhooks/{webhookId}</td><td>1</td></tr>
</tbody></table>
