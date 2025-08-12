WebSocket API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/websocket/)

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

  + [Introduction](/ems-api/websocket/)
  + [Messages](/ems-api/websocket/messages)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* WebSocket API

On this page

WebSocket API
=============

This section will provide necessary information about the `CoinAPI EMS WebSocket API` protocol.

WebSocket API provides real-time communication capacity for order management, execution reports, balances and the positions.

Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)
* [WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)

caution

Your WebSocket client implementation must comply with the "v13" version of the protocol documented in the [RFC6455](http://www.ietf.org/rfc/rfc6455.txt), including responding with the "Pong" message each time we will send "Ping" (every minute), failure to respond with the "Pong" from your WebSocket client will cause a connection to be closed.

Endpoints[​](/ems-api/websocket/#endpoints "Direct link to Endpoints")
----------------------------------------------------------------------

| Deployment method | Environment | Url |
| --- | --- | --- |
| Managed Cloud | Production | Use [Managed Cloud REST API /v1/locations](#ems-docs-sh) to get specific endpoints to each server site where your deployments span |

Authentication[​](/ems-api/websocket/#authentication "Direct link to Authentication")
-------------------------------------------------------------------------------------

API authentication is required for our `Managed Cloud` deployment. There are 2 methods for authenticating with us, you only need to use one:

1. Custom authorization header named `X-CoinAPI-Key` with the API Key
2. Query string parameter named `apikey` with the API Key
3. [TLS Client Certificate](#certificate) from the `Managed Cloud REST API` (/v1/certificate/pem endpoint) while establishing a TLS session with us.

### Custom authorization header[​](/ems-api/websocket/#custom-authorization-header "Direct link to Custom authorization header")

You can authorize by providing additional custom header named `X-CoinAPI-Key` and API key as its value.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authorization header you should send to us will look like: `X-CoinAPI-Key: 73034021-THIS-IS-SAMPLE-KEY`

tip

This method is recommended by us and you should use it in production environments.

### Query string authorization parameter[​](/ems-api/websocket/#query-string-authorization-parameter "Direct link to Query string authorization parameter")

You can authorize by providing an additional parameter named `apikey` with a value equal to your API key in the query string of your HTTP request.

Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY` and that you want to request all exchange rates from `BTC` asset, then your query string should look like this: `GET /v1/exchangerate/BTC?apikey=73034021-THIS-IS-SAMPLE-KEY`

info

Query string method may be more practical for development activities.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Get open positions](/ems-api/rest-api/get-open-positions)[Next

Introduction](/ems-api/websocket/)

* [Endpoints](/ems-api/websocket/#endpoints)
* [Authentication](/ems-api/websocket/#authentication)
  + [Custom authorization header](/ems-api/websocket/#custom-authorization-header)
  + [Query string authorization parameter](/ems-api/websocket/#query-string-authorization-parameter)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.