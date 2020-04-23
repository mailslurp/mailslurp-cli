# AliasControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**createAlias**](AliasControllerApi.md#createAlias) | **POST** /aliases | Create an email alias
[**createAnonymousAlias**](AliasControllerApi.md#createAnonymousAlias) | **POST** /aliases/anonymous | Create an anonymous email alias
[**deleteAlias**](AliasControllerApi.md#deleteAlias) | **DELETE** /aliases/{aliasId} | Delete an owned alias
[**getAlias**](AliasControllerApi.md#getAlias) | **GET** /aliases/{aliasId} | Get an email alias
[**getAliases**](AliasControllerApi.md#getAliases) | **GET** /aliases | Get all email aliases
[**updateAlias**](AliasControllerApi.md#updateAlias) | **PUT** /aliases/{aliasId} | Update an owned alias



## createAlias

Create an email alias

Create an email alias belonging to a user ID. To create anonymous aliases use the 'createAnonymousAlias' method.

### Example

```bash
mailslurp createAlias
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createOwnedAliasOptions** | [**CreateOwnedAliasOptions**](CreateOwnedAliasOptions.md) | createOwnedAliasOptions |

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createAnonymousAlias

Create an anonymous email alias

### Example

```bash
mailslurp createAnonymousAlias
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createAnonymousAliasOptions** | [**CreateAnonymousAliasOptions**](CreateAnonymousAliasOptions.md) | createAnonymousAliasOptions |

### Return type

[**Alias**](Alias.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteAlias

Delete an owned alias

### Example

```bash
mailslurp deleteAlias aliasId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **aliasId** | [**string**](.md) | aliasId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAlias

Get an email alias

Get an email alias by ID

### Example

```bash
mailslurp getAlias aliasId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **aliasId** | [**string**](.md) | aliasId | [default to null]

### Return type

[**Alias**](Alias.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAliases

Get all email aliases

Get all email aliases in paginated form

### Example

```bash
mailslurp getAliases  page=value  size=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **integer** | Optional page index in alias list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in alias list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]

### Return type

[**Page«Alias»**](Page«Alias».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateAlias

Update an owned alias

### Example

```bash
mailslurp updateAlias aliasId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **aliasId** | [**string**](.md) | aliasId | [default to null]
 **createOwnedAliasOptions** | [**CreateOwnedAliasOptions**](CreateOwnedAliasOptions.md) | createOwnedAliasOptions |

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

