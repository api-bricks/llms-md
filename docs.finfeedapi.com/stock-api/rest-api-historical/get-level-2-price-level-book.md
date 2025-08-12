Get Level-2 Price Level Book | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Stock Data API](/stock-api/)
* [Authentication](/stock-api/authentication)
* [Metadata Tables](/stock-api/metadata-tables/introduction)
* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)

  + [Introduction](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
  + [Native IEX](/stock-api/rest-api-historical/get-admin-messages)

    - [Get Admin Messages](/stock-api/rest-api-historical/get-admin-messages)
    - [Get Level-3 Order Book](/stock-api/rest-api-historical/get-level-3-order-book)
    - [Get Level-2 Price Level Book](/stock-api/rest-api-historical/get-level-2-price-level-book)
    - [Get Level-1 Quotes](/stock-api/rest-api-historical/get-level-1-quotes)
    - [Get System Events](/stock-api/rest-api-historical/get-system-events)
    - [Get Trades](/stock-api/rest-api-historical/get-trades)
  + [Metadata](/stock-api/rest-api-historical/list-of-exchanges)
  + [Ohlcv](/stock-api/rest-api-historical/list-all-periods)
* [JSON RPC](/stock-api/jsonrpc-api)

* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
* Native IEX
* Get Level-2 Price Level Book

Get Level-2 Price Level Book
============================

```
GET

/v1/native/iex/level2-price-level-update/:symbol
------------------------------------------------
```

Get Level-2 Price Level Book

Request[​](/stock-api/rest-api-historical/get-level-2-price-level-book#request "Direct link to Request")
--------------------------------------------------------------------------------------------------------

### Path Parameters

**symbol** stringrequired

The symbol identifier



### Query Parameters

**date** date-timerequired

Optional date in format YYYY-MM-DD (defaults to latest available data)

Responses[​](/stock-api/rest-api-historical/get-level-2-price-level-book#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------------------

* 200

successful operation

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the price level update was recorded as DateTime

**is\_side\_buy** boolean

Indicates if this is a price level update for the Buy Side.

**is\_event\_processing\_complete** boolean

Indicates if event processing is complete.

**size** int32

Aggregate quoted size at the price level

**price** double

Price level as decimal

* ]

```
[  
  {  
    "symbol": "string",  
    "timestamp_nanos": 0,  
    "timestamp": "2025-08-12T06:08:07.166Z",  
    "is_side_buy": true,  
    "is_event_processing_complete": true,  
    "size": 0,  
    "price": 0  
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

Get Level-3 Order Book](/stock-api/rest-api-historical/get-level-3-order-book)[Next

Get Level-1 Quotes](/stock-api/rest-api-historical/get-level-1-quotes)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.