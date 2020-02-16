# ContactControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**createContact**](ContactControllerApi.md#createContact) | **POST** /contacts | Create a contact
[**deleteContact**](ContactControllerApi.md#deleteContact) | **DELETE** /contacts/{contactId} | Delete contact
[**getAllContacts**](ContactControllerApi.md#getAllContacts) | **GET** /contacts/paginated | Get all contacts
[**getContact**](ContactControllerApi.md#getContact) | **GET** /contacts/{contactId} | Get contact
[**getContacts**](ContactControllerApi.md#getContacts) | **GET** /contacts | Get all contacts



## createContact

Create a contact

### Example

```bash
mailslurp createContact
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createContactOptions** | [**CreateContactOptions**](CreateContactOptions.md) | createContactOptions |

### Return type

[**ContactDto**](ContactDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteContact

Delete contact

### Example

```bash
mailslurp deleteContact contactId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **contactId** | [**string**](.md) | contactId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllContacts

Get all contacts

### Example

```bash
mailslurp getAllContacts  page=value  size=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **integer** | Optional page index in inbox list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in inbox list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]

### Return type

[**Page«ContactProjection»**](Page«ContactProjection».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getContact

Get contact

### Example

```bash
mailslurp getContact contactId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **contactId** | [**string**](.md) | contactId | [default to null]

### Return type

[**ContactDto**](ContactDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getContacts

Get all contacts

### Example

```bash
mailslurp getContacts
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**array[ContactProjection]**](ContactProjection.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

