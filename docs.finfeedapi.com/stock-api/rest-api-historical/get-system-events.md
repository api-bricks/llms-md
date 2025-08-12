Get System Events | FinFeedAPI.com Documentation




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
* Get System Events

Get System Events
=================

```
GET

/v1/native/iex/admin/system-event
---------------------------------
```

Get System Events

Request[​](/stock-api/rest-api-historical/get-system-events#request "Direct link to Request")
---------------------------------------------------------------------------------------------

### Query Parameters

**date** date-timerequired

Date in format YYYY-MM-DD

Responses[​](/stock-api/rest-api-historical/get-system-events#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------------

* 200

successful operation

* application/json

* Schema
* Example (from schema)

**Schema**

* Array [

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the system event was recorded as DateTime

**system\_event** int32

System event as byte value

**system\_event\_code** stringnullable

System event as string

**system\_event\_text** stringnullable

Human-readable description of the system event

**is\_system\_event\_start\_of\_messages** boolean

Indicates if the system event is 'Start of Messages' (O).
Outside of heartbeat messages on the lower level protocol,
the start of day message is the first message sent in any trading session.

**is\_system\_event\_start\_of\_system\_hours** boolean

Indicates if the system event is 'Start of System Hours' (S).
This message indicates that IEX is open and ready to start accepting orders.

**is\_system\_event\_start\_of\_regular\_market\_hours** boolean

Indicates if the system event is 'Start of Regular Market Hours' (R).
This message indicates that DAY and GTX orders, as well as market orders and pegged orders,
are available for execution on IEX.

**is\_system\_event\_end\_of\_regular\_market\_hours** boolean

Indicates if the system event is 'End of Regular Market Hours' (M).
This message indicates that DAY orders, market orders, and pegged orders
are no longer accepted by IEX.

**is\_system\_event\_end\_of\_system\_hours** boolean

Indicates if the system event is 'End of System Hours' (E).
This message indicates that IEX is now closed and will not accept
any new orders during this trading session. It is still possible
to receive messages after the end of day.

**is\_system\_event\_end\_of\_messages** boolean

Indicates if the system event is 'End of Messages' (C).
This is always the last message sent in any trading session.

* ]

```
[  
  {  
    "timestamp_nanos": 0,  
    "timestamp": "2025-08-12T06:08:07.172Z",  
    "system_event": 0,  
    "system_event_code": "string",  
    "system_event_text": "string",  
    "is_system_event_start_of_messages": true,  
    "is_system_event_start_of_system_hours": true,  
    "is_system_event_start_of_regular_market_hours": true,  
    "is_system_event_end_of_regular_market_hours": true,  
    "is_system_event_end_of_system_hours": true,  
    "is_system_event_end_of_messages": true  
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

Get Level-1 Quotes](/stock-api/rest-api-historical/get-level-1-quotes)[Next

Get Trades](/stock-api/rest-api-historical/get-trades)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.