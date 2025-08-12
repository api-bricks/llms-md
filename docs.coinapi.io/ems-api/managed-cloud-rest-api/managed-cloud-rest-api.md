Managed Cloud REST API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)

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

  + [Introduction](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
  + [Account](/ems-api/managed-cloud-rest-api/account)
  + [Exchange](/ems-api/managed-cloud-rest-api/exchange)
  + [Location](/ems-api/managed-cloud-rest-api/location)
  + [Endpoints](/ems-api/managed-cloud-rest-api/endpoints)
  + [Certificate](/ems-api/managed-cloud-rest-api/certificate)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)

  + [Introduction](/ems-api/rest-api/rest-api)
  + [Orders](/ems-api/rest-api/orders)
  + [Balances](/ems-api/rest-api/balances)
  + [Positions](/ems-api/rest-api/positions)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* Introduction

On this page

Version: v1

Managed Cloud REST API
======================

This section will provide necessary information about the `CoinAPI EMS Managed Cloud REST API` protocol.
This API is used to manage the overall deployment of **Execution Management System API** (`EMS API`) software,
which means that in this API, you define the accounts, credentials, and configurations for the order destinations or identify the CoinAPI endpoints where you need to connect to access the `EMS API`.
Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)

### Endpoints[​](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#endpoints "Direct link to Endpoints")

| Environment | Url |
| --- | --- |
| Production | `https://ems-mgmt.coinapi.io/` |

### Authentication[​](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#authentication "Direct link to Authentication")

To use resources that require authorized access, you will need to provide an API key to us when making HTTP requests.

There are 2 methods for passing the API key to us, you only need to use one:

1. Custom authorization header named `X-CoinAPI-Key`
2. Query string parameter named `apikey`

#### Custom authorization header[​](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#custom-authorization-header "Direct link to Custom authorization header")

You can authorize by providing additional custom header named `X-CoinAPI-Key` and API key as its value.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authorization header you should send to us will look like: `X-CoinAPI-Key: 73034021-THIS-IS-SAMPLE-KEY`

tip

This method is recommended by us and you should use it in production environments.

#### Query string authorization parameter[​](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#query-string-authorization-parameter "Direct link to Query string authorization parameter")

You can authorize by providing an additional parameter named `apikey` with a value equal to your API key in the query string of your HTTP request.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY` and that you want to request all accounts, then your query string should look like this: `GET /v1/accounts?apikey=73034021-THIS-IS-SAMPLE-KEY`

info

Query string method may be more practical for development activities.

Authentication[​](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#authentication "Direct link to Authentication")
------------------------------------------------------------------------------------------------------------------------

* API Key: APIKeyHeader
* API Key: APIKeyQueryParam

|  |  |
| --- | --- |
| Security Scheme Type: | apiKey |
| Header parameter name: | X-CoinAPI-Key |

|  |  |
| --- | --- |
| Security Scheme Type: | apiKey |
| Header parameter name: | apikey |

### Contact

COINAPI LTD: [[email protected]](/cdn-cgi/l/email-protection#e695939696899492a685898f8887968fc88f89)

URL: [https://www.coinapi.io](/cdn-cgi/l/email-protection#472f333337347d68683030306924282e2926372e692e28)

### Terms of Service

[<https://www.coinapi.io/legal>](https://www.coinapi.io/legal)

### License

[37284](https://github.com/api-bricks/api-bricks-sdk/blob/master/LICENSE)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/ems-api/rest-api/rest-api)[Next

Account](/ems-api/managed-cloud-rest-api/account)

* [Endpoints](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#endpoints)
* [Authentication](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.