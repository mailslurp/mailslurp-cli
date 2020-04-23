# EmailControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**deleteAllEmails**](EmailControllerApi.md#deleteAllEmails) | **DELETE** /emails | Delete all emails
[**deleteEmail**](EmailControllerApi.md#deleteEmail) | **DELETE** /emails/{emailId} | Delete an email
[**downloadAttachment**](EmailControllerApi.md#downloadAttachment) | **GET** /emails/{emailId}/attachments/{attachmentId} | Get email attachment bytes
[**forwardEmail**](EmailControllerApi.md#forwardEmail) | **POST** /emails/{emailId}/forward | Forward email
[**getAttachmentMetaData**](EmailControllerApi.md#getAttachmentMetaData) | **GET** /emails/{emailId}/attachments/{attachmentId}/metadata | Get email attachment metadata
[**getAttachments**](EmailControllerApi.md#getAttachments) | **GET** /emails/{emailId}/attachments | Get all email attachment metadata
[**getEmail**](EmailControllerApi.md#getEmail) | **GET** /emails/{emailId} | Get email content
[**getEmailHTML**](EmailControllerApi.md#getEmailHTML) | **GET** /emails/{emailId}/html | Get email content as HTML
[**getEmailsPaginated**](EmailControllerApi.md#getEmailsPaginated) | **GET** /emails | Get all emails
[**getRawEmailContents**](EmailControllerApi.md#getRawEmailContents) | **GET** /emails/{emailId}/raw | Get raw email string
[**getRawEmailJson**](EmailControllerApi.md#getRawEmailJson) | **GET** /emails/{emailId}/raw/json | Get raw email in JSON
[**getUnreadEmailCount**](EmailControllerApi.md#getUnreadEmailCount) | **GET** /emails/unreadCount | Get unread email count
[**validateEmail**](EmailControllerApi.md#validateEmail) | **POST** /emails/{emailId}/validate | Validate email



## deleteAllEmails

Delete all emails

Deletes all emails in your account. Be careful as emails cannot be recovered

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

Delete an email

Deletes an email and removes it from the inbox. Deleted emails cannot be recovered.

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

Get email attachment bytes

Returns the specified attachment for a given email as a byte stream (file download). You can find attachment ids in email responses endpoint responses. The response type is application/octet-stream.

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

Forward email

Forward an existing email to new recipients.

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

Get email content

Returns a email summary object with headers and content. To retrieve the raw unparsed email use the getRawEmail endpoints

### Example

```bash
mailslurp getEmail emailId=value  decode=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]
 **decode** | **boolean** | Decode email body quoted-printable encoding to plain text. SMTP servers often encode text using quoted-printable format (for instance '=D7'). This can be a pain for testing | [optional] [default to false]

### Return type

[**Email**](Email.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getEmailHTML

Get email content as HTML

Retrieve email content as HTML response for viewing in browsers. Decodes quoted-printable entities and converts charset to UTF-8. Pass your API KEY as a request parameter when viewing in a browser: '?apiKey=xxx'

### Example

```bash
mailslurp getEmailHTML emailId=value  decode=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]
 **decode** | **boolean** | decode | [optional] [default to false]

### Return type

**string**

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: text/html

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getEmailsPaginated

Get all emails

By default returns all emails across all inboxes sorted by ascending created at date. Responses are paginated. You can restrict results to a list of inbox IDs. You can also filter out read messages

### Example

```bash
mailslurp getEmailsPaginated  Specify as:  inboxId=value1 inboxId=value2 inboxId=...  page=value  size=value  sort=value  unreadOnly=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**array[string]**](string.md) | Optional inbox ids to filter by. Can be repeated. By default will use all inboxes belonging to your account. | [optional] [default to null]
 **page** | **integer** | Optional page index in email list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in email list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]
 **unreadOnly** | **boolean** | Optional filter for unread emails only. All emails are considered unread until they are viewed in the dashboard or requested directly | [optional] [default to false]

### Return type

[**Page«EmailProjection»**](Page«EmailProjection».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getRawEmailContents

Get raw email string

Returns a raw, unparsed, and unprocessed email. If your client has issues processing the response it is likely due to the response content-type which is text/plain. If you need a JSON response content-type use the getRawEmailJson endpoint

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


## getRawEmailJson

Get raw email in JSON

Returns a raw, unparsed, and unprocessed email wrapped in a JSON response object for easier handling when compared with the getRawEmail text/plain response

### Example

```bash
mailslurp getRawEmailJson emailId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **emailId** | [**string**](.md) | emailId | [default to null]

### Return type

[**RawEmailJson**](RawEmailJson.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getUnreadEmailCount

Get unread email count

Get number of emails unread

### Example

```bash
mailslurp getUnreadEmailCount
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**UnreadCount**](UnreadCount.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## validateEmail

Validate email

Validate the HTML content of email if HTML is found. Considered valid if no HTML.

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

