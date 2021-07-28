# Create App Registration for Graph Access
Permissions needed

- 
- 

# Create SP for APIM management

Docs
- https://docs.microsoft.com/en-us/azure/api-management/api-management-role-based-access-control
- https://docs.microsoft.com/en-us/cli/azure/ad/sp?view=azure-cli-latest#az_ad_sp_create_for_rbac


```
az ad sp create-for-rbac --sdk-auth -n "apim-admin" 
   --role "API Management Service Contributor" 
   --scopes /subscriptions/<subscriptionId>/resourceGroups/<rgname>/providers/Microsoft.ApiManagement/service/<ApimName>
```

```

{
  "clientId": "778671d4-7b9d-44b2-aab3-5bdff51a7196",
  "clientSecret": "IEqU2CYWp2Egndes1yK0jZ.FxQo~fBzWxi",
  "subscriptionId": "7ab070b2-d112-4fe1-ae56-92978ac7e02a",
  "tenantId": "a3224a3f-3d62-4b9a-b070-dd7305016a23",
  "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}
```

## Add new JWT Validate policy in APIM

Docs
- https://docs.microsoft.com/en-us/rest/api/apimanagement/2020-06-01-preview/apipolicy/createorupdate

## The current signed in user needs to have the following role assignment (at minimum)
```
  "roleDefinitionName": "API Management Service Contributor",
  "scope": "/subscriptions/<sub ID>/resourceGroups/<RG Name?/providers/Microsoft.ApiManagement/service/<APIM Name>"
```