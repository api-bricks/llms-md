Current depth of the order book | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/order-book/current-depth-of-the-order-book)

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
* Current depth of the order book

Current depth of the order book
===============================

```
GET

/v1/orderbooks/:symbol_id/depth/current
---------------------------------------
```

Retrieves the current depth of the order book for the specified symbol.

Request[​](/market-data/rest-api/order-book/current-depth-of-the-order-book#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------------

### Path Parameters

**symbol\_id** stringrequired

The symbol ID (from the Metadata -> Symbols)



### Query Parameters

**limit\_levels** int32

The maximum number of levels to include in the response.

Responses[​](/market-data/rest-api/order-book/current-depth-of-the-order-book#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**ask\_levels** int64

The number of ask levels in the order book.

**bid\_levels** int64

The number of bid levels in the order book.

**ask\_depth** double

The depth of the ask side of the order book.

**bid\_depth** double

The depth of the bid side of the order book.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.957Z",  
  "time_coinapi": "2025-08-12T06:09:08.957Z",  
  "ask_levels": 0,  
  "bid_levels": 0,  
  "ask_depth": 0,  
  "bid_depth": 0  
}
```

* Schema
* Example (from schema)

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**ask\_levels** int64

The number of ask levels in the order book.

**bid\_levels** int64

The number of bid levels in the order book.

**ask\_depth** double

The depth of the ask side of the order book.

**bid\_depth** double

The depth of the bid side of the order book.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.957Z",  
  "time_coinapi": "2025-08-12T06:09:08.957Z",  
  "ask_levels": 0,  
  "bid_levels": 0,  
  "ask_depth": 0,  
  "bid_depth": 0  
}
```

* Schema
* Example (from schema)

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**ask\_levels** int64

The number of ask levels in the order book.

**bid\_levels** int64

The number of bid levels in the order book.

**ask\_depth** double

The depth of the ask side of the order book.

**bid\_depth** double

The depth of the bid side of the order book.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.957Z",  
  "time_coinapi": "2025-08-12T06:09:08.957Z",  
  "ask_levels": 0,  
  "bid_levels": 0,  
  "ask_depth": 0,  
  "bid_depth": 0  
}
```

* Schema
* Example (from schema)

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**ask\_levels** int64

The number of ask levels in the order book.

**bid\_levels** int64

The number of bid levels in the order book.

**ask\_depth** double

The depth of the ask side of the order book.

**bid\_depth** double

The depth of the bid side of the order book.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.958Z",  
  "time_coinapi": "2025-08-12T06:09:08.958Z",  
  "ask_levels": 0,  
  "bid_levels": 0,  
  "ask_depth": 0,  
  "bid_depth": 0  
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

Introduction](/market-data/rest-api/order-book/coinapi-market-data-rest-api)[Next

Get current order book](/market-data/rest-api/order-book/get-current-order-book)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.