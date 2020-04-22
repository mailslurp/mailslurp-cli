# MailSlurp API Bash client

## Overview

This is a Bash client script for accessing MailSlurp API service.

The script uses cURL underneath for making all REST calls.

## Usage

```shell
# Make sure the script has executable rights
$ chmod u+x mailslurp

# Print the list of operations available on the service
$ ./mailslurp -h

# Print the service description
$ ./mailslurp --about

# Print detailed information about specific operation
$ ./mailslurp <operationId> -h

# Make GET request
./mailslurp --host http://<hostname>:<port> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make GET request using arbitrary curl options (must be passed before <operationId>) to an SSL service using username:password
mailslurp -k -sS --tlsv1.2 --host https://<hostname> -u <user>:<password> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make POST request
$ echo '<body_content>' | mailslurp --host <hostname> --content-type json <operationId> -

# Make POST request with simple JSON content, e.g.:
# {
#   "key1": "value1",
#   "key2": "value2",
#   "key3": 23
# }
$ echo '<body_content>' | mailslurp --host <hostname> --content-type json <operationId> key1==value1 key2=value2 key3:=23 -

# Preview the cURL command without actually executing it
$ mailslurp --host http://<hostname>:<port> --dry-run <operationid>

```

## Docker image

You can easily create a Docker image containing a preconfigured environment
for using the REST Bash client including working autocompletion and short
welcome message with basic instructions, using the generated Dockerfile:

```shell
docker build -t my-rest-client .
docker run -it my-rest-client
```

By default you will be logged into a Zsh environment which has much more
advanced auto completion, but you can switch to Bash, where basic autocompletion
is also available.

## Shell completion

### Bash

The generated bash-completion script can be either directly loaded to the current Bash session using:

```shell
source mailslurp.bash-completion
```

Alternatively, the script can be copied to the `/etc/bash-completion.d` (or on OSX with Homebrew to `/usr/local/etc/bash-completion.d`):

```shell
sudo cp mailslurp.bash-completion /etc/bash-completion.d/mailslurp
```

#### OS X

On OSX you might need to install bash-completion using Homebrew:

```shell
brew install bash-completion
```

and add the following to the `~/.bashrc`:

```shell
if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi
```

### Zsh

In Zsh, the generated `_mailslurp` Zsh completion file must be copied to one of the folders under `$FPATH` variable.

## Documentation for API Endpoints

