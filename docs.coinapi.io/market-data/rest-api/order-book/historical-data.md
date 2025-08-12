Historical data | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/order-book/historical-data)

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

    - [Introduction](/market-data/rest-api/order-book/coinapi-market-data-rest-api)
    - [Current depth of the order book](/market-data/rest-api/order-book/current-depth-of-the-order-book)
    - [Get current order book](/market-data/rest-api/order-book/get-current-order-book)
    - [Historical data](/market-data/rest-api/order-book/historical-data)
    - [Latest data](/market-data/rest-api/order-book/latest-data)
  + [Order Book L3](/market-data/rest-api/order-book-l3/)
  + [Quotes](/market-data/rest-api/quotes/)
  + [Trades](/market-data/rest-api/trades/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* REST API
* [Order Book](/market-data/rest-api/order-book/)
* Historical data

Historical data
===============

```
GET

/v1/orderbooks/:symbol_id/history
---------------------------------
```

Get historical order book snapshots for a specific symbol within time range, returned in time ascending order.

info

The historical order book data via the REST API is currently limited by a number of updates and to the maximum number of 20 levels.

warning

The 'time\_start' and 'time\_end' parameters must be from the same day as this endpoint provides intraday data only for specific day.
Please use the 'date' parameter instead for querying data for a specific day without filter.

Request[​](/market-data/rest-api/order-book/historical-data#request "Direct link to Request")
---------------------------------------------------------------------------------------------

### Path Parameters

**symbol\_id** stringrequired

Symbol identifier for requested timeseries (from the Metadata -> Symbols)



### Query Parameters

**date** string

Date in ISO 8601, returned data is for the whole given day (preferred method, required if 'time\_start' is not provided)

**time\_start** string

Starting time in ISO 8601 (deprecated, use 'date' instead)

**time\_end** string

Timeseries ending time in ISO 8601 (deprecated, use 'date' instead)

**limit** int32

**Default value:** `100`

Amount of items to return (optional, minimum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

**limit\_levels** int32

Maximum amount of levels from each side of the book to include in response (optional)

Responses[​](/market-data/rest-api/order-book/historical-data#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------------

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

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:08.960Z",  
    "time_coinapi": "2025-08-12T06:09:08.960Z"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "asks": [  
      {  
        "price": 456.35,  
        "size": 123  
      },  
      {  
        "price": 456.36,  
        "size": 23  
      }  
    ],  
    "bids": [  
      {  
        "price": 456.1,  
        "size": 42  
      },  
      {  
        "price": 456.09,  
        "size": 5  
      }  
    ]  
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

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:08.960Z",  
    "time_coinapi": "2025-08-12T06:09:08.960Z"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "asks": [  
      {  
        "price": 456.35,  
        "size": 123  
      },  
      {  
        "price": 456.36,  
        "size": 23  
      }  
    ],  
    "bids": [  
      {  
        "price": 456.1,  
        "size": 42  
      },  
      {  
        "price": 456.09,  
        "size": 5  
      }  
    ]  
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

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:08.960Z",  
    "time_coinapi": "2025-08-12T06:09:08.960Z"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "asks": [  
      {  
        "price": 456.35,  
        "size": 123  
      },  
      {  
        "price": 456.36,  
        "size": 23  
      }  
    ],  
    "bids": [  
      {  
        "price": 456.1,  
        "size": 42  
      },  
      {  
        "price": 456.09,  
        "size": 5  
      }  
    ]  
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

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time_exchange": "2025-08-12T06:09:08.961Z",  
    "time_coinapi": "2025-08-12T06:09:08.961Z"  
  }  
]
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "asks": [  
      {  
        "price": 456.35,  
        "size": 123  
      },  
      {  
        "price": 456.36,  
        "size": 23  
      }  
    ],  
    "bids": [  
      {  
        "price": 456.1,  
        "size": 42  
      },  
      {  
        "price": 456.09,  
        "size": 5  
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

Get current order book](/market-data/rest-api/order-book/get-current-order-book)[Next

Latest data](/market-data/rest-api/order-book/latest-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.