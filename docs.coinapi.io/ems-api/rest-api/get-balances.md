Get balances | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/get-balances)

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

  + [Introduction](/ems-api/rest-api/rest-api)
  + [Orders](/ems-api/rest-api/orders)
  + [Balances](/ems-api/rest-api/balances)

    - [Get balances](/ems-api/rest-api/get-balances)
  + [Positions](/ems-api/rest-api/positions)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [Balances](/ems-api/rest-api/balances)
* Get balances

Get balances
============

```
GET

/v1/balances
------------
```

Get current currency balance from all or single exchange.

Request[​](/ems-api/rest-api/get-balances#request "Direct link to Request")
---------------------------------------------------------------------------

### Query Parameters

**exchange\_id** string

Filter the balances to the specific exchange.

Responses[​](/ems-api/rest-api/get-balances#responses "Direct link to Responses")
---------------------------------------------------------------------------------

* 200
* 490

Collection of balances.

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**exchange\_id** string

Exchange identifier used to identify the routing destination.

**data**

object[]

* Array [

**asset\_id\_exchange** string

Exchange currency code.

**asset\_id\_coinapi** string

CoinAPI currency code.

**balance** double

Value of the current total currency balance on the exchange.

**available** double

Value of the current available currency balance on the exchange that can be used as collateral.

**locked** double

Value of the current locked currency balance by the exchange.

**last\_updated\_by** string

**Possible values:** [`INITIALIZATION`, `BALANCE_MANAGER`, `EXCHANGE`]

Source of the last modification.

**rate\_usd** double

Current exchange rate to the USD for the single unit of the currency.

**traded** double

Value of the current total traded.

* ]

* ]

```
[  
  {  
    "exchange_id": "KRAKEN",  
    "data": [  
      {  
        "asset_id_exchange": "XBT",  
        "asset_id_coinapi": "BTC",  
        "balance": 0.00134444,  
        "available": 0.00134444,  
        "locked": 0,  
        "last_updated_by": "EXCHANGE",  
        "rate_usd": 1355.12,  
        "traded": 0.007  
      }  
    ]  
  }  
]
```

Exchange is unreachable.

* appliction/json

* Schema
* Example (from schema)

**Schema**

**type** string

Message type, constant.

**reject\_reason** RejectReason (string)

**Possible values:** [`OTHER`, `EXCHANGE_UNREACHABLE`, `EXCHANGE_RESPONSE_TIMEOUT`, `ORDER_ID_NOT_FOUND`, `INVALID_TYPE`, `METHOD_NOT_SUPPORTED`, `JSON_ERROR`]

Cause of rejection.

**exchange\_id** string

If the message related to exchange, then the identifier of the exchange will be provided.

**message** string

Message text.

**rejected\_message** string

Value of rejected request, if available.

```
{  
  "type": "MESSAGE_REJECT",  
  "reject_reason": "ORDER_ID_NOT_FOUND",  
  "exchange_id": "BINANCE",  
  "message": "Order with ID: BINANCE-7d8a-4888 not found",  
  "rejected_message": "{\"client_order_id\":\"BINANCE-7d8a-4888\",\"exchange_id\":\"BINANCE\",\"type\":\"ORDER_CANCEL_SINGLE_REQUEST\"}"  
}
```

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Balances](/ems-api/rest-api/balances)[Next

Positions](/ems-api/rest-api/positions)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.