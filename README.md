# Coinkite API Code for Javascript / Node.js

[Learn more about Coinkite's API here](https://docs.coinkite.com/)
and visit the [Coinkite Main Site](https://coinkite.com/) to open your
account today!

## Introduction

Every request made to the Coinkite API requires three special header
lines. This code can generate the timestamp and signature values that
you will need.

Example header lines:

	X-CK-Key: K5555a555-55a555aa-a55aa5a5555aaa5a
	X-CK-Timestamp: 2014-06-23T03:10:04.905376
	X-CK-Sign: 0aa7755aaa45189a98a5a8a887a564aa55aa5aa4aa7a98aa2858aaa60a5a56aa


## Requirements

For use under `node`, you will need the `crypto` module. It's quite standard and
you probably already have it.

For use with Javascript on the browser side, you will need the
HMAC-SHA256 code from [CryptoJS](http://crypto-js.googlecode.com).
Before you do that however, think long and hard why the browser should
have any access to your Coinkite account.

The keys you need can be created on
[Coinkite.com under Merchant / API]([https://coinkite.com/merchant/api).


## How to Use: Node

````javascript
	CK_API = require('./coinkite-api.js')
	console.log("Example:\n", CK_API.auth_headers('aa', 'bb', 'cc'))
````

## How to Use: Javascript

In the `HEAD` of your HTML, include the javascript libary from:

	https://cdnjs.cloudflare.com/ajax/libs/crypto-js/3.1.2/rollups/hmac-sha256.js

And the `coinkite-api.js` file after that.

Then, make sure that all your HTTP calls to Coinkite's API have the extra
headers supplied from `auth_headers`. You need to use a hook in jQuery or
whatever library you are using to do your REST calls.

A more complete example can be found in our 
[Angular Coinkite API example](https://github.com/coinkite/coinkite-angular)
which uses this code.


## More about Coinkite

Coinkite is the world's easiest and most powerful web wallet for
safely holding all your cryptocurrencies, including Bitcoin and Litecoin.

[Learn more about all we offer](https://coinkite.com/)


