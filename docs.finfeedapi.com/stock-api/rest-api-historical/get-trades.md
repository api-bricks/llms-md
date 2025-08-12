Get Trades | FinFeedAPI.com Documentation




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
* Get Trades

Get Trades
==========

```
GET

/v1/native/iex/trade/:symbol
----------------------------
```

Get Trades

Request[​](/stock-api/rest-api-historical/get-trades#request "Direct link to Request")
--------------------------------------------------------------------------------------

### Path Parameters

**symbol** stringrequired

The symbol identifier



### Query Parameters

**date** date-timerequired

Optional date in format YYYY-MM-DD (defaults to latest available data)

Responses[​](/stock-api/rest-api-historical/get-trades#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------

* 200

successful operation

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**is\_trade\_break** boolean

Indicates if this record represents a trade break (true) or a trade report (false).

**symbol** stringnullable

The stock symbol.

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch.

**timestamp** date-time

Time when the event was recorded as DateTime (UTC).

**size** int32

Trade volume (or break volume) in number of shares.

**price** double

Trade price (or break price) as decimal.

**trade\_id** int64

IEX trade identifier (same for report and its corresponding break).

**is\_intermarket\_sweep** boolean

Bit 7 (Mask 0x80): Intermarket Sweep Flag.
True: Intermarket Sweep Order ("ISO").
False: Non-Intermarket Sweep Order.

**is\_extended\_hours\_trade** boolean

Bit 6 (Mask 0x40): Extended Hours Flag.
True: Extended Hours Trade (i.e., Form T sale condition).
False: Regular Market Session Trade.

**is\_odd\_lot\_trade** boolean

Bit 5 (Mask 0x20): Odd Lot Flag.
True: Odd Lot Trade.
False: Round or Mixed Lot Trade.

**is\_trade\_through\_exempt** boolean

Bit 4 (Mask 0x10): Trade Through Exempt Flag.
True: Trade is not subject to Rule 611 (Trade Through) of SEC Reg. NMS.
False: Trade is subject to Rule 611 (Trade Through) of SEC Reg. NMS.
Applied when the taking order was an ISO that traded through a protected quotation,
OR the NBBO was crossed at the time of the trade,
OR the trade occurred through a self-helped venue's quotation,
OR the trade was a single-price cross.

**is\_single\_price\_cross\_trade** boolean

Bit 3 (Mask 0x08): Single-price Cross Trade Flag.
True: Trade resulting from a single-price cross.
False: Execution during continuous trading.

* ]

```
[  
  {  
    "is_trade_break": true,  
    "symbol": "string",  
    "timestamp_nanos": 0,  
    "timestamp": "2025-08-12T06:08:07.185Z",  
    "size": 0,  
    "price": 0,  
    "trade_id": 0,  
    "is_intermarket_sweep": true,  
    "is_extended_hours_trade": true,  
    "is_odd_lot_trade": true,  
    "is_trade_through_exempt": true,  
    "is_single_price_cross_trade": true  
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

Get System Events](/stock-api/rest-api-historical/get-system-events)[Next

List of exchanges](/stock-api/rest-api-historical/list-of-exchanges)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.