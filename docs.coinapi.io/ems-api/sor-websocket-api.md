SOR - WebSocket API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/sor-websocket-api)

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
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* SOR - WebSocket API

On this page

CoinAPI OEML SOR API
====================

Base URL[​](/ems-api/sor-websocket-api#base-url "Direct link to Base URL")
--------------------------------------------------------------------------

`/v1/sor`

Endpoints[​](/ems-api/sor-websocket-api#endpoints "Direct link to Endpoints")
-----------------------------------------------------------------------------

### Get Smart Orders[​](/ems-api/sor-websocket-api#get-smart-orders "Direct link to Get Smart Orders")

#### GET `/requests`[​](/ems-api/sor-websocket-api#get-requests "Direct link to get-requests")

Fetches all smart order requests.

**Response:**

```
[  
    {  
        "id": "fb7d3987-fd78-41fa-985e-748a67375b31",  
        "status": "Cancelled",  
        "statusInfo": "User requested cancel",  
        "symbol": "BTC-USD",  
        "amount": 20,  
        "algorithm": "TWAP",  
        "side": "Sell",  
        "duration": "5MIN",  
        "interval": "30SEC",  
        "exchanges": [  
            "DERIBIT"  
        ],  
        "statusHistory": {  
            "Running": "07/24/2024 09:41:40",  
            "Cancelled": "07/24/2024 09:44:13"  
        },  
        "parametersUpdates": {  
            "2024-07-24T09:42:14.9062991Z": {  
                "side": "sell",  
                "symbol": "BTC-USD",  
                "symbol_type": "perpetual",  
                "amount": "20",  
                "duration": "5MIN",  
                "interval": "1MIN"  
            }  
        },  
        "fills": [  
            {  
                "exchange": "DERIBIT",  
                "amountFilled": 3.0,  
                "price": 66370.5,  
                "timeStamp": "2024-07-24T09:41:45.7727049Z"  
            },  
            {  
                "exchange": "DERIBIT",  
                "amountFilled": 2.0,  
                "price": 66370.5,  
                "timeStamp": "2024-07-24T09:42:45.8954363Z"  
            },  
            {  
                "exchange": "DERIBIT",  
                "amountFilled": 2.0,  
                "price": 66370.5,  
                "timeStamp": "2024-07-24T09:43:16.0088651Z"  
            },  
            {  
                "exchange": "DERIBIT",  
                "amountFilled": 2.0,  
                "price": 66387.5,  
                "timeStamp": "2024-07-24T09:43:46.2376039Z"  
            }  
        ]  
    }  
]
```

### Get Balances[​](/ems-api/sor-websocket-api#get-balances "Direct link to Get Balances")

#### GET `/balances`[​](/ems-api/sor-websocket-api#get-balances-1 "Direct link to get-balances-1")

Fetches all balances.

**Response:**

```
{  
    "DERIBIT": [  
        {  
            "id": "BTC",  
            "asset_id_exchange": "BTC",  
            "asset_id_coinapi": "BTC",  
            "balance": 0.00324182,  
            "available": 0.00308591,  
            "locked": 0.00015591,  
            "traded": 0.0,  
            "last_updated_by": "EXCHANGE",  
            "rate_usd": null  
        }  
    ]  
}
```

### Get Open Orders[​](/ems-api/sor-websocket-api#get-open-orders "Direct link to Get Open Orders")

#### GET `/orders`[​](/ems-api/sor-websocket-api#get-orders "Direct link to get-orders")

Fetches all open orders.

**Response:**

```
{  
    "DERIBIT": [  
        {  
            "id": "79696dc9-70a9-4b4f-b52d-f4a816894268",  
            "client_order_id_format_exchange": "79696dc9-70a9-4b4f-b52d-f4a816894268",  
            "exchange_order_id": "72327252536",  
            "amount_open": 10.0,  
            "amount_filled": 0.0,  
            "status": "NEW",  
            "status_history": [  
                [  
                    "RECEIVED",  
                    "2024-06-28T07:43:53.1499458Z"  
                ],  
                [  
                    "ROUTING",  
                    "2024-06-28T07:43:53.2547245Z"  
                ],  
                [  
                    "ROUTED",  
                    "2024-06-28T07:43:53.3086465Z"  
                ],  
                [  
                    "NEW",  
                    "2024-06-28T07:43:53.3163276Z"  
                ]  
            ],  
            "error_message": null,  
            "fills": [],  
            "exchange_id": "DERIBIT",  
            "client_order_id": "79696dc9-70a9-4b4f-b52d-f4a816894268",  
            "symbol_id_exchange": "BTC-PERPETUAL",  
            "symbol_id_coinapi": "DERIBIT_PERP_BTC_USD",  
            "amount_order": 10.0,  
            "price": 61200.0,  
            "avg_px": 0.0,  
            "side": "BUY",  
            "order_type": "LIMIT",  
            "time_in_force": "GOOD_TILL_CANCEL",  
            "expire_time": null,  
            "exec_inst": []  
        }  
    ]  
}
```

### Get Open Positions[​](/ems-api/sor-websocket-api#get-open-positions "Direct link to Get Open Positions")

#### GET `/positions`[​](/ems-api/sor-websocket-api#get-positions "Direct link to get-positions")

Fetches all open positions.

**Response:**

```
{  
    "DERIBIT": [  
        {  
            "id": "BTC-PERPETUAL",  
            "symbol_id_exchange": "BTC-PERPETUAL",  
            "symbol_id_coinapi": "DERIBIT_PERP_BTC_USD",  
            "avg_entry_price": 61362.86103755,  
            "quantity": 40.0,  
            "side": "BUY",  
            "unrealized_pnl": 0.000111354,  
            "leverage": 10.0,  
            "cross_margin": false,  
            "liquidation_price": 41280.82400315,  
            "raw_data": "[{"Key":54,"Value":{"Obj":"1","Tag":54}},{"Key":55,"Value":{"Obj":"BTC-PERPETUAL","Tag":55}},{"Key":95,"Value":{"Obj":"30","Tag":95}},{"Key":96,"Value":{"Obj":"6.4341e-5;1.2868e-4;1.11354e-4","Tag":96}},{"Key":231,"Value":{"Obj":"10.0","Tag":231}},{"Key":702,"Value":{"Obj":"1","Tag":702}},{"Key":703,"Value":{"Obj":"TQ","Tag":703}},{"Key":704,"Value":{"Obj":"40.0","Tag":704}},{"Key":705,"Value":{...  
        }  
    ]  
}
```

### Add Smart Order[​](/ems-api/sor-websocket-api#add-smart-order "Direct link to Add Smart Order")

#### POST `/add`[​](/ems-api/sor-websocket-api#post-add "Direct link to post-add")

Adds a new smart order.

**Request Body:**

```
{  
    "Algorithm": "TWAP",  
    "Exchanges": ["DERIBIT"],  
    "Parameters": {  
        "side": "sell",  
        "symbol": "BTC-USD",  
        "symbol_type": "perpetual",  
        "amount": "29",  
        "duration": "1MIN",  
        "interval": "5SEC"  
    }  
}
```

**Response:**

```
{  
    "type": "New",  
    "id": "d574e33e-133f-4bf0-bb8b-9c6294c32d2a",  
    "exchanges": [  
        "DERIBIT"  
    ],  
    "algorithm": "TWAP",  
    "parameters": {  
        "side": "sell",  
        "symbol": "BTC-USD",  
        "symbol_type": "perpetual",  
        "amount": "29",  
        "duration": "1MIN",  
        "interval": "5SEC"  
    }  
}
```

### Cancel Smart Order[​](/ems-api/sor-websocket-api#cancel-smart-order "Direct link to Cancel Smart Order")

#### POST `/cancel/{id}`[​](/ems-api/sor-websocket-api#post-cancelid "Direct link to post-cancelid")

Cancels a smart order by its ID.

**Request Parameter:**

* `id`: The ID of the order to be canceled.

**Response:**

* `200 OK` if the order is successfully canceled.
* `400 Bad Request` if there is an error.

### Update Smart Order[​](/ems-api/sor-websocket-api#update-smart-order "Direct link to Update Smart Order")

#### PUT `/update`[​](/ems-api/sor-websocket-api#put-update "Direct link to put-update")

Updates an existing smart order.

**Request Body:**

```
{  
    "Id": "string",  
    "Parameters": {  
        "amount": "string",  
        "duration": "string",  
        "interval": "string"  
    }  
}
```

**Response:**

* `200 OK` if the order is successfully updated.
* `400 Bad Request` if there is an error.

WebSocket Feed[​](/ems-api/sor-websocket-api#websocket-feed "Direct link to WebSocket Feed")
--------------------------------------------------------------------------------------------

### Add Smart Order Message:[​](/ems-api/sor-websocket-api#add-smart-order-message "Direct link to Add Smart Order Message:")

#### Message Format[​](/ems-api/sor-websocket-api#message-format "Direct link to Message Format")

```
{  
    "type": "New",  
	"Algorithm": "TWAP",  
    "Exchanges": ["DERIBIT"],  
    "Parameters": {  
        "side": "sell",  
        "symbol": "BTC-USD",  
        "symbol_type": "perpetual",  
        "amount": "29",  
        "duration": "1MIN",  
        "interval": "5SEC"  
    }  
}
```

##### This will trigger output which can look like this:[​](/ems-api/sor-websocket-api#this-will-trigger-output-which-can-look-like-this "Direct link to This will trigger output which can look like this:")

**StatusChange message**

```
{  
  "Type": "StatusChange",  
  "CompositeId": "fddac1f2-d98a-4e5c-9824-8e334039bb81",  
  "Data": {  
    "Id": "fddac1f2-d98a-4e5c-9824-8e334039bb81",  
    "TotalFilled": 0,  
    "FillsCount": 0,  
    "Status": "Running",  
    "Fills": []  
  }  
}
```

**TradeRequest message**

```
{  
  "Type": "TradeRequest",  
  "CompositeId": "fddac1f2-d98a-4e5c-9824-8e334039bb81",  
  "Data": {  
    "type": "ORDER_NEW_SINGLE_REQUEST",  
    "exchange_id": "DERIBIT",  
    "client_order_id": "04fd0f2c-e53f-4ab8-ae05-e881a4cbafb7",  
    "symbol_id_exchange": null,  
    "symbol_id_coinapi": "DERIBIT_PERP_BTC_USD",  
    "amount_order": 3,  
    "price": 66484.5,  
    "avg_px": 0,  
    "side": "BUY",  
    "order_type": "LIMIT",  
    "time_in_force": "IMMEDIATE_OR_CANCEL",  
    "expire_time": null,  
    "exec_inst": []  
  }  
}
```

**TradeFill message**

```
{  
  "Type": "TradeFill",  
  "CompositeId": "fddac1f2-d98a-4e5c-9824-8e334039bb81",  
  "Data": {  
    "OrderId": "04fd0f2c-e53f-4ab8-ae05-e881a4cbafb7",  
    "Exchange": "DERIBIT",  
    "SymbolId": "DERIBIT_PERP_BTC_USD",  
    "AmountFilled": 3,  
    "Price": 66484.5,  
    "Side": "Buy",  
    "Status": "FILLED",  
    "TimeStamp": "2024-07-24T11:29:59.6384886Z"  
  }  
}
```

`...`

**StatusChange message**

```
{  
  "Type": "StatusChange",  
  "CompositeId": "fddac1f2-d98a-4e5c-9824-8e334039bb81",  
  "Data": {  
    "Id": "fddac1f2-d98a-4e5c-9824-8e334039bb81",  
    "TotalFilled": 20,  
    "FillsCount": 6,  
    "Status": "Completed",  
    "Fills": [  
      {  
        "OrderId": "04fd0f2c-e53f-4ab8-ae05-e881a4cbafb7",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66484.5,  
        "Side": "Buy",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:29:59.6384886Z"  
      },  
      {  
        "OrderId": "fdb7b32b-ad35-42ea-b65d-3f25f98c03df",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66484.5,  
        "Side": "Buy",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:30:09.8103657Z"  
      },  
      {  
        "OrderId": "327365c9-62bf-4746-8836-76a7c8126059",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66485,  
        "Side": "Buy",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:30:20.0299802Z"  
      },  
      {  
        "OrderId": "4c42b8ef-7ab0-43ca-b405-b3145be24aa4",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66485,  
        "Side": "Buy",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:30:30.1605334Z"  
      },  
      {  
        "OrderId": "c54adf52-488e-4afa-87c3-2250c43970ee",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66485,  
        "Side": "Buy",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:30:40.3878383Z"  
      },  
      {  
        "OrderId": "2a5fa24b-31f2-4909-831b-da710c059ad8",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 5,  
        "Price": 66456,  
        "Side": "Buy",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:31:00.7103820Z"  
      }  
    ]  
  }  
}
```

### Cancel Message:[​](/ems-api/sor-websocket-api#cancel-message "Direct link to Cancel Message:")

#### Message Format[​](/ems-api/sor-websocket-api#message-format-1 "Direct link to Message Format")

```
{  
  "Type": "cancel",  
  "Id": "7287b325-243b-44c5-a3de-63d148bbc04b"  
}
```

##### This will trigger output which can look like this:[​](/ems-api/sor-websocket-api#this-will-trigger-output-which-can-look-like-this-1 "Direct link to This will trigger output which can look like this:")

```
{  
  "Type": "StatusChange",  
  "CompositeId": "7287b325-243b-44c5-a3de-63d148bbc04b",  
  "Data": {  
    "Id": "7287b325-243b-44c5-a3de-63d148bbc04b",  
    "TotalFilled": 9,  
    "FillsCount": 3,  
    "Status": "Cancelled",  
    "Fills": [  
      {  
        "OrderId": "7431c0d8-61ad-4bb3-81b3-79f25765f98a",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66419,  
        "Side": "Sell",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:39:35.9672103Z"  
      },  
      {  
        "OrderId": "8b5d8ff1-ed8b-43c6-b237-d5e970c4e3fd",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66414,  
        "Side": "Sell",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:39:41.2653974Z"  
      },  
      {  
        "OrderId": "d7e1dcbc-60c3-456a-8c26-01995aecbd84",  
        "Exchange": "DERIBIT",  
        "SymbolId": "DERIBIT_PERP_BTC_USD",  
        "AmountFilled": 3,  
        "Price": 66414,  
        "Side": "Sell",  
        "Status": "FILLED",  
        "TimeStamp": "2024-07-24T11:39:51.4043702Z"  
      }  
    ]  
  }  
}
```

### Supported Algorithms[​](/ems-api/sor-websocket-api#supported-algorithms "Direct link to Supported Algorithms")

The following algorithms are supported for trading:

* **TWAP** (Time-Weighted Average Price): Executes trades evenly over a specified period.
  + **Parameters**:
    - `amount`: Total amount to be traded.
    - `duration`: Total duration of the trading period.
    - `interval`: Time interval between each trade.

***Pseudocode***

```
Initialize totalAmount, duration, interval, side  
Calculate iterationCount = (duration / interval) + 1  
Calculate amountPerTrade = totalAmount / iterationCount  
Initialize currentIteration = 0  
  
While currentIteration < iterationCount:  
    if order is already filled:  
        Stop the smart order  
    else:  
        Execute trade with amountPerTrade  
        Increment currentIteration  
        Wait for interval  
    End If  
End While
```

* **VWAP** (Volume-Weighted Average Price): Executes trades based on the volume over a specified period.
  + **Parameters**:
    - `amount`: Total amount to be traded.
    - `duration`: Total duration of the trading period.
    - `interval`: Time interval between each trade.

***Pseudocode***

```
Initialize totalAmount, duration, interval, side  
Calculate iterationCount = (duration / interval) + 1  
Initialize currentIteration = 0  
  
While currentIteration < iterationCount:  
    if order is already filled:  
        Stop the smart order  
    else:  
        Get intervalMarketVolume from CoinAPI OHLCV data  
        Calculate tradeVolume = min(intervalMarketVolume * safetyThreshold, totalAmount / (iterationCount - currentIteration))  
        Execute trade with tradeVolume  
        Increment currentIteration  
        Wait for interval  
    End If  
End While
```

old docs
========

Establishes a WebSocket connection for real-time communication.

Once connected, you can send and receive JSON messages using the defined DTOs.

To send a new order message:

```
{  
  "type": "New",  
  "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
  "exchanges": ["exchange1", "exchange2"],  
  "algorithm": "TWAP",  
  "parameters": {  
    "symbol": "BTC-USD",  
    "symbol_type": "spot",  
    "side": "Buy",  
    "amount": 10,  
    "duration": "1DAY",  
    "interval": "1HRS"  
  }  
}
```

To cancel an order:

```
{  
  "type": "Cancel",  
  "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6"  
}
```

To change parameters of an existing order:

```
{  
  "type": "ParamChange",  
  "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
  "parameters": {  
    "amount": 10,  
    "duration": "1DAY",  
    "interval": "1HRS"  
  }  
}
```

Available message types:

* New (NewSmartOrderRequestDto)
* Cancel (SmartOrderCancelRequestDto)
* ParamChange (SmartOrderParamsChangeRequestDto)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Messages](/ems-api/fix/messages)[Next

Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [Base URL](/ems-api/sor-websocket-api#base-url)
* [Endpoints](/ems-api/sor-websocket-api#endpoints)
  + [Get Smart Orders](/ems-api/sor-websocket-api#get-smart-orders)
  + [Get Balances](/ems-api/sor-websocket-api#get-balances)
  + [Get Open Orders](/ems-api/sor-websocket-api#get-open-orders)
  + [Get Open Positions](/ems-api/sor-websocket-api#get-open-positions)
  + [Add Smart Order](/ems-api/sor-websocket-api#add-smart-order)
  + [Cancel Smart Order](/ems-api/sor-websocket-api#cancel-smart-order)
  + [Update Smart Order](/ems-api/sor-websocket-api#update-smart-order)
* [WebSocket Feed](/ems-api/sor-websocket-api#websocket-feed)
  + [Add Smart Order Message:](/ems-api/sor-websocket-api#add-smart-order-message)
  + [Cancel Message:](/ems-api/sor-websocket-api#cancel-message)
  + [Supported Algorithms](/ems-api/sor-websocket-api#supported-algorithms)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.