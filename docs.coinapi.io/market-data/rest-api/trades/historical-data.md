Historical data | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/trades/historical-data)

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

* [Market Data API](/market-data/)
* [Authentication](/market-data/authentication)
* [API limits and billing](/market-data/api-limits-and-billing-metrics)
* [Metadata Tables](/market-data/metadata-tables/introduction)
* [REST API](/market-data/rest-api/)

  + [Introduction](/market-data/rest-api/)
  + [Exchange Rates](/market-data/rest-api/exchange-rates/)
  + [Metadata](/market-data/rest-api/metadata/)
  + [MetricsV1](/market-data/rest-api/metricsv1/)
  + [MetricsV2](/market-data/rest-api/metricsv2/)
  + [Ohlcv](/market-data/rest-api/ohlcv/)
  + [Options](/market-data/rest-api/options/)
  + [Order Book](/market-data/rest-api/order-book/)
  + [Order Book L3](/market-data/rest-api/order-book-l3/)
  + [Quotes](/market-data/rest-api/quotes/)
  + [Trades](/market-data/rest-api/trades/)

    - [Introduction](/market-data/rest-api/trades/coinapi-market-data-rest-api)
    - [Historical data](/market-data/rest-api/trades/historical-data)
    - [Latest data by symbol\_id](/market-data/rest-api/trades/latest-data-by-symbol-id)
    - [Latest data](/market-data/rest-api/trades/latest-data)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* REST API
* [Trades](/market-data/rest-api/trades/)
* Historical data

Historical data
===============

```
GET

/v1/trades/:symbol_id/history
-----------------------------
```

Get history transactions from specific symbol, returned in time ascending order.

warning

The 'time\_start' and 'time\_end' parameters must be from the same day as this endpoint provides intraday data only for specific day.
Please use the 'date' parameter instead for querying data for a specific day without filter.

Request[​](/market-data/rest-api/trades/historical-data#request "Direct link to Request")
-----------------------------------------------------------------------------------------

### Path Parameters

**symbol\_id** stringrequired

Symbol identifier for requested timeseries (from the Metadata -> Symbols)



### Query Parameters

**date** string

Date in ISO 8601, returned data is for the whole given day (required if 'time\_start' is not provided)

**time\_start** string

Starting time in ISO 8601

**time\_end** string

Timeseries ending time in ISO 8601

**limit** int32

**Default value:** `100`

Amount of items to return (optional, minimum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

**include\_id** boolean

Information that additional exchange trade identifier should be included in the `id_trade` parameter of the trade if exchange providing identifiers.

Responses[​](/market-data/rest-api/trades/historical-data#responses "Direct link to Responses")
-----------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The time of trade reported by the exchange.

**time\_coinapi** date-time

The time when the trade was received by CoinAPI.

**uuid** uuid

The unique identifier for the trade.

**price** double

The price of the transaction.

**size** double

The base asset amount traded in the transaction.

**taker\_side** stringnullable

The aggressor side of the transaction (BUY/SELL/BUY\_ESTIMATED/SELL\_ESTIMATED/UNKNOWN).

**id\_trade** stringnullable

The trade identifier.

**id\_order\_maker** stringnullable

The order maker identifier.

**id\_order\_taker** stringnullable

The order taker identifier.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:09.030Z",  
    "time_coinapi": "2025-08-12T06:09:09.030Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string",  
    "id_trade": "string",  
    "id_order_maker": "string",  
    "id_order_taker": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "770c7a3b-7258-4441-8182-83740f3e2457",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "BUY"  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T23:12:59.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "SELL"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The time of trade reported by the exchange.

**time\_coinapi** date-time

The time when the trade was received by CoinAPI.

**uuid** uuid

The unique identifier for the trade.

**price** double

The price of the transaction.

**size** double

The base asset amount traded in the transaction.

**taker\_side** stringnullable

The aggressor side of the transaction (BUY/SELL/BUY\_ESTIMATED/SELL\_ESTIMATED/UNKNOWN).

**id\_trade** stringnullable

The trade identifier.

**id\_order\_maker** stringnullable

The order maker identifier.

**id\_order\_taker** stringnullable

The order taker identifier.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:09.030Z",  
    "time_coinapi": "2025-08-12T06:09:09.030Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string",  
    "id_trade": "string",  
    "id_order_maker": "string",  
    "id_order_taker": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "770c7a3b-7258-4441-8182-83740f3e2457",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "BUY"  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T23:12:59.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "SELL"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The time of trade reported by the exchange.

**time\_coinapi** date-time

The time when the trade was received by CoinAPI.

**uuid** uuid

The unique identifier for the trade.

**price** double

The price of the transaction.

**size** double

The base asset amount traded in the transaction.

**taker\_side** stringnullable

The aggressor side of the transaction (BUY/SELL/BUY\_ESTIMATED/SELL\_ESTIMATED/UNKNOWN).

**id\_trade** stringnullable

The trade identifier.

**id\_order\_maker** stringnullable

The order maker identifier.

**id\_order\_taker** stringnullable

The order taker identifier.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:09.030Z",  
    "time_coinapi": "2025-08-12T06:09:09.030Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string",  
    "id_trade": "string",  
    "id_order_maker": "string",  
    "id_order_taker": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "770c7a3b-7258-4441-8182-83740f3e2457",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "BUY"  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T23:12:59.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "SELL"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The time of trade reported by the exchange.

**time\_coinapi** date-time

The time when the trade was received by CoinAPI.

**uuid** uuid

The unique identifier for the trade.

**price** double

The price of the transaction.

**size** double

The base asset amount traded in the transaction.

**taker\_side** stringnullable

The aggressor side of the transaction (BUY/SELL/BUY\_ESTIMATED/SELL\_ESTIMATED/UNKNOWN).

**id\_trade** stringnullable

The trade identifier.

**id\_order\_maker** stringnullable

The order maker identifier.

**id\_order\_taker** stringnullable

The order taker identifier.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:09.030Z",  
    "time_coinapi": "2025-08-12T06:09:09.030Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string",  
    "id_trade": "string",  
    "id_order_maker": "string",  
    "id_order_taker": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "770c7a3b-7258-4441-8182-83740f3e2457",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "BUY"  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T23:12:59.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
    "price": 770,  
    "size": 0.05,  
    "taker_side": "SELL"  
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

Introduction](/market-data/rest-api/trades/coinapi-market-data-rest-api)[Next

Latest data by symbol\_id](/market-data/rest-api/trades/latest-data-by-symbol-id)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.