# CommonOperationsApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**createNewEmailAddress**](CommonOperationsApi.md#createNewEmailAddress) | **POST** /newEmailAddress | Create new email address
[**deleteEmail**](CommonOperationsApi.md#deleteEmail) | **DELETE** /deleteEmail | Delete an email
[**deleteEmailAddress**](CommonOperationsApi.md#deleteEmailAddress) | **DELETE** /deleteEmailAddress | Delete email address and its emails
[**emptyInbox**](CommonOperationsApi.md#emptyInbox) | **DELETE** /emptyInbox | Delete all emails in an inbox
[**sendEmailSimple**](CommonOperationsApi.md#sendEmailSimple) | **POST** /sendEmail | Send an email from a random email address
[**waitForEmailCount**](CommonOperationsApi.md#waitForEmailCount) | **GET** /waitForEmailCount | Wait for and return count number of emails
[**waitForLatestEmail**](CommonOperationsApi.md#waitForLatestEmail) | **GET** /waitForLatestEmail | Fetch inbox&#39;s latest email or if empty wait for email to arrive
[**waitForMatchingEmail**](CommonOperationsApi.md#waitForMatchingEmail) | **POST** /waitForMatchingEmails | Wait or return list of emails that match simple matching patterns
[**waitForNthEmail**](CommonOperationsApi.md#waitForNthEmail) | **GET** /waitForNthEmail | Wait for or fetch the email with a given index in the inbox specified


## **createNewEmailAddress**

Create new email address

Returns an Inbox with an 'id' and an 'emailAddress'

### Example
```bash
mailslurp createNewEmailAddress
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**Inbox**](Inbox.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: Not Applicable
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **deleteEmail**

Delete an email

Deletes an email

### Example
```bash
mailslurp deleteEmail  emailId=value
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

## **deleteEmailAddress**

Delete email address and its emails

Deletes an inbox

### Example
```bash
mailslurp deleteEmailAddress  inboxId=value
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: Not Applicable
 - **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **emptyInbox**

Delete all emails in an inbox

Deletes all emails

### Example
```bash
mailslurp emptyInbox  inboxId=value
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: Not Applicable
 - **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **sendEmailSimple**

Send an email from a random email address

To specify an email address first create an inbox and use that with the other send email methods

### Example
```bash
mailslurp sendEmailSimple
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sendEmailOptions** | [**SendEmailOptions**](SendEmailOptions.md) | sendEmailOptions |

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **waitForEmailCount**

Wait for and return count number of emails

Will only wait if count is greater that the found emails in given inbox.If you need to wait for an email for a non-empty inbox see the other receive methods.

### Example
```bash
mailslurp waitForEmailCount  count=value  inboxId=value  timeout=value
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **count** | **integer** | Number of emails to wait for. Must be greater that 1 | [optional] [default to null]
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]

### Return type

[**array[EmailPreview]**](EmailPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: Not Applicable
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **waitForLatestEmail**

Fetch inbox's latest email or if empty wait for email to arrive

Will return either the last received email or wait for an email to arrive and return that. If you need to wait for an email for a non-empty inbox see the other receive methods.

### Example
```bash
mailslurp waitForLatestEmail  inboxId=value  timeout=value
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]

### Return type

[**Email**](Email.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: Not Applicable
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **waitForMatchingEmail**

Wait or return list of emails that match simple matching patterns

Results must also meet provided count. Match options allow simple CONTAINS or EQUALS filtering on SUBJECT, TO, BCC, CC, and FROM.

### Example
```bash
mailslurp waitForMatchingEmail  count=value  inboxId=value  timeout=value
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **matchOptions** | [**MatchOptions**](MatchOptions.md) | matchOptions |
 **count** | **integer** | Number of emails to wait for. Must be greater that 1 | [optional] [default to null]
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]

### Return type

[**array[EmailPreview]**](EmailPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

## **waitForNthEmail**

Wait for or fetch the email with a given index in the inbox specified

### Example
```bash
mailslurp waitForNthEmail  inboxId=value  index=value  timeout=value
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **index** | **integer** | Zero based index of the email to wait for | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]

### Return type

[**Email**](Email.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

 - **Content-Type**: Not Applicable
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

