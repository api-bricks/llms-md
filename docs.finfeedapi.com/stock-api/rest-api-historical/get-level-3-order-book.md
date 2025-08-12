Get Level-3 Order Book | FinFeedAPI.com Documentation




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
* Get Level-3 Order Book

Get Level-3 Order Book
======================

```
GET

/v1/native/iex/level3-order-book/:symbol
----------------------------------------
```

Get Level-3 Order Book

Request[​](/stock-api/rest-api-historical/get-level-3-order-book#request "Direct link to Request")
--------------------------------------------------------------------------------------------------

### Path Parameters

**symbol** stringrequired

The symbol identifier



### Query Parameters

**date** date-timerequired

Optional date in format YYYY-MM-DD (defaults to latest available data)

Responses[​](/stock-api/rest-api-historical/get-level-3-order-book#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------------

* 200

successful operation

* application/json

* Schema
* Example (from schema)
* Example

**Schema**

* Array [

**add\_order**

object

Represents the response DTO for add order information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the order was added as DateTime (UTC)

**is\_side\_buy** boolean

Indicates if this is a Buy order ('8'/0x38).

**size** int32

Quoted size in number of shares

**price** double

Price as decimal

**order\_id** int64

Order identifier

**delete\_order**

object

Represents the response DTO for order delete information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the order was deleted as DateTime

**order\_id\_reference** int64

Order identifier reference

**modify\_order**

object

Represents the response DTO for order modify information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the order was modified as DateTime (UTC)

**order\_id\_reference** int64

Order identifier reference

**is\_priority\_reset** boolean

Indicates if priority is reseted

**size** int32

New total quoted size in number of shares

**price** double

Price as decimal

**executed\_order**

object

Represents the response DTO for order executed information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the order was executed as DateTime

**order\_id\_reference** int64

Order identifier reference

**sale\_condition\_flags** int32

Sale condition flags for the execution as byte value

**is\_intermarket\_sweep** boolean

Bit 7 (Mask 0x80): Intermarket Sweep Flag
True: Intermarket Sweep Order ("ISO")
False: Non-Intermarket Sweep Order

**is\_extended\_hours\_trade** boolean

Bit 6 (Mask 0x40): Extended Hours Flag
True: Extended Hours Trade (i.e., Form T sale condition)
False: Regular Market Session Trade

**is\_odd\_lot\_trade** boolean

Bit 5 (Mask 0x20): Odd Lot Flag
True: Odd Lot Trade
False: Round or Mixed Lot Trade

**is\_trade\_through\_exempt** boolean

Bit 4 (Mask 0x10): Trade Through Exempt Flag
True: Trade is not subject to Rule 611 (Trade Through) of SEC Reg. NMS
False: Trade is subject to Rule 611 (Trade Through) of SEC Reg. NMS

**is\_single\_price\_cross\_trade** boolean

Bit 3 (Mask 0x08): Single-price Cross Trade Flag
True: Trade resulting from a single-price cross
False: Execution during continuous trading

**size** int32

Trade volume in number of shares

**price** double

Execution price as decimal

**trade\_id** int64

IEX trade identifier

**clear\_book**

object

Represents the response DTO for clear book information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the book was cleared as DateTime

* ]

```
[  
  {  
    "add_order": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.164Z",  
      "is_side_buy": true,  
      "size": 0,  
      "price": 0,  
      "order_id": 0  
    },  
    "delete_order": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.164Z",  
      "order_id_reference": 0  
    },  
    "modify_order": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.164Z",  
      "order_id_reference": 0,  
      "is_priority_reset": true,  
      "size": 0,  
      "price": 0  
    },  
    "executed_order": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.164Z",  
      "order_id_reference": 0,  
      "sale_condition_flags": 0,  
      "is_intermarket_sweep": true,  
      "is_extended_hours_trade": true,  
      "is_odd_lot_trade": true,  
      "is_trade_through_exempt": true,  
      "is_single_price_cross_trade": true,  
      "size": 0,  
      "price": 0,  
      "trade_id": 0  
    },  
    "clear_book": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.164Z"  
    }  
  }  
]
```

```
[  
  {  
    "add_order": {  
      "symbol": "AAPL",  
      "timestamp_nanos": 1754978643549000000,  
      "timestamp": "2025-08-12T06:04:03.5490000Z",  
      "is_side_buy": true,  
      "size": 100,  
      "price": 176.42,  
      "order_id": 123456789  
    }  
  },  
  {  
    "delete_order": {  
      "symbol": "TSLA",  
      "timestamp_nanos": 1754978643549000000,  
      "timestamp": "2025-08-12T06:04:03.5490000Z",  
      "order_id_reference": 987654321  
    }  
  },  
  {  
    "modify_order": {  
      "symbol": "NFLX",  
      "timestamp_nanos": 1754978643549000000,  
      "timestamp": "2025-08-12T06:04:03.5490000Z",  
      "order_id_reference": 789456123,  
      "is_priority_reset": false,  
      "size": 150,  
      "price": 625.85  
    }  
  },  
  {  
    "executed_order": {  
      "symbol": "META",  
      "timestamp_nanos": 1754978643549000000,  
      "timestamp": "2025-08-12T06:04:03.5490000Z",  
      "order_id_reference": 555123456,  
      "sale_condition_flags": 0,  
      "is_intermarket_sweep": false,  
      "is_extended_hours_trade": false,  
      "is_odd_lot_trade": false,  
      "is_trade_through_exempt": false,  
      "is_single_price_cross_trade": false,  
      "size": 200,  
      "price": 421,  
      "trade_id": 123987456  
    }  
  },  
  {  
    "clear_book": {  
      "symbol": "MSFT",  
      "timestamp_nanos": 1754978643549000000,  
      "timestamp": "2025-08-12T06:04:03.5490000Z"  
    }  
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

Get Admin Messages](/stock-api/rest-api-historical/get-admin-messages)[Next

Get Level-2 Price Level Book](/stock-api/rest-api-historical/get-level-2-price-level-book)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.