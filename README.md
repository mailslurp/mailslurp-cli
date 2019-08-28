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
*CommonOperationsApi* | [**createNewEmailAddress**](docs/CommonOperationsApi.md#createnewemailaddress) | **POST** /newEmailAddress | Create new email address
*CommonOperationsApi* | [**sendEmailSimple**](docs/CommonOperationsApi.md#sendemailsimple) | **POST** /sendEmail | Send an email from a random email address
*CommonOperationsApi* | [**waitForLatestEmail**](docs/CommonOperationsApi.md#waitforlatestemail) | **GET** /fetchLatestEmail | Fetch inbox&#39;s latest email or if empty wait for email to arrive
*CommonOperationsApi* | [**waitForNthEmail**](docs/CommonOperationsApi.md#waitfornthemail) | **GET** /waitForNthEmail | Wait for or fetch the email with a given index in the inbox specified
*ExtraOperationsApi* | [**bulkCreateInboxes**](docs/ExtraOperationsApi.md#bulkcreateinboxes) | **POST** /bulk/inboxes | Bulk create Inboxes (email addresses)
*ExtraOperationsApi* | [**bulkDeleteInboxes**](docs/ExtraOperationsApi.md#bulkdeleteinboxes) | **DELETE** /bulk/inboxes | Bulk Delete Inboxes
*ExtraOperationsApi* | [**bulkSendEmails**](docs/ExtraOperationsApi.md#bulksendemails) | **POST** /bulk/send | Bulk Send Emails
*ExtraOperationsApi* | [**createInbox**](docs/ExtraOperationsApi.md#createinbox) | **POST** /inboxes | Create an Inbox (email address)
*ExtraOperationsApi* | [**createWebhook**](docs/ExtraOperationsApi.md#createwebhook) | **POST** /inboxes/{inboxId}/webhooks | Attach a WebHook URL to an inbox
*ExtraOperationsApi* | [**deleteEmail**](docs/ExtraOperationsApi.md#deleteemail) | **DELETE** /emails/{emailId} | Delete Email
*ExtraOperationsApi* | [**deleteInbox**](docs/ExtraOperationsApi.md#deleteinbox) | **DELETE** /inboxes/{inboxId} | Delete Inbox / Email Address
*ExtraOperationsApi* | [**deleteWebhook**](docs/ExtraOperationsApi.md#deletewebhook) | **DELETE** /inboxes/{inboxId}/webhooks/{webhookId} | Delete and disable a WebHook for an Inbox
*ExtraOperationsApi* | [**downloadAttachment**](docs/ExtraOperationsApi.md#downloadattachment) | **GET** /emails/{emailId}/attachments/{attachmentId} | Get email attachment
*ExtraOperationsApi* | [**getEmail**](docs/ExtraOperationsApi.md#getemail) | **GET** /emails/{emailId} | Get Email Content
*ExtraOperationsApi* | [**getEmails**](docs/ExtraOperationsApi.md#getemails) | **GET** /inboxes/{inboxId}/emails | List Emails in an Inbox / EmailAddress
*ExtraOperationsApi* | [**getInbox**](docs/ExtraOperationsApi.md#getinbox) | **GET** /inboxes/{inboxId} | Get Inbox / EmailAddress
*ExtraOperationsApi* | [**getInboxes**](docs/ExtraOperationsApi.md#getinboxes) | **GET** /inboxes | List Inboxes / Email Addresses
*ExtraOperationsApi* | [**getRawEmailContents**](docs/ExtraOperationsApi.md#getrawemailcontents) | **GET** /emails/{emailId}/raw | Get Raw Email Content
*ExtraOperationsApi* | [**getWebhooks**](docs/ExtraOperationsApi.md#getwebhooks) | **GET** /inboxes/{inboxId}/webhooks | Get all WebHooks for an Inbox
*ExtraOperationsApi* | [**sendEmail**](docs/ExtraOperationsApi.md#sendemail) | **POST** /inboxes/{inboxId} | Send Email


## Documentation For Models

 - [BasicAuthOptions](docs/BasicAuthOptions.md)
 - [BulkSendEmailOptions](docs/BulkSendEmailOptions.md)
 - [CreateWebhookOptions](docs/CreateWebhookOptions.md)
 - [Email](docs/Email.md)
 - [EmailAnalysis](docs/EmailAnalysis.md)
 - [EmailPreview](docs/EmailPreview.md)
 - [Inbox](docs/Inbox.md)
 - [SendEmailOptions](docs/SendEmailOptions.md)
 - [Webhook](docs/Webhook.md)


## Documentation For Authorization


## API_KEY

- **Type**: API key
- **API key parameter name**: x-api-key
- **Location**: HTTP header

