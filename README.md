# TwitterUserIdLookup

Looks up the user ID of a single Twitter user based on their username via HTTP.

## Setup

[Composer](https://getcomposer.org/) is recommended to download the required dependencies.

A file named `twitter_tokens.php` should be created and placed in the same directory as `lookup_twitter_user_id.php` containing the following variables:
* `$consumer_key`
* `$consumer_secret`
* `$access_token`
* `$access_token_secret`

These values can be found at <https://apps.twitter.com/> after registering your application.

## Request

The request is a standard HTTP request to `lookup_twitter_user_id.php` with a single GET parameter named `username`.

## Response

The response will be sent in JSON format. If successful, the response will be a single name/value pair named `id` with the user ID as a long. For example, for the user TwitterDev, this is the response:

`{"id":2244994945}`

If the ID was not able to be found, it will instead respond with a single name/value pair with the name `error` with one of the following strings:

* "User not found"
* "User is suspended"
* "Error validating username"