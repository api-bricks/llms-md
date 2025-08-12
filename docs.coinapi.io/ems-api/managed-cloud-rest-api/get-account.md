Get accounts | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/managed-cloud-rest-api/get-account)

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

    - [Get accounts](/ems-api/managed-cloud-rest-api/get-account)
    - [Add or update account](/ems-api/managed-cloud-rest-api/persist-account)
    - [Delete account](/ems-api/managed-cloud-rest-api/delete-account)
    - [Delete all accounts](/ems-api/managed-cloud-rest-api/delete-account-all)
  + [Exchange](/ems-api/managed-cloud-rest-api/exchange)
  + [Location](/ems-api/managed-cloud-rest-api/location)
  + [Endpoints](/ems-api/managed-cloud-rest-api/endpoints)
  + [Certificate](/ems-api/managed-cloud-rest-api/certificate)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [Account](/ems-api/managed-cloud-rest-api/account)
* Get accounts

Get accounts
============

```
GET

/v1/accounts
------------
```

Get all accounts maintained for your subscription in the EMS API.

Request[​](/ems-api/managed-cloud-rest-api/get-account#request "Direct link to Request")
----------------------------------------------------------------------------------------

### Query Parameters

**filter\_exchange\_id** any

Exchange id of the specific account to provide single account instead of the list of all accounts

Responses[​](/ems-api/managed-cloud-rest-api/get-account#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------

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

**parameters**

object[]

Exchange specific configuration parameters

* Array [

**key** string

**value** string

* ]

* ]

```
[  
  {  
    "exchange_id": "string",  
    "parameters": [  
      {  
        "key": "PublicApiKey",  
        "value": "36279b02-d24f-40be-a61b-e9fd7de46dd6"  
      }  
    ]  
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

Account](/ems-api/managed-cloud-rest-api/account)[Next

Add or update account](/ems-api/managed-cloud-rest-api/persist-account)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.