# DomainControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**createDomain**](DomainControllerApi.md#createDomain) | **POST** /domains | Create Domain
[**deleteDomain**](DomainControllerApi.md#deleteDomain) | **DELETE** /domains/{id} | Delete a domain
[**getDomain**](DomainControllerApi.md#getDomain) | **GET** /domains/{id} | Get a domain
[**getDomains**](DomainControllerApi.md#getDomains) | **GET** /domains | Get domains



## createDomain

Create Domain

Link a domain that you own with MailSlurp so you can create email addresses using it. Endpoint returns DNS records used for validation. You must add these verification records to your host provider's DNS setup to verify the domain.

### Example

```bash
mailslurp createDomain
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domainOptions** | [**CreateDomainOptions**](CreateDomainOptions.md) | domainOptions |

### Return type

[**Domain plus verification records and status**](Domain plus verification records and status.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteDomain

Delete a domain

Delete a domain. This will disable any existing inboxes that use this domain.

### Example

```bash
mailslurp deleteDomain id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | [**string**](.md) | id | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getDomain

Get a domain

Returns domain verification status and tokens for a given domain

### Example

```bash
mailslurp getDomain id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | [**string**](.md) | id | [default to null]

### Return type

[**Domain plus verification records and status**](Domain plus verification records and status.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getDomains

Get domains

List all custom domains you have created

### Example

```bash
mailslurp getDomains
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**array[DomainPreview]**](DomainPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

