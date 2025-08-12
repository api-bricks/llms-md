Get API endpoints | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/managed-cloud-rest-api/get-api-endpoints)

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

    - [Get API endpoints](/ems-api/managed-cloud-rest-api/get-api-endpoints)
  + [Certificate](/ems-api/managed-cloud-rest-api/certificate)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [Endpoints](/ems-api/managed-cloud-rest-api/endpoints)
* Get API endpoints

Get API endpoints
=================

```
GET

/v1/endpoints
-------------
```

Get all API endpoints that the EMS API expose for your subscription.

Request[​](/ems-api/managed-cloud-rest-api/get-api-endpoints#request "Direct link to Request")
----------------------------------------------------------------------------------------------

### Query Parameters

**filter\_exchange\_id** any

Exchange id

Responses[​](/ems-api/managed-cloud-rest-api/get-api-endpoints#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------

* 200

OK

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**exchange\_id** string

Exchange identifier and optional tag identifying specific account configured when the software will be managing multiple accounts on the same exchange; for eg:
`BITSTAMP`
`` BITSTAMP/7c177641-74bd-4dbe-9b01-2497c12a5f70` ``
`BITSTAMP/2574`
Allowed separators between the exchange identifier and the tag: `~/.,:;!@#$%^&*-_+=.`

**location\_id** string

Location identifier

**endpoint\_schema** string

Endpoint schema

**endpoint\_host** string

Endpoint host

**endpoint\_url** string

Endpoint URL

* ]

```
[  
  {  
    "exchange_id": "KRAKEN",  
    "location_id": "aws-us-east-2",  
    "endpoint_schema": "https",  
    "endpoint_host": "1314.51253.51.ec2.eu-west-1.amazonaws.com",  
    "endpoint_url": "https://1314.51253.51.ec2.eu-west-1.amazonaws.com/"  
  }  
]
```

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Endpoints](/ems-api/managed-cloud-rest-api/endpoints)[Next

Certificate](/ems-api/managed-cloud-rest-api/certificate)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.