All URIs are relative to **

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AliasControllerApi* | [**createAlias**](docs/AliasControllerApi.md#createalias) | **POST** /aliases | Create an email alias
*AliasControllerApi* | [**createAnonymousAlias**](docs/AliasControllerApi.md#createanonymousalias) | **POST** /aliases/anonymous | Create an anonymous email alias
*AliasControllerApi* | [**deleteAlias**](docs/AliasControllerApi.md#deletealias) | **DELETE** /aliases/{aliasId} | Delete an owned alias
*AliasControllerApi* | [**getAlias**](docs/AliasControllerApi.md#getalias) | **GET** /aliases/{aliasId} | Get an email alias
*AliasControllerApi* | [**getAliases**](docs/AliasControllerApi.md#getaliases) | **GET** /aliases | Get all email aliases
*AliasControllerApi* | [**updateAlias**](docs/AliasControllerApi.md#updatealias) | **PUT** /aliases/{aliasId} | Update an owned alias
*AttachmentControllerApi* | [**uploadAttachment**](docs/AttachmentControllerApi.md#uploadattachment) | **POST** /attachments | Upload an attachment for sending
*AttachmentControllerApi* | [**uploadMultipartForm**](docs/AttachmentControllerApi.md#uploadmultipartform) | **POST** /attachments/multipart | Upload an attachment for sending using Multipart Form
*BulkActionsControllerApi* | [**bulkCreateInboxes**](docs/BulkActionsControllerApi.md#bulkcreateinboxes) | **POST** /bulk/inboxes | Bulk create Inboxes (email addresses)
*BulkActionsControllerApi* | [**bulkDeleteInboxes**](docs/BulkActionsControllerApi.md#bulkdeleteinboxes) | **DELETE** /bulk/inboxes | Bulk Delete Inboxes
*BulkActionsControllerApi* | [**bulkSendEmails**](docs/BulkActionsControllerApi.md#bulksendemails) | **POST** /bulk/send | Bulk Send Emails
*CommonActionsControllerApi* | [**createNewEmailAddress**](docs/CommonActionsControllerApi.md#createnewemailaddress) | **POST** /createInbox | Create new random inbox
*CommonActionsControllerApi* | [**createNewEmailAddress1**](docs/CommonActionsControllerApi.md#createnewemailaddress1) | **POST** /newEmailAddress | Create new random inbox
*CommonActionsControllerApi* | [**emptyInbox**](docs/CommonActionsControllerApi.md#emptyinbox) | **DELETE** /emptyInbox | Delete all emails in an inbox
*CommonActionsControllerApi* | [**sendEmailSimple**](docs/CommonActionsControllerApi.md#sendemailsimple) | **POST** /sendEmail | Send an email
*ContactControllerApi* | [**createContact**](docs/ContactControllerApi.md#createcontact) | **POST** /contacts | Create a contact
*ContactControllerApi* | [**deleteContact**](docs/ContactControllerApi.md#deletecontact) | **DELETE** /contacts/{contactId} | Delete contact
*ContactControllerApi* | [**getAllContacts**](docs/ContactControllerApi.md#getallcontacts) | **GET** /contacts/paginated | Get all contacts
*ContactControllerApi* | [**getContact**](docs/ContactControllerApi.md#getcontact) | **GET** /contacts/{contactId} | Get contact
*ContactControllerApi* | [**getContacts**](docs/ContactControllerApi.md#getcontacts) | **GET** /contacts | Get all contacts
*DomainControllerApi* | [**createDomain**](docs/DomainControllerApi.md#createdomain) | **POST** /domains | Create Domain
*DomainControllerApi* | [**deleteDomain**](docs/DomainControllerApi.md#deletedomain) | **DELETE** /domains/{id} | Delete a domain
*DomainControllerApi* | [**getDomain**](docs/DomainControllerApi.md#getdomain) | **GET** /domains/{id} | Get a domain
*DomainControllerApi* | [**getDomains**](docs/DomainControllerApi.md#getdomains) | **GET** /domains | Get domains
*EmailControllerApi* | [**deleteAllEmails**](docs/EmailControllerApi.md#deleteallemails) | **DELETE** /emails | Delete all emails
*EmailControllerApi* | [**deleteEmail**](docs/EmailControllerApi.md#deleteemail) | **DELETE** /emails/{emailId} | Delete an email
*EmailControllerApi* | [**downloadAttachment**](docs/EmailControllerApi.md#downloadattachment) | **GET** /emails/{emailId}/attachments/{attachmentId} | Get email attachment bytes
*EmailControllerApi* | [**forwardEmail**](docs/EmailControllerApi.md#forwardemail) | **POST** /emails/{emailId}/forward | Forward email
*EmailControllerApi* | [**getAttachmentMetaData**](docs/EmailControllerApi.md#getattachmentmetadata) | **GET** /emails/{emailId}/attachments/{attachmentId}/metadata | Get email attachment metadata
*EmailControllerApi* | [**getAttachments**](docs/EmailControllerApi.md#getattachments) | **GET** /emails/{emailId}/attachments | Get all email attachment metadata
*EmailControllerApi* | [**getEmail**](docs/EmailControllerApi.md#getemail) | **GET** /emails/{emailId} | Get email content
*EmailControllerApi* | [**getEmailHTML**](docs/EmailControllerApi.md#getemailhtml) | **GET** /emails/{emailId}/html | Get email content as HTML
*EmailControllerApi* | [**getEmailsPaginated**](docs/EmailControllerApi.md#getemailspaginated) | **GET** /emails | Get all emails
*EmailControllerApi* | [**getRawEmailContents**](docs/EmailControllerApi.md#getrawemailcontents) | **GET** /emails/{emailId}/raw | Get raw email string
*EmailControllerApi* | [**getRawEmailJson**](docs/EmailControllerApi.md#getrawemailjson) | **GET** /emails/{emailId}/raw/json | Get raw email in JSON
*EmailControllerApi* | [**getUnreadEmailCount**](docs/EmailControllerApi.md#getunreademailcount) | **GET** /emails/unreadCount | Get unread email count
*EmailControllerApi* | [**validateEmail**](docs/EmailControllerApi.md#validateemail) | **POST** /emails/{emailId}/validate | Validate email
*FormControllerApi* | [**submitForm**](docs/FormControllerApi.md#submitform) | **POST** /forms | Submit a form to be parsed and sent as an email to an address determined by the form fields
*GroupControllerApi* | [**addContactsToGroup**](docs/GroupControllerApi.md#addcontactstogroup) | **PUT** /groups/{groupId}/contacts | Add contacts to a group
*GroupControllerApi* | [**createGroup**](docs/GroupControllerApi.md#creategroup) | **POST** /groups | Create a group
*GroupControllerApi* | [**deleteGroup**](docs/GroupControllerApi.md#deletegroup) | **DELETE** /groups/{groupId} | Delete group
*GroupControllerApi* | [**getAllGroups**](docs/GroupControllerApi.md#getallgroups) | **GET** /groups/paginated | Get all Contact Groups in paginated format
*GroupControllerApi* | [**getGroup**](docs/GroupControllerApi.md#getgroup) | **GET** /groups/{groupId} | Get group
*GroupControllerApi* | [**getGroupWithContacts**](docs/GroupControllerApi.md#getgroupwithcontacts) | **GET** /groups/{groupId}/contacts | Get group and contacts belonging to it
*GroupControllerApi* | [**getGroups**](docs/GroupControllerApi.md#getgroups) | **GET** /groups | Get all groups
*GroupControllerApi* | [**removeContactsFromGroup**](docs/GroupControllerApi.md#removecontactsfromgroup) | **DELETE** /groups/{groupId}/contacts | Remove contacts from a group
*InboxControllerApi* | [**createInbox**](docs/InboxControllerApi.md#createinbox) | **POST** /inboxes | Create an Inbox (email address)
*InboxControllerApi* | [**deleteAllInboxes**](docs/InboxControllerApi.md#deleteallinboxes) | **DELETE** /inboxes | Delete all inboxes
*InboxControllerApi* | [**deleteInbox**](docs/InboxControllerApi.md#deleteinbox) | **DELETE** /inboxes/{inboxId} | Delete inbox
*InboxControllerApi* | [**getAllInboxes**](docs/InboxControllerApi.md#getallinboxes) | **GET** /inboxes/paginated | List Inboxes Paginated
*InboxControllerApi* | [**getEmails**](docs/InboxControllerApi.md#getemails) | **GET** /inboxes/{inboxId}/emails | Get emails in an Inbox
*InboxControllerApi* | [**getInbox**](docs/InboxControllerApi.md#getinbox) | **GET** /inboxes/{inboxId} | Get Inbox
*InboxControllerApi* | [**getInboxEmailsPaginated**](docs/InboxControllerApi.md#getinboxemailspaginated) | **GET** /inboxes/{inboxId}/emails/paginated | Get inbox emails paginated
*InboxControllerApi* | [**getInboxTags**](docs/InboxControllerApi.md#getinboxtags) | **GET** /inboxes/tags | Get inbox tags
*InboxControllerApi* | [**getInboxes**](docs/InboxControllerApi.md#getinboxes) | **GET** /inboxes | List Inboxes / Email Addresses
*InboxControllerApi* | [**sendEmail**](docs/InboxControllerApi.md#sendemail) | **POST** /inboxes/{inboxId} | Send Email
*InboxControllerApi* | [**setInboxFavourited**](docs/InboxControllerApi.md#setinboxfavourited) | **PUT** /inboxes/{inboxId}/favourite | Set inbox favourited state
*InboxControllerApi* | [**updateInbox**](docs/InboxControllerApi.md#updateinbox) | **PATCH** /inboxes/{inboxId} | Update Inbox
*TemplateControllerApi* | [**createTemplate**](docs/TemplateControllerApi.md#createtemplate) | **POST** /templates | Create a Template
*TemplateControllerApi* | [**deleteTemplate**](docs/TemplateControllerApi.md#deletetemplate) | **DELETE** /templates/{TemplateId} | Delete Template
*TemplateControllerApi* | [**getAllTemplates**](docs/TemplateControllerApi.md#getalltemplates) | **GET** /templates/paginated | Get all Templates in paginated format
*TemplateControllerApi* | [**getTemplate**](docs/TemplateControllerApi.md#gettemplate) | **GET** /templates/{TemplateId} | Get Template
*TemplateControllerApi* | [**getTemplates**](docs/TemplateControllerApi.md#gettemplates) | **GET** /templates | Get all Templates
*WaitForControllerApi* | [**waitFor**](docs/WaitForControllerApi.md#waitfor) | **POST** /waitFor | Wait for conditions to be met
*WaitForControllerApi* | [**waitForEmailCount**](docs/WaitForControllerApi.md#waitforemailcount) | **GET** /waitForEmailCount | Wait for and return count number of emails
*WaitForControllerApi* | [**waitForLatestEmail**](docs/WaitForControllerApi.md#waitforlatestemail) | **GET** /waitForLatestEmail | Fetch inbox&#39;s latest email or if empty wait for an email to arrive
*WaitForControllerApi* | [**waitForMatchingEmail**](docs/WaitForControllerApi.md#waitformatchingemail) | **POST** /waitForMatchingEmails | Wait or return list of emails that match simple matching patterns
*WaitForControllerApi* | [**waitForNthEmail**](docs/WaitForControllerApi.md#waitfornthemail) | **GET** /waitForNthEmail | Wait for or fetch the email with a given index in the inbox specified
*WebhookControllerApi* | [**createWebhook**](docs/WebhookControllerApi.md#createwebhook) | **POST** /inboxes/{inboxId}/webhooks | Attach a WebHook URL to an inbox
*WebhookControllerApi* | [**deleteWebhook**](docs/WebhookControllerApi.md#deletewebhook) | **DELETE** /inboxes/{inboxId}/webhooks/{webhookId} | Delete and disable a Webhook for an Inbox
*WebhookControllerApi* | [**getAllWebhooks**](docs/WebhookControllerApi.md#getallwebhooks) | **GET** /webhooks/paginated | List Webhooks Paginated
*WebhookControllerApi* | [**getWebhook**](docs/WebhookControllerApi.md#getwebhook) | **GET** /webhooks/{webhookId} | Get a webhook for an Inbox
*WebhookControllerApi* | [**getWebhooks**](docs/WebhookControllerApi.md#getwebhooks) | **GET** /inboxes/{inboxId}/webhooks | Get all Webhooks for an Inbox
*WebhookControllerApi* | [**sendTestData**](docs/WebhookControllerApi.md#sendtestdata) | **POST** /webhooks/{webhookId}/test | Send webhook test data


## Documentation For Models

 - [Alias](docs/Alias.md)
 - [AttachmentMetaData](docs/AttachmentMetaData.md)
 - [BasicAuthOptions](docs/BasicAuthOptions.md)
 - [BulkSendEmailOptions](docs/BulkSendEmailOptions.md)
 - [ContactDto](docs/ContactDto.md)
 - [ContactProjection](docs/ContactProjection.md)
 - [CreateAnonymousAliasOptions](docs/CreateAnonymousAliasOptions.md)
 - [CreateContactOptions](docs/CreateContactOptions.md)
 - [CreateDomainOptions](docs/CreateDomainOptions.md)
 - [CreateGroupOptions](docs/CreateGroupOptions.md)
 - [CreateOwnedAliasOptions](docs/CreateOwnedAliasOptions.md)
 - [CreateTemplateOptions](docs/CreateTemplateOptions.md)
 - [CreateWebhookOptions](docs/CreateWebhookOptions.md)
 - [DomainDto](docs/DomainDto.md)
 - [DomainPreview](docs/DomainPreview.md)
 - [Email](docs/Email.md)
 - [EmailAnalysis](docs/EmailAnalysis.md)
 - [EmailPreview](docs/EmailPreview.md)
 - [EmailProjection](docs/EmailProjection.md)
 - [ForwardEmailOptions](docs/ForwardEmailOptions.md)
 - [GroupContactsDto](docs/GroupContactsDto.md)
 - [GroupDto](docs/GroupDto.md)
 - [GroupProjection](docs/GroupProjection.md)
 - [HTMLValidationResult](docs/HTMLValidationResult.md)
 - [Inbox](docs/Inbox.md)
 - [InboxProjection](docs/InboxProjection.md)
 - [JsonNode](docs/JsonNode.md)
 - [MatchOption](docs/MatchOption.md)
 - [MatchOptions](docs/MatchOptions.md)
 - [Pageable](docs/Pageable.md)
 - [Page«Alias»](docs/Page«Alias».md)
 - [Page«ContactProjection»](docs/Page«ContactProjection».md)
 - [Page«EmailPreview»](docs/Page«EmailPreview».md)
 - [Page«EmailProjection»](docs/Page«EmailProjection».md)
 - [Page«GroupProjection»](docs/Page«GroupProjection».md)
 - [Page«InboxProjection»](docs/Page«InboxProjection».md)
 - [Page«TemplateProjection»](docs/Page«TemplateProjection».md)
 - [Page«WebhookProjection»](docs/Page«WebhookProjection».md)
 - [RawEmailJson](docs/RawEmailJson.md)
 - [SendEmailOptions](docs/SendEmailOptions.md)
 - [SetInboxFavouritedOptions](docs/SetInboxFavouritedOptions.md)
 - [SimpleSendEmailOptions](docs/SimpleSendEmailOptions.md)
 - [Sort](docs/Sort.md)
 - [TemplateDto](docs/TemplateDto.md)
 - [TemplateProjection](docs/TemplateProjection.md)
 - [TemplateVariable](docs/TemplateVariable.md)
 - [UnreadCount](docs/UnreadCount.md)
 - [UpdateGroupContacts](docs/UpdateGroupContacts.md)
 - [UpdateInboxOptions](docs/UpdateInboxOptions.md)
 - [UploadAttachmentOptions](docs/UploadAttachmentOptions.md)
 - [ValidationDto](docs/ValidationDto.md)
 - [ValidationMessage](docs/ValidationMessage.md)
 - [WaitForConditions](docs/WaitForConditions.md)
 - [WebhookDto](docs/WebhookDto.md)
 - [WebhookProjection](docs/WebhookProjection.md)
 - [WebhookTestRequest](docs/WebhookTestRequest.md)
 - [WebhookTestResponse](docs/WebhookTestResponse.md)
 - [WebhookTestResult](docs/WebhookTestResult.md)


## Documentation For Authorization


## API_KEY


- **Type**: API key
- **API key parameter name**: x-api-key
- **Location**: HTTP header

