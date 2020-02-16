# WebhookControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**createWebhook**](WebhookControllerApi.md#createWebhook) | **POST** /inboxes/{inboxId}/webhooks | Attach a WebHook URL to an inbox
[**deleteWebhook**](WebhookControllerApi.md#deleteWebhook) | **DELETE** /inboxes/{inboxId}/webhooks/{webhookId} | Delete and disable a Webhook for an Inbox
[**getAllWebhooks**](WebhookControllerApi.md#getAllWebhooks) | **GET** /webhooks/paginated | List Webhooks Paginated
[**getWebhook**](WebhookControllerApi.md#getWebhook) | **GET** /webhooks/{webhookId} | Get a webhook for an Inbox
[**getWebhooks**](WebhookControllerApi.md#getWebhooks) | **GET** /inboxes/{inboxId}/webhooks | Get all Webhooks for an Inbox
[**sendTestData**](WebhookControllerApi.md#sendTestData) | **POST** /webhooks/{webhookId}/test | Send webhook test data



## createWebhook

Attach a WebHook URL to an inbox

Get notified whenever an inbox receives an email via a WebHook URL. An emailID will be posted to this URL every time an email is received for this inbox. The URL must be publicly reachable by the MailSlurp server. You can provide basicAuth values if you wish to secure this endpoint.

### Example

```bash
mailslurp createWebhook inboxId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]
 **webhookOptions** | [**CreateWebhookOptions**](CreateWebhookOptions.md) | webhookOptions |

### Return type

[**WebhookDto**](WebhookDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteWebhook

Delete and disable a Webhook for an Inbox

### Example

```bash
mailslurp deleteWebhook inboxId=value webhookId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]
 **webhookId** | [**string**](.md) | webhookId | [default to null]

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAllWebhooks

List Webhooks Paginated

List webhooks in paginated form. Allows for page index, page size, and sort direction.

### Example

```bash
mailslurp getAllWebhooks  page=value  size=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **integer** | Optional page index in inbox list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in inbox list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]

### Return type

[**Page«WebhookProjection»**](Page«WebhookProjection».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getWebhook

Get a webhook for an Inbox

### Example

```bash
mailslurp getWebhook webhookId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **webhookId** | [**string**](.md) | webhookId | [default to null]

### Return type

[**WebhookDto**](WebhookDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getWebhooks

Get all Webhooks for an Inbox

### Example

```bash
mailslurp getWebhooks inboxId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]

### Return type

[**array[WebhookDto]**](WebhookDto.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## sendTestData

Send webhook test data

### Example

```bash
mailslurp sendTestData webhookId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **webhookId** | [**string**](.md) | webhookId | [default to null]

### Return type

[**WebhookTestResult**](WebhookTestResult.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

