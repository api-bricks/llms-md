Get Level-1 Quotes | FinFeedAPI.com Documentation




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
* Get Level-1 Quotes

Get Level-1 Quotes
==================

```
GET

/v1/native/iex/level1-quote/:symbol
-----------------------------------
```

Get Level-1 Quotes

Request[​](/stock-api/rest-api-historical/get-level-1-quotes#request "Direct link to Request")
----------------------------------------------------------------------------------------------

### Path Parameters

**symbol** stringrequired

The symbol identifier



### Query Parameters

**date** date-timerequired

Optional date in format YYYY-MM-DD (defaults to latest available data)

Responses[​](/stock-api/rest-api-historical/get-level-1-quotes#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------

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

Time when the quote update was recorded as DateTime

**is\_symbol\_available** boolean

Gets whether the symbol is available for trading
True if active, False if halted, paused, or otherwise not available

**is\_pre\_post\_market\_session** boolean

Gets whether the market session is regular or pre/post-market
True if pre/post-market session, False if regular market session

**ask\_size** int32

Ask size in number of shares

**ask\_price** double

Ask price as decimal

**bid\_price** double

Bid price as decimal

**bid\_size** int32

Bid size in number of shares

* ]

```
[  
  {  
    "symbol": "string",  
    "timestamp_nanos": 0,  
    "timestamp": "2025-08-12T06:08:07.167Z",  
    "is_symbol_available": true,  
    "is_pre_post_market_session": true,  
    "ask_size": 0,  
    "ask_price": 0,  
    "bid_price": 0,  
    "bid_size": 0  
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

Get Level-2 Price Level Book](/stock-api/rest-api-historical/get-level-2-price-level-book)[Next

Get System Events](/stock-api/rest-api-historical/get-system-events)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.