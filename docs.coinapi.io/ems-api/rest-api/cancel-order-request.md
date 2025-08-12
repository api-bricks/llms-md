Cancel order request | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/cancel-order-request)

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

    - [Get open orders](/ems-api/rest-api/get-open-orders)
    - [Send new order](/ems-api/rest-api/send-new-order)
    - [Get order execution report](/ems-api/rest-api/get-order-execution-report)
    - [Cancel order request](/ems-api/rest-api/cancel-order-request)
    - [Cancel all orders request](/ems-api/rest-api/cancel-all-orders-request)
    - [History of order changes](/ems-api/rest-api/history-of-order-changes)
  + [Balances](/ems-api/rest-api/balances)
  + [Positions](/ems-api/rest-api/positions)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [Orders](/ems-api/rest-api/orders)
* Cancel order request

Cancel order request
====================

```
POST

/v1/orders/cancel
-----------------
```

Request cancel for an existing order. The order can be canceled using the `client_order_id` or `exchange_order_id`.

Request[​](/ems-api/rest-api/cancel-order-request#request "Direct link to Request")
-----------------------------------------------------------------------------------

* application/json

### Body

**required**

OrderCancelSingleRequest object.

**exchange\_id** stringrequired

Exchange identifier used to identify the routing destination.

**exchange\_order\_id** string

Unique identifier of the order assigned by the exchange or executing system. One of the properties (`exchange_order_id`, `client_order_id`) is required to identify the new order.

**client\_order\_id** string

The unique identifier of the order assigned by the client. One of the properties (`exchange_order_id`, `client_order_id`) is required to identify the new order.

Responses[​](/ems-api/rest-api/cancel-order-request#responses "Direct link to Responses")
-----------------------------------------------------------------------------------------

* 200
* 400
* 490

The last execution report for the order for which cancelation was requested.

* application/json

* Schema
* Example (from schema)

**Schema**

**exchange\_id** stringrequired

Exchange identifier used to identify the routing destination.

**client\_order\_id** stringrequired

The unique identifier of the order assigned by the client.

**symbol\_id\_exchange** string

Exchange symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order.

**symbol\_id\_coinapi** string

CoinAPI symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order.

**amount\_order** numberrequired

Order quantity.

**price** numberrequired

Order price.

**side** OrdSide (string)required

**Possible values:** [`BUY`, `SELL`]

Side of order.

**order\_type** OrdType (string)required

**Possible values:** [`LIMIT`]

Order types are documented in the separate section: [EMS / Starter Guide / Order parameters / Order type](#ems-order-params-type)

**time\_in\_force** TimeInForce (string)required

**Possible values:** [`GOOD_TILL_CANCEL`, `GOOD_TILL_TIME_EXCHANGE`, `GOOD_TILL_TIME_OMS`, `FILL_OR_KILL`, `IMMEDIATE_OR_CANCEL`]

Order time in force options are documented in the separate section: [EMS / Starter Guide / Order parameters / Time in force](#ems-order-params-tif)

**expire\_time** date

Expiration time. Conditionaly required for orders with time\_in\_force = `GOOD_TILL_TIME_EXCHANGE` or `GOOD_TILL_TIME_OEML`.

**exec\_inst** string[]

**Possible values:** [`MAKER_OR_CANCEL`, `AUCTION_ONLY`, `INDICATION_OF_INTEREST`]

Order execution instructions are documented in the separate section: [EMS / Starter Guide / Order parameters / Execution instructions](#ems-order-params-exec)

**client\_order\_id\_format\_exchange** stringrequired

The unique identifier of the order assigned by the client converted to the exchange order tag format for the purpose of tracking it.

**exchange\_order\_id** string

Unique identifier of the order assigned by the exchange or executing system.

**amount\_open** numberrequired

Quantity open for further execution. `amount_open` = `amount_order` - `amount_filled`

**amount\_filled** numberrequired

Total quantity filled.

**avg\_px** number

Calculated average price of all fills on this order.

**status** OrdStatus (string)required

**Possible values:** [`RECEIVED`, `ROUTING`, `ROUTED`, `NEW`, `PENDING_CANCEL`, `PARTIALLY_FILLED`, `FILLED`, `CANCELED`, `REJECTED`]

Order statuses and the lifecycle are documented in the separate section: [EMS / Starter Guide / Order Lifecycle](#ems-order-lifecycle)

**status\_history** array[]

Timestamped history of order status changes.

**error\_message** string

Error message.

**fills**

object[]

Relay fill information on working orders.

* Array [

**time** date

Execution time.

**price** number

Execution price.

**amount** number

Executed quantity.

* ]

```
{  
  "exchange_id": "KRAKEN",  
  "client_order_id": "6ab36bc1-344d-432e-ac6d-0bf44ee64c2b",  
  "symbol_id_exchange": "XBT/USDT",  
  "symbol_id_coinapi": "KRAKEN_SPOT_BTC_USDT",  
  "amount_order": 0.045,  
  "price": 0.0783,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": "2020-01-01T10:45:20.1677709Z",  
  "exec_inst": [  
    "MAKER_OR_CANCEL"  
  ],  
  "client_order_id_format_exchange": "f81211e2-27c4-b86a-8143-01088ba9222c",  
  "exchange_order_id": 3456456754,  
  "amount_open": 0.22,  
  "amount_filled": 0,  
  "avg_px": 0.0783,  
  "status": "RECEIVED",  
  "status_history": [  
    [  
      [  
        [  
          "RECEIVED",  
          "2020-05-27T11:16:20.1677709Z"  
        ],  
        [  
          "REJECTED",  
          "2020-05-27T11:16:20.1677710Z"  
        ]  
      ]  
    ]  
  ],  
  "error_message": "{\"result\":\"error\",\"reason\":\"InsufficientFunds\",\"message\":\"Failed to place buy order on symbol 'BTCUSD' for price $7,000.00 and quantity 0.22 BTC due to insufficient funds\"}",  
  "fills": [  
    {  
      "time": "2020-01-01T10:45:20.1677709Z",  
      "price": 10799.2,  
      "amount": 0.002  
    }  
  ]  
}
```

Input model validation errors.

* application/json

* Schema
* Example (from schema)

**Schema**

**type** string

**title** string

**status** number

**traceId** string

**errors** string

```
{  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",  
  "title": "One or more validation errors occurred.",  
  "status": 400,  
  "traceId": "d200e8b5-4271a5461ce5342f",  
  "errors": "string"  
}
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

Get order execution report](/ems-api/rest-api/get-order-execution-report)[Next

Cancel all orders request](/ems-api/rest-api/cancel-all-orders-request)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.