# InboxControllerApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**createInbox**](InboxControllerApi.md#createInbox) | **POST** /inboxes | Create an Inbox (email address)
[**deleteAllInboxes**](InboxControllerApi.md#deleteAllInboxes) | **DELETE** /inboxes | Delete all inboxes
[**deleteInbox**](InboxControllerApi.md#deleteInbox) | **DELETE** /inboxes/{inboxId} | Delete Inbox / Email Address
[**getAllInboxes**](InboxControllerApi.md#getAllInboxes) | **GET** /inboxes/paginated | List Inboxes Paginated
[**getEmails**](InboxControllerApi.md#getEmails) | **GET** /inboxes/{inboxId}/emails | Get emails in an Inbox
[**getInbox**](InboxControllerApi.md#getInbox) | **GET** /inboxes/{inboxId} | Get Inbox / EmailAddress
[**getInboxEmailsPaginated**](InboxControllerApi.md#getInboxEmailsPaginated) | **GET** /inboxes/{inboxId}/emails/paginated | Get inbox emails paginated
[**getInboxes**](InboxControllerApi.md#getInboxes) | **GET** /inboxes | List Inboxes / Email Addresses
[**sendEmail**](InboxControllerApi.md#sendEmail) | **POST** /inboxes/{inboxId} | Send Email
[**setInboxFavourited**](InboxControllerApi.md#setInboxFavourited) | **PUT** /inboxes/{inboxId}/favourite | Set inbox favourited state



## createInbox

Create an Inbox (email address)

Create a new inbox and with a ranmdomized email address to send and receive from. Pass emailAddress parameter if you wish to use a specific email address. Creating an inbox is required before sending or receiving emails. If writing tests it is recommended that you create a new inbox during each test method so that it is unique and empty.

### Example

```bash
mailslurp createInbox  description=value  emailAddress=value  expiresAt=value  favourite=value  name=value  Specify as:  tags=value1 tags=value2 tags=...
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **description** | **string** | Optional description for an inbox. | [optional] [default to null]
 **emailAddress** | **string** | Optional email address including domain you wish inbox to use (eg: test123@mydomain.com). Only supports domains that you have registered and verified with MailSlurp using dashboard or 'createDomain' method. | [optional] [default to null]
 **expiresAt** | **string** | Optional expires at timestamp. If your plan supports this feature you can specify when an inbox should expire. If left empty inbox will exist permanently or expire when your plan dictates | [optional] [default to null]
 **favourite** | **boolean** | Is inbox favourited. | [optional] [default to null]
 **name** | **string** | Optional name for an inbox. | [optional] [default to null]
 **tags** | [**array[string]**](string.md) | Optional tags for an inbox. Can be used for searching and filtering inboxes. | [optional] [default to null]

### Return type

[**Inbox**](Inbox.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteAllInboxes

Delete all inboxes

Permanently delete all inboxes and associated email addresses and all emails within the given inboxes

### Example

```bash
mailslurp deleteAllInboxes
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


## deleteInbox

Delete Inbox / Email Address

Permanently delete an inbox and associated email address and all emails within the given inboxes

### Example

```bash
mailslurp deleteInbox inboxId=value
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


## getAllInboxes

List Inboxes Paginated

List inboxes in paginated form. Allows for page index, page size, and sort direction. Can also filter by favourited or email address like pattern.

### Example

```bash
mailslurp getAllInboxes  favourite=value  page=value  search=value  size=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **favourite** | **boolean** | Optionally filter results for favourites only | [optional] [default to false]
 **page** | **integer** | Optional page index in inbox list pagination | [optional] [default to 0]
 **search** | **string** | Optionally filter by search words partial matching ID, tags, name, and email address | [optional] [default to null]
 **size** | **integer** | Optional page size in inbox list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]

### Return type

[**Page«InboxProjection»**](Page«InboxProjection».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getEmails

Get emails in an Inbox

List emails that an inbox has received. Only emails that are sent to the inbox's email address will appear in the inbox. It may take several seconds for any email you send to an inbox's email address to appear in the inbox. To make this endpoint wait for a minimum number of emails use the 'minCount' parameter. The server will retry the inbox database until the 'minCount' is satisfied or the 'retryTimeout' is reached

### Example

```bash
mailslurp getEmails inboxId=value  limit=value  minCount=value  retryTimeout=value  since=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | Id of inbox that emails belongs to | [default to null]
 **limit** | **integer** | Limit the result set, ordered by received date time sort direction | [optional] [default to null]
 **minCount** | **integer** | Minimum acceptable email count. Will cause request to hang (and retry) until minCount is satisfied or retryTimeout is reached. | [optional] [default to null]
 **retryTimeout** | **integer** | Maximum milliseconds to spend retrying inbox database until minCount emails are returned | [optional] [default to null]
 **since** | **string** | Exclude emails received before this ISO 8601 date time | [optional] [default to null]
 **sort** | **string** | Sort the results by received date and direction ASC or DESC | [optional] [default to null]

### Return type

[**array[EmailPreview]**](EmailPreview.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getInbox

Get Inbox / EmailAddress

Returns an inbox's properties, including its email address and ID.

### Example

```bash
mailslurp getInbox inboxId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]

### Return type

[**Inbox**](Inbox.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getInboxEmailsPaginated

Get inbox emails paginated

Get a paginated list of emails in an inbox. Does not hold connections open.

### Example

```bash
mailslurp getInboxEmailsPaginated inboxId=value  page=value  size=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | Id of inbox that emails belongs to | [default to null]
 **page** | **integer** | Optional page index in inbox emails list pagination | [optional] [default to 0]
 **size** | **integer** | Optional page size in inbox emails list pagination | [optional] [default to 20]
 **sort** | **string** | Optional createdAt sort direction ASC or DESC | [optional] [default to ASC]

### Return type

[**Page«EmailPreview»**](Page«EmailPreview».md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getInboxes

List Inboxes / Email Addresses

List the inboxes you have created

### Example

```bash
mailslurp getInboxes
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**array[Inbox]**](Inbox.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## sendEmail

Send Email

Send an email from the inbox's email address. Specify the email recipients and contents in the request body. See the 'SendEmailOptions' for more information. Note the 'inboxId' refers to the inbox's id NOT its email address

### Example

```bash
mailslurp sendEmail inboxId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]
 **sendEmailOptions** | [**SendEmailOptions**](SendEmailOptions.md) | sendEmailOptions |

### Return type

(empty response body)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: Not Applicable

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## setInboxFavourited

Set inbox favourited state

Set and return new favourite state for an inbox

### Example

```bash
mailslurp setInboxFavourited inboxId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inboxId** | [**string**](.md) | inboxId | [default to null]
 **setInboxFavouritedOptions** | [**SetInboxFavouritedOptions**](SetInboxFavouritedOptions.md) | setInboxFavouritedOptions |

### Return type

[**Inbox**](Inbox.md)

### Authorization

[API_KEY](../README.md#API_KEY)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

