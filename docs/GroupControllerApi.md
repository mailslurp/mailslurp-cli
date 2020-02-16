# GroupControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**addContactsToGroup**](GroupControllerApi.md#addContactsToGroup) | **PUT** /groups/{groupId}/contacts | Add contacts to a group
[**createGroup**](GroupControllerApi.md#createGroup) | **POST** /groups | Create a group
[**deleteGroup**](GroupControllerApi.md#deleteGroup) | **DELETE** /groups/{groupId} | Delete group
[**getAllGroups**](GroupControllerApi.md#getAllGroups) | **GET** /groups/paginated | Get all Contact Groups in paginated format
[**getGroup**](GroupControllerApi.md#getGroup) | **GET** /groups/{groupId} | Get group
[**getGroupWithContacts**](GroupControllerApi.md#getGroupWithContacts) | **GET** /groups/{groupId}/contacts | Get group and contacts belonging to it
[**getGroups**](GroupControllerApi.md#getGroups) | **GET** /groups | Get all groups
[**removeContactsFromGroup**](GroupControllerApi.md#removeContactsFromGroup) | **DELETE** /groups/{groupId}/contacts | Remove contacts from a group



## addContactsToGroup

Add contacts to a group

### Example

```bash
mailslurp addContactsToGroup groupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupId** | [**string**](.md) | groupId | [default to null]
 **updateGroupContactsOption** | [**UpdateGroupContacts**](UpdateGroupContacts.md) | updateGroupContactsOption |

### Return type

[**GroupContactsDto**](GroupContactsDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createGroup

Create a group

### Example

```bash
mailslurp createGroup
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createGroupOptions** | [**CreateGroupOptions**](CreateGroupOptions.md) | createGroupOptions |

### Return type

[**GroupDto**](GroupDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteGroup

Delete group

### Example

```bash
mailslurp deleteGroup groupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupId** | [**string**](.md) | groupId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllGroups

Get all Contact Groups in paginated format

### Example

```bash
mailslurp getAllGroups  page=value  size=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **integer** | Optional page index in inbox list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in inbox list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]

### Return type

[**Page«GroupProjection»**](Page«GroupProjection».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getGroup

Get group

### Example

```bash
mailslurp getGroup groupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupId** | [**string**](.md) | groupId | [default to null]

### Return type

[**GroupDto**](GroupDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getGroupWithContacts

Get group and contacts belonging to it

### Example

```bash
mailslurp getGroupWithContacts groupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupId** | [**string**](.md) | groupId | [default to null]

### Return type

[**GroupContactsDto**](GroupContactsDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getGroups

Get all groups

### Example

```bash
mailslurp getGroups
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**array[GroupProjection]**](GroupProjection.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## removeContactsFromGroup

Remove contacts from a group

### Example

```bash
mailslurp removeContactsFromGroup groupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupId** | [**string**](.md) | groupId | [default to null]
 **updateGroupContactsOption** | [**UpdateGroupContacts**](UpdateGroupContacts.md) | updateGroupContactsOption |

### Return type

[**GroupContactsDto**](GroupContactsDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

