Authentication | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/authentication)

* [Market Data](/market-data/)
* [Exchange Rates](/exchange-rates-api/)
* [EMS](/ems-api/)
* [Indexes](/indexes-api/)
* [Flat Files](/flat-files-api/)
* [NAAS](/naas-api/)

[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.coinapi.io)

Search

[Get a free API Key](https://console.coinapi.io/?link=/apikeys/create)

* [EMS API](/ems-api/)
* [Authentication](/ems-api/authentication)
* [API limits and billing](/ems-api/api-limits-and-billing-metrics)
* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* Authentication

On this page

Authentication
==============

In this section, you will find comprehensive information about the process of CoinAPI authentication.
It covers the fundamental aspects and procedures involved in obtaining authentication for CoinAPI usage.
Whether you are new to CoinAPI or seeking to enhance your understanding of the authentication process, this section will provide you with a valuable overview of the topic.

There are different types of authentication methods available to secure and control access to its services.

* `API Key` - fundamental method of authentication that involves the usage of an API key for authentication and access control.
* `API Key + JWT token` - extended authentication method that combines the use of an API key along with a JWT token for enhanced security and authentication.
  Useful when you need to share the API Key publicly, for example when accessing the CoinAPI endpoints from the frontend JavaScript code exposed to the end-users.
  JWT token will be required along the API Key from the CoinAPI side to perform successful authentication, and the JWT tokens can be only generated from your side as you know the secret (private key or secret) based on which JWT token with the specified expiration time are issued.

Authentication methods supported by the API[​](/ems-api/authentication#authentication-methods-supported-by-the-api "Direct link to Authentication methods supported by the API")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Here's an overview of the various products offered by CoinAPI and the supported authentication methods for each product.
To use resources that require authorized access, you will need to use one of the many authentication methods described below.

| Product name | API | X-CoinAPI-Key header | Query param | TLS Client Cert | SenderCompID |
| --- | --- | --- | --- | --- | --- |
| `EMS` | `Managed Cloud REST` | ✅ | ✅ | ❌ | ❌ |
| `EMS` | `REST` | ✅ | ✅ | ✅ | ❌ |
| `EMS` | `WS` | ✅ | ✅ | ✅ | ❌ |
| `EMS` | `FIX` | ❌ | ❌ | ✅ | ✅ |

caution

If you are using the Authorization header to pass the API key, please note that it cannot be used together with a JWT token. In case you have enabled JWT authentication, we recommend using alternative methods to pass the API key such as: a Custom authentication header, Query string parameter, or API Key in the URL.

### X-CoinAPI-Key header[​](/ems-api/authentication#x-coinapi-key-header "Direct link to X-CoinAPI-Key header")

You can authorize by providing an additional custom header named `X-CoinAPI-Key` and API key as its value.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authentication header you should send to us will look like:

`X-CoinAPI-Key: 73034021-THIS-IS-SAMPLE-KEY`

### Query string parameter (apikey)[​](/ems-api/authentication#query-string-parameter-apikey "Direct link to Query string parameter (apikey)")

You can authorize by providing an additional parameter named `apikey` with a value equal to your API key in the query string of your HTTP request.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY` and that you want to request all exchange rates from `BTC` asset, then your query string should look like this: `GET /v1/exchangerate/BTC?apikey=73034021-THIS-IS-SAMPLE-KEY`

caution

The Query string method may be more practical for development activities.

### TLS Client Cert[​](/ems-api/authentication#tls-client-cert "Direct link to TLS Client Cert")

TLS Client Certificate acquired from the `Managed Cloud REST API` (/v1/certificate/pem endpoint) provided while establishing a TLS session with us.

### SenderCompID[​](/ems-api/authentication#sendercompid "Direct link to SenderCompID")

This method of authentication is FIX protocol-specific. The exact message that needs to be sent to us will be described in the documentation of the specific API protocol Logon (35=A) message page.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

EMS API](/ems-api/)[Next

API limits and billing](/ems-api/api-limits-and-billing-metrics)

* [Authentication methods supported by the API](/ems-api/authentication#authentication-methods-supported-by-the-api)
  + [X-CoinAPI-Key header](/ems-api/authentication#x-coinapi-key-header)
  + [Query string parameter (apikey)](/ems-api/authentication#query-string-parameter-apikey)
  + [TLS Client Cert](/ems-api/authentication#tls-client-cert)
  + [SenderCompID](/ems-api/authentication#sendercompid)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.