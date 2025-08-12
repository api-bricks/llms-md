History of order changes | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/history-of-order-changes)

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
* History of order changes

History of order changes
========================

```
GET

/v1/orders/history
------------------
```

Based on the date range, all changes registered in the orderbook.

Request[​](/ems-api/rest-api/history-of-order-changes#request "Direct link to Request")
---------------------------------------------------------------------------------------

### Query Parameters

**time\_start** stringrequired

Start date

**time\_end** stringrequired

End date

Responses[​](/ems-api/rest-api/history-of-order-changes#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------

* 200
* 400

The last execution report of the requested order.

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**apikey** string

Apikey

**exchangeId** string

Exchange id

**clientOrderId** string

Client order id

**symbolIdExchange** string

Symbol id exchange

**symbolIdCoinapi** string

Symbol id in coinapi

**amountOrder** number

Amount

**price** number

Price

**side** number

1-buy, 2-sell

**orderType** string

Order type

**timeInForce** string

Time in force

**expireTime** date

Expire time

**execInst** string[]

Exec inst

**clientOrderIdFormatExchange** string

Client order id format

**exchangeOrderId** string

Exchange order id

**amountOpen** number

Amount open

**amountFilled** number

Amount filled

**avgPx** number

Average price

**status** string

Status

**statusHistoryStatus** string[]

History status

**statusHistoryTime** date[]

History status time

**errorMessageResult** string

Error message

**errorMessageReason** string

Error message reason

**errorMessageMessage** string

Error message

**fillsTime** date[]

Fills time

**fillsPrice** number[]

Fills price

**fillsAmount** number[]

Fills amount

**createdTime** date

Created time

* ]

```
[  
  {  
    "apikey": "9a55567a-b5ff-4b78-b6aa-xxxx",  
    "exchangeId": "BINANCE",  
    "clientOrderId": "6ab36bc1-344d-432e-ac6d-0bf44ee64c2b",  
    "symbolIdExchange": "BTCUSDT",  
    "symbolIdCoinapi": "BINANCE_SPOT_BTC_USDT",  
    "amountOrder": 0.00034,  
    "price": 31939.47,  
    "side": 2,  
    "orderType": "LIMIT",  
    "timeInForce": "GOOD_TILL_CANCEL",  
    "expireTime": "2022-05-01T00:00:00",  
    "execInst": [  
      [  
        "MAKER_OR_CANCEL"  
      ]  
    ],  
    "clientOrderIdFormatExchange": "6ab36bc1-344d-432e-ac6d-0bf44ee64c2b",  
    "exchangeOrderId": "6ab36bc1-344d-432e-ac6d-0bf44ee64c2b",  
    "amountOpen": 0.00034,  
    "amountFilled": 0,  
    "avgPx": 0,  
    "status": "REJECTED",  
    "statusHistoryStatus": [  
      [  
        "RECEIVED",  
        "ROUTING",  
        "REJECTED"  
      ]  
    ],  
    "statusHistoryTime": [  
      [  
        "2022-05-27T13:06:34.5122626Z",  
        "2022-05-27T13:06:37.3410216Z",  
        "2022-05-27T13:06:40.1342877Z"  
      ]  
    ],  
    "errorMessageResult": "string",  
    "errorMessageReason": "string",  
    "errorMessageMessage": "-2015 Invalid API-key, IP, or permissions for action. https://api.binance.com/api/v3/order?newOrderRespType",  
    "fillsTime": [  
      [  
        "2022-05-27T13:06:34.5122626Z",  
        "2022-05-27T13:06:37.3410216Z",  
        "2022-05-27T13:06:40.1342877Z"  
      ]  
    ],  
    "fillsPrice": [  
      [  
        31939.47,  
        31939.67  
      ]  
    ],  
    "fillsAmount": [  
      [  
        0.0032,  
        0.0009  
      ]  
    ],  
    "createdTime": "2022-06-27T07:02:33.1977903Z"  
  }  
]
```

Orders log is not configured.

* application/json

* Schema
* Example (from schema)

**Schema**

**message** string

Message text.

```
{  
  "message": "string"  
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

Cancel all orders request](/ems-api/rest-api/cancel-all-orders-request)[Next

Balances](/ems-api/rest-api/balances)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.