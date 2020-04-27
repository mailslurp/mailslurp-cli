# WaitForControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**waitFor**](WaitForControllerApi.md#waitFor) | **POST** /waitFor | Wait for conditions to be met
[**waitForEmailCount**](WaitForControllerApi.md#waitForEmailCount) | **GET** /waitForEmailCount | Wait for and return count number of emails
[**waitForLatestEmail**](WaitForControllerApi.md#waitForLatestEmail) | **GET** /waitForLatestEmail | Fetch inbox&#39;s latest email or if empty wait for an email to arrive
[**waitForMatchingEmail**](WaitForControllerApi.md#waitForMatchingEmail) | **POST** /waitForMatchingEmails | Wait or return list of emails that match simple matching patterns
[**waitForNthEmail**](WaitForControllerApi.md#waitForNthEmail) | **GET** /waitForNthEmail | Wait for or fetch the email with a given index in the inbox specified



## waitFor

Wait for conditions to be met

Generic waitFor method that will wait until an inbox meets given conditions or return immediately if already met

### Example

```bash
mailslurp waitFor
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **waitForConditions** | [**WaitForConditions**](WaitForConditions.md) | Conditions to wait for | [optional]

### Return type

[**array[EmailPreview]**](EmailPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## waitForEmailCount

Wait for and return count number of emails

If inbox contains count or more emails at time of request then return count worth of emails. If not wait until the count is reached and return those or return an error if timeout is exceeded.

### Example

```bash
mailslurp waitForEmailCount  count=value  inboxId=value  timeout=value  unreadOnly=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **count** | **integer** | Number of emails to wait for. Must be greater that 1 | [optional] [default to null]
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]
 **unreadOnly** | **boolean** | Optional filter for unread only | [optional] [default to false]

### Return type

[**array[EmailPreview]**](EmailPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## waitForLatestEmail

Fetch inbox's latest email or if empty wait for an email to arrive

Will return either the last received email or wait for an email to arrive and return that. If you need to wait for an email for a non-empty inbox set 'unreadOnly=true' or see the other receive methods such as 'waitForNthEmail' or 'waitForEmailCount'.

### Example

```bash
mailslurp waitForLatestEmail  inboxId=value  timeout=value  unreadOnly=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]
 **unreadOnly** | **boolean** | Optional filter for unread only. | [optional] [default to false]

### Return type

[**Email**](Email.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## waitForMatchingEmail

Wait or return list of emails that match simple matching patterns

Perform a search of emails in an inbox with the given patterns. If results match expected count then return or else retry the search until results are found or timeout is reached. Match options allow simple CONTAINS or EQUALS filtering on SUBJECT, TO, BCC, CC, and FROM. See the 'MatchOptions' object for options.

### Example

```bash
mailslurp waitForMatchingEmail  count=value  inboxId=value  timeout=value  unreadOnly=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **matchOptions** | [**MatchOptions**](MatchOptions.md) | matchOptions |
 **count** | **integer** | Number of emails to wait for. Must be greater that 1 | [optional] [default to null]
 **inboxId** | [**string**](.md) | Id of the inbox we are fetching emails from | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait | [optional] [default to null]
 **unreadOnly** | **boolean** | Optional filter for unread only | [optional] [default to false]

### Return type

[**array[EmailPreview]**](EmailPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## waitForNthEmail

Wait for or fetch the email with a given index in the inbox specified

If nth email is already present in inbox then return it. If not hold the connection open until timeout expires or the nth email is received and returned.

### Example

```bash
mailslurp waitForNthEmail  inboxId=value  index=value  timeout=value  unreadOnly=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | Id of the inbox you are fetching emails from | [optional] [default to null]
 **index** | **integer** | Zero based index of the email to wait for. If an inbox has 1 email already and you want to wait for the 2nd email pass index=1 | [optional] [default to null]
 **timeout** | **integer** | Max milliseconds to wait for the nth email if not already present | [optional] [default to null]
 **unreadOnly** | **boolean** | Optional filter for unread only | [optional] [default to false]

### Return type

[**Email**](Email.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

