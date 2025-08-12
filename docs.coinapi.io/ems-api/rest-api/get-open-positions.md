Get open positions | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/get-open-positions)

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
  + [Positions](/ems-api/rest-api/positions)

    - [Get open positions](/ems-api/rest-api/get-open-positions)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [Positions](/ems-api/rest-api/positions)
* Get open positions

Get open positions
==================

```
GET

/v1/positions
-------------
```

Get current open positions across all or single exchange.

Request[​](/ems-api/rest-api/get-open-positions#request "Direct link to Request")
---------------------------------------------------------------------------------

### Query Parameters

**exchange\_id** string

Filter the balances to the specific exchange.

Responses[​](/ems-api/rest-api/get-open-positions#responses "Direct link to Responses")
---------------------------------------------------------------------------------------

* 200
* 490

Collection of positons.

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

**symbol\_id\_exchange** string

Exchange symbol.

**symbol\_id\_coinapi** string

CoinAPI symbol.

**avg\_entry\_price** number

Calculated average price of all fills on this position.

**quantity** number

The current position quantity.

**side** OrdSide (string)

**Possible values:** [`BUY`, `SELL`]

Side of order.

**unrealized\_pnl** number

Unrealised profit or loss (PNL) of this position.

**leverage** number

Leverage for this position reported by the exchange.

**cross\_margin** boolean

Is cross margin mode enable for this position?

**liquidation\_price** number

Liquidation price. If mark price will reach this value, the position will be liquidated.

**raw\_data** object

* ]

* ]

```
[  
  {  
    "exchange_id": "KRAKEN",  
    "data": [  
      {  
        "symbol_id_exchange": "XBTUSD",  
        "symbol_id_coinapi": "BITMEX_PERP_BTC_USD",  
        "avg_entry_price": 0.00134444,  
        "quantity": 7,  
        "side": "BUY",  
        "unrealized_pnl": 0,  
        "leverage": 0,  
        "cross_margin": true,  
        "liquidation_price": 0.072323,  
        "raw_data": "Other information provided by the exchange on this position."  
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

Positions](/ems-api/rest-api/positions)[Next

Introduction](/ems-api/websocket/)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.