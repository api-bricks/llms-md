Get site locations | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/managed-cloud-rest-api/locations)

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

    - [Get site locations](/ems-api/managed-cloud-rest-api/locations)
  + [Endpoints](/ems-api/managed-cloud-rest-api/endpoints)
  + [Certificate](/ems-api/managed-cloud-rest-api/certificate)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [Location](/ems-api/managed-cloud-rest-api/location)
* Get site locations

Get site locations
==================

```
GET

/v1/locations
-------------
```

This endpoint providing information about the server site locations supported in the EMS API.

Responses[​](/ems-api/managed-cloud-rest-api/locations#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------

* 200

OK

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**location\_id** string

CoinAPI location identifier

**region\_name** string

Identifier of the region by the location provider

**provider\_name** string

Identifier of the location provider

* ]

```
[  
  {  
    "location_id": "aws-us-east-1",  
    "region_name": "us-east-1",  
    "provider_name": "aws"  
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

Location](/ems-api/managed-cloud-rest-api/location)[Next

Endpoints](/ems-api/managed-cloud-rest-api/endpoints)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.