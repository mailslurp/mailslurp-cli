# EmailControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**deleteAllEmails**](EmailControllerApi.md#deleteAllEmails) | **DELETE** /emails | Delete all emails
[**deleteEmail**](EmailControllerApi.md#deleteEmail) | **DELETE** /emails/{emailId} | Delete Email
[**downloadAttachment**](EmailControllerApi.md#downloadAttachment) | **GET** /emails/{emailId}/attachments/{attachmentId} | Get email attachment
[**forwardEmail**](EmailControllerApi.md#forwardEmail) | **POST** /emails/{emailId}/forward | Forward Email
[**getAttachmentMetaData**](EmailControllerApi.md#getAttachmentMetaData) | **GET** /emails/{emailId}/attachments/{attachmentId}/metadata | Get email attachment metadata
[**getAttachments**](EmailControllerApi.md#getAttachments) | **GET** /emails/{emailId}/attachments | Get all email attachment metadata
[**getEmail**](EmailControllerApi.md#getEmail) | **GET** /emails/{emailId} | Get Email Content
[**getEmailsPaginated**](EmailControllerApi.md#getEmailsPaginated) | **GET** /emails | Get all emails
[**getRawEmailContents**](EmailControllerApi.md#getRawEmailContents) | **GET** /emails/{emailId}/raw | Get Raw Email Content
[**validateEmail**](EmailControllerApi.md#validateEmail) | **POST** /emails/{emailId}/validate | Validate email



## deleteAllEmails

Delete all emails

Deletes all emails

### Example

```bash
mailslurp deleteAllEmails
```

### Parameters

This endpoint does not need any parameter.

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteEmail

Delete Email

Deletes an email and removes it from the inbox

### Example

```bash
mailslurp deleteEmail emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## downloadAttachment

Get email attachment

Returns the specified attachment for a given email as a byte stream (file download). Get the attachmentId from the email response.

### Example

```bash
mailslurp downloadAttachment attachmentId=value emailId=value  apiKey=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **attachmentId** | **string** | attachmentId | [default to null]
 **emailId** | [**string**](.md) | emailId | [default to null]
 **apiKey** | **string** | Can pass apiKey in url for this request if you wish to download the file in a browser | [optional] [default to null]

### Return type

**string**

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/octet-stream

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## forwardEmail

Forward Email

Forward email content to given recipients

### Example

```bash
mailslurp forwardEmail emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]
 **forwardEmailOptions** | [**ForwardEmailOptions**](ForwardEmailOptions.md) | forwardEmailOptions |

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAttachmentMetaData

Get email attachment metadata

Returns the metadata such as name and content-type for a given attachment and email.

### Example

```bash
mailslurp getAttachmentMetaData attachmentId=value emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **attachmentId** | **string** | attachmentId | [default to null]
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

[**AttachmentMetaData**](AttachmentMetaData.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAttachments

Get all email attachment metadata

Returns an array of attachment metadata such as name and content-type for a given email if present.

### Example

```bash
mailslurp getAttachments emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

[**array[AttachmentMetaData]**](AttachmentMetaData.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getEmail

Get Email Content

Returns a email summary object with headers and content. To retrieve the raw unparsed email use the getRawMessage endpoint

### Example

```bash
mailslurp getEmail emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

[**Email**](Email.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getEmailsPaginated

Get all emails

Responses are paginated

### Example

```bash
mailslurp getEmailsPaginated  Specify as:  inboxId=value1 inboxId=value2 inboxId=...  page=value  size=value  sort=value  unreadOnly=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**array[string]**](string.md) | Optional inbox ids to filter by. Can be repeated | [optional] [default to null]
 **page** | **integer** | Optional page index in email list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in email list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]
 **unreadOnly** | **boolean** | Optional filter for unread emails only | [optional] [default to false]

### Return type

[**Page«EmailProjection»**](Page«EmailProjection».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getRawEmailContents

Get Raw Email Content

Returns a raw, unparsed and unprocessed email

### Example

```bash
mailslurp getRawEmailContents emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

**string**

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: text/plain

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## validateEmail

Validate email

Validate HTML content of email

### Example

```bash
mailslurp validateEmail emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

[**ValidationDto**](ValidationDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

