Authentication | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/authentication)

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

* [Market Data API](/market-data/)
* [Authentication](/market-data/authentication)
* [API limits and billing](/market-data/api-limits-and-billing-metrics)
* [Metadata Tables](/market-data/metadata-tables/introduction)
* [REST API](/market-data/rest-api/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

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

Authentication methods supported by the API[​](/market-data/authentication#authentication-methods-supported-by-the-api "Direct link to Authentication methods supported by the API")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Here's an overview of the various products offered by CoinAPI and the supported authentication methods for each product.
To use resources that require authorized access, you will need to use one of the many authentication methods described below.

| API Product | X-CoinAPI-Key header | Query param | URL path | Authorization header | Basic auth | JWT | SenderCompID | AWS Signature Version 2/4 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `REST` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `WS V1` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `WS DS` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `FIX` | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| `S3` | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |

caution

If you are using the Authorization header to pass the API key, please note that it cannot be used together with a JWT token. In case you have enabled JWT authentication, we recommend using alternative methods to pass the API key such as: a Custom authentication header, Query string parameter, or API Key in the URL.

### X-CoinAPI-Key header[​](/market-data/authentication#x-coinapi-key-header "Direct link to X-CoinAPI-Key header")

You can authorize by providing an additional custom header named `X-CoinAPI-Key` and API key as its value.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authentication header you should send to us will look like:

`X-CoinAPI-Key: 73034021-THIS-IS-SAMPLE-KEY`

### Query string parameter (apikey)[​](/market-data/authentication#query-string-parameter-apikey "Direct link to Query string parameter (apikey)")

You can authorize by providing an additional parameter named `apikey` with a value equal to your API key in the query string of your HTTP request.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY` and that you want to request all exchange rates from `BTC` asset, then your query string should look like this: `GET /v1/exchangerate/BTC?apikey=73034021-THIS-IS-SAMPLE-KEY`

caution

The Query string method may be more practical for development activities.

### URL path[​](/market-data/authentication#url-path "Direct link to URL path")

To ensure proper authentication when passing the API key in the URL, it is important to format it correctly.
The real API key should always be preceded by the `APIKEY-` prefix, followed by the actual API key.
For example, if your API key is `73034021-THIS-IS-SAMPLE-KEY`, the URL should be structured as `/APIKEY-73034021-THIS-IS-SAMPLE-KEY`.

The API key can be placed end of the URL path. Note that the key is completely ignored when determining the path of the requested resource. Here are examples of the different placements:

* `/v1/exchanges/APIKEY-73034021-THIS-IS-SAMPLE-KEY`
* `/APIKEY-73034021-THIS-IS-SAMPLE-KEY`

Please make sure to replace `73034021-THIS-IS-SAMPLE-KEY` with your actual API key for authentication and access to the requested resources and remember to include the `APIKEY-` prefix before your real API key.

### Authorization header[​](/market-data/authentication#authorization-header "Direct link to Authorization header")

This method involves including the API key directly in the Authorization header of the API request.

`Authorization: 73034021-THIS-IS-SAMPLE-KEY`

### Basic auth[​](/market-data/authentication#basic-auth "Direct link to Basic auth")

Use Basic Authentication by setting the Authorization header with a base64 encoded string that combines your API key with a username (coinapi):

`Authorization: Basic Y29pbmFwaTo3MzAzNDAyMS1USElTLUlTLVNBTVBMRS1LRVk=`

In this example, `Y29pbmFwaTo3MzAzNDAyMS1USElTLUlTLVNBTVBMRS1LRVk` is a base64 encoded string of the username and API key (coinapi:73034021-THIS-IS-SAMPLE-KEY).

### JWT token[​](/market-data/authentication#jwt-token "Direct link to JWT token")

The JWT authentication method provides a secure and efficient way to authorize requests using JSON Web Tokens (JWT).
With this method, JWTs can be passed via the Authorization header in the `Bearer JWT_TOKEN` format.

#### Supported JWT Algorithms[​](/market-data/authentication#supported-jwt-algorithms "Direct link to Supported JWT Algorithms")

The JWT authentication method supports the following algorithms for JWT token verification with various key sizes:

* `RSASSA-PSS (e.g. PS256)`
* `RSASSA-PKCS1-v1_5 (e.g. RS256)`
* `ECDSA (e.g. ES256)`
* `HMAC (e.g. HS256)`

#### Enabling JWT authentication[​](/market-data/authentication#enabling-jwt-authentication "Direct link to Enabling JWT authentication")

To enable JWT authentication for your API key:

1. Access the customer portal and import the public JWT key (RSA or ECDSA) for the API key.
2. Generate a JWT token using your private key (it ensures the authenticity and integrity of the token)
3. Include the generated JWT token in the `Authorization` header of your API requests using `Bearer JWT_TOKEN` format.
4. Let the CoinAPI server verify the token's authenticity using the corresponding public key you've imported in Step 1 during the API request.

#### Example request with JWT authentication[​](/market-data/authentication#example-request-with-jwt-authentication "Direct link to Example request with JWT authentication")

To include a JWT in an API request, add the token to the `Authorization` header using the Bearer scheme. The format of the header is as follows:

`Authorization: Bearer JWT_TOKEN`

Example request header with JWT token generated using RS256 algorithm:

```
Authorization: Bearer eyJraWQiOiI5ODViMmQ0ZC1kMjE1LTQwN2MtODcxNi01NTIzNjA0YmM0ZTIiLCJhbGciOiJSUzI1NiJ9.ew0KICAic3ViIjogIjEyMzQ1Njc4OTAiLA0KICAibmFtZSI6ICJFWEFNUExFIFRPS0VOIiwNCiAgImlhdCI6IDE1MTYyMzkwMjIsDQogICJuYmYiOiAxNjg2MTM3MDI0LA0KICAiZXhwIjogMTcxNzY3MzAyNA0KfQ.CX6MWRSXQPKuQ_jrFCME91IwZhK8lq_2XrbDOyZ4-tPo0Ro52HA289sIfLo2LNafWQlq2lClfCN55TxyfC8n0xiifUwdec7g3kcGjCri6vTxaa8p6S3Fyyt2DxXccpi3Se4d_3mEQBZwMchKbQsw-W7Wj7njUk31ycgPQovvF4WrTuEYmhYw1sO9jCTORHmsSO7Shml7kv7AxlIUmzB2oq2KSmBhJV38Nz9oYj3KlPoMjgaIl4xYldNqnGyshh6fQyUQ1gQMQV6e4M5ro8YthjPOCvAT8yk77dTyOoE6Im58cAp6KtM-Gko-tWppUQTu-0M82LOvD_duP77n-hcoTw
```

Decoded JWT token header:

```
{ "kid": "985b2d4d-d215-407c-8716-5523604bc4e2", "alg": "RS256" }
```

Decoded JWT token payload:

```
{  
  "sub": "1234567890",  
  "name": "EXAMPLE TOKEN",  
  "iat": 1516239022,  
  "nbf": 1686137024,  
  "exp": 1717673024  
}
```

#### JWT Token expiration[​](/market-data/authentication#jwt-token-expiration "Direct link to JWT Token expiration")

To ensure the validity of JWT tokens and prevent the use of expired tokens, the inclusion of the following claims is required:

* `NBF (Not Before)`

  + The "nbf" claim specifies the earliest time at which the token can be considered valid. Tokens with a "nbf" claim set in the future should not be accepted.
* `EXP (Expiration Time)`

  + The "exp" claim defines the expiration time of the token. Tokens with an "exp" claim set in the past should not be accepted.

#### Request authentication[​](/market-data/authentication#request-authentication "Direct link to Request authentication")

During the process of request authentication, the CoinAPI server follows a series of steps to ensure secure access to its resources.
Here's an overview of the authentication process:

1. Upon receiving the request, the CoinAPI server extracts the JWT from the `Authorization` header.
2. Then, it verifies the JWT signature and checks the "NBF" and "EXP" claims to ensure token validity and expiration.
3. If the JWT is valid and not expired, the server authorizes the request and proceeds with the necessary processing to access CoinAPI resources.
4. If the JWT is invalid or expired, the server returns an appropriate error response.

### SenderCompID[​](/market-data/authentication#sendercompid "Direct link to SenderCompID")

This method of authentication is FIX protocol-specific. The exact message that needs to be sent to us will be described in the documentation of the specific API protocol Logon (35=A) message page.

### AWS Signature Version 2[​](/market-data/authentication#aws-signature-version-2 "Direct link to AWS Signature Version 2")

Please in this method of authorization put the API Key in the `Access Key ID` and `Secret Access Key` fields.

### AWS Signature Version 4[​](/market-data/authentication#aws-signature-version-4 "Direct link to AWS Signature Version 4")

AMAZON S3 uses the `Authorization` request header to provide authorization information. The value for this header must follow a specific pattern described as [AWS Signature Version 4](https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-auth-using-authorization-header.html).

The example below shows the Authorization header value compliant with AWS Signature Version 4.

Please note that the Credential string contains our `apikey` as access-key-id.
Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authorization header you should send to us will look like:

`Authentication: AWS4-HMAC-SHA256 Credential=73034021-THIS-IS-SAMPLE-KEY/20211203/us-east-1/s3/aws4_request, SignedHeaders=host; Signature=65e655c69da9906ac6076a28f75d9e4947aaed3be1f419757a3a84e24662673d`

Although AWS Signature Version 4 is very strict about each of the signature components, our API takes only our `apikey` value into account.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Market Data API](/market-data/)[Next

API limits and billing](/market-data/api-limits-and-billing-metrics)

* [Authentication methods supported by the API](/market-data/authentication#authentication-methods-supported-by-the-api)
  + [X-CoinAPI-Key header](/market-data/authentication#x-coinapi-key-header)
  + [Query string parameter (apikey)](/market-data/authentication#query-string-parameter-apikey)
  + [URL path](/market-data/authentication#url-path)
  + [Authorization header](/market-data/authentication#authorization-header)
  + [Basic auth](/market-data/authentication#basic-auth)
  + [JWT token](/market-data/authentication#jwt-token)
  + [SenderCompID](/market-data/authentication#sendercompid)
  + [AWS Signature Version 2](/market-data/authentication#aws-signature-version-2)
  + [AWS Signature Version 4](/market-data/authentication#aws-signature-version-4)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.