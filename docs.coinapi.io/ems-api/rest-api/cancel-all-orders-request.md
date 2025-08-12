Cancel all orders request | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/cancel-all-orders-request)

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
* Cancel all orders request

Cancel all orders request
=========================

```
POST

/v1/orders/cancel/all
---------------------
```

This request cancels all open orders on single specified exchange.

Request[​](/ems-api/rest-api/cancel-all-orders-request#request "Direct link to Request")
----------------------------------------------------------------------------------------

* application/json

### Body

**required**

OrderCancelAllRequest object.

**exchange\_id** stringrequired

Identifier of the exchange from which active orders should be canceled.

Responses[​](/ems-api/rest-api/cancel-all-orders-request#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------

* 200
* 400
* 490

Result

* application/json

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

Cancel order request](/ems-api/rest-api/cancel-order-request)[Next

History of order changes](/ems-api/rest-api/history-of-order-changes)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.