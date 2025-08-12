REST API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/rest-api)

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

* Managed Cloud REST API

On this page

Version: v1

REST API
========

This section will provide necessary information about the `CoinAPI EMS REST API` protocol.
This API is also available in the Postman application: [<https://postman.coinapi.io/>](https://postman.coinapi.io/)

Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)

### Endpoints[​](/ems-api/rest-api/rest-api#endpoints "Direct link to Endpoints")

| Deployment method | Environment | Url |
| --- | --- | --- |
| Managed Cloud | Production | Use [Managed Cloud REST API /v1/locations](#ems-docs-sh) to get specific endpoints to each server site where your deployments span |
| Self Hosted | Production | IP Address of the `ems-gateway` container/excecutable in the closest server site to the caller location |

### Authentication[​](/ems-api/rest-api/rest-api#authentication "Direct link to Authentication")

If the software is deployed as `Self-Hosted` then API do not require authentication as inside your infrastructure, your company is responsible for the security and access controls.
If the software is deployed in our `Managed Cloud`, there are 2 methods for authenticating with us, you only need to use one:

1. Custom authorization header named `X-CoinAPI-Key` with the API Key
2. Query string parameter named `apikey` with the API Key
3. [TLS Client Certificate](#certificate) from the `Managed Cloud REST API` (/v1/certificate/pem endpoint) while establishing a TLS session with us.

#### Custom authorization header[​](/ems-api/rest-api/rest-api#custom-authorization-header "Direct link to Custom authorization header")

You can authorize by providing additional custom header named `X-CoinAPI-Key` and API key as its value.
Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authorization header you should send to us will look like: `X-CoinAPI-Key: 73034021-THIS-IS-SAMPLE-KEY`

tip

This method is recommended by us and you should use it in production environments.

#### Query string authorization parameter[​](/ems-api/rest-api/rest-api#query-string-authorization-parameter "Direct link to Query string authorization parameter")

You can authorize by providing an additional parameter named `apikey` with a value equal to your API key in the query string of your HTTP request.
Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY` and that you want to request all balances, then your query string should look like this: `GET /v1/balances?apikey=73034021-THIS-IS-SAMPLE-KEY`

info

Query string method may be more practical for development activities.

### Contact

COINAPI LTD: [[email protected]](/cdn-cgi/l/email-protection#52212722223d202612313d3b3c33223b7c3b3d)

URL: [https://www.coinapi.io](/cdn-cgi/l/email-protection#0a627e7e7a793025257d7d7d24696563646b7a63246365)

### Terms of Service

[<https://www.coinapi.io/legal>](https://www.coinapi.io/legal)

### License

[28961](https://github.com/api-bricks/api-bricks-sdk/blob/master/LICENSE)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

API limits and billing](/ems-api/api-limits-and-billing-metrics)[Next

Introduction](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)

* [Endpoints](/ems-api/rest-api/rest-api#endpoints)
* [Authentication](/ems-api/rest-api/rest-api#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.