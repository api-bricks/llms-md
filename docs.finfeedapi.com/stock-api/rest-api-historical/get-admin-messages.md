Get Admin Messages | FinFeedAPI.com Documentation




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
* Get Admin Messages

Get Admin Messages
==================

```
GET

/v1/native/iex/admin/messages/:symbol
-------------------------------------
```

Get Admin Messages

Request[​](/stock-api/rest-api-historical/get-admin-messages#request "Direct link to Request")
----------------------------------------------------------------------------------------------

### Path Parameters

**symbol** stringrequired

The symbol identifier



### Query Parameters

**date** date-timerequired

Optional date in format YYYY-MM-DD (defaults to latest available data)

Responses[​](/stock-api/rest-api-historical/get-admin-messages#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------

* 200

successful operation

* application/json

* Schema
* Example (from schema)
* Example

**Schema**

* Array [

**trading\_status**

object

Represents the response DTO for trading status information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the trading status was recorded as DateTime

**is\_trading\_live** boolean

Gets whether the security is currently trading on IEX

**is\_trading\_halted** boolean

Gets whether the security is halted across all US equity markets

**is\_trading\_in\_order\_acceptance\_period** boolean

Gets whether the security is in Order Acceptance Period on IEX

**is\_trading\_paused** boolean

Gets whether the security is paused and in Order Acceptance Period on IEX

**is\_reason\_halt\_news\_pending** boolean

Gets whether the halt reason is News Pending

**is\_reason\_ipo\_not\_yet\_trading** boolean

Gets whether the halt reason is IPO Not Yet Trading

**is\_reason\_ipo\_deferred** boolean

Gets whether the halt reason is IPO Deferred

**is\_reason\_halt\_news\_dissemination** boolean

Gets whether the order acceptance period reason is Halt News Dissemination

**is\_reason\_ipo\_order\_acceptance\_period** boolean

Gets whether the order acceptance period reason is IPO Order Acceptance Period

**is\_reason\_ipo\_pre\_launch\_period** boolean

Gets whether the order acceptance period reason is IPO Pre-Launch Period

**is\_reason\_market\_wide\_circuit\_breaker\_level1** boolean

Gets whether the order acceptance period reason is Market-Wide Circuit Breaker Level 1 – Breached

**is\_reason\_market\_wide\_circuit\_breaker\_level2** boolean

Gets whether the order acceptance period reason is Market-Wide Circuit Breaker Level 2 – Breached

**is\_reason\_market\_wide\_circuit\_breaker\_level3** boolean

Gets whether the halt reason is Market-Wide Circuit Breaker Level 3 – Breached

**is\_reason\_not\_applicable** boolean

Gets whether the reason is Not Applicable

**is\_reason\_not\_available** boolean

Gets whether the halt reason is Not Available

**official\_price**

object

Represents the response DTO for official price information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the official price was recorded as DateTime

**price\_type** int32

Type of price as byte value

**price\_type\_code** stringnullable

Type of price as character string

**price\_type\_text** stringnullable

Human-readable description of the price type

**is\_price\_type\_opening** boolean

Indicates if the price type is 'IEX Official Opening Price' ('Q'/0x51).

**is\_price\_type\_closing** boolean

Indicates if the price type is 'IEX Official Closing Price' ('M'/0x4d).

**official\_price** double

Official price as decimal

**security\_event**

object

Represents the response DTO for security event information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the security event was recorded as DateTime

**security\_event** int32

Security event as byte value

**security\_event\_code** stringnullable

Security event as character string ('O' or 'C')

**security\_event\_text** stringnullable

Human-readable description of the security event

**is\_opening\_process\_complete** boolean

Indicates if the security event is 'Opening Process Complete' ('O'/0x4f).

**is\_closing\_process\_complete** boolean

Indicates if the security event is 'Closing Process Complete' ('C'/0x43).

**auction\_information**

object

Represents the response DTO for auction information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the auction data was recorded as DateTime

**auction\_type** int32

Type of auction as byte value

**auction\_type\_code** stringnullable

Type of auction as character string

**auction\_type\_text** stringnullable

Human-readable description of the auction type

**is\_auction\_type\_opening** boolean

Indicates if the auction type is 'Opening Auction' ('O'/0x4f).

**is\_auction\_type\_closing** boolean

Indicates if the auction type is 'Closing Auction' ('C'/0x43).

**is\_auction\_type\_ipo** boolean

Indicates if the auction type is 'IPO Auction' ('I'/0x49).

**is\_auction\_type\_halt** boolean

Indicates if the auction type is 'Halt Auction' ('H'/0x48).

**is\_auction\_type\_volatility** boolean

Indicates if the auction type is 'Volatility Auction' ('V'/0x56).

**paired\_shares** int32

Number of shares paired at the Reference Price

**reference\_price** double

Reference price as decimal

**indicative\_clearing\_price** double

Indicative clearing price as decimal

**imbalance\_shares** int32

Number of unpaired shares at the Reference Price

**imbalance\_side** int32

Side of the imbalance as byte value

**imbalance\_side\_code** stringnullable

Side of the imbalance as character string

**imbalance\_side\_text** stringnullable

Human-readable description of the imbalance side

**is\_imbalance\_side\_buy** boolean

Indicates if there is a buy-side imbalance ('B'/0x42).

**is\_imbalance\_side\_sell** boolean

Indicates if there is a sell-side imbalance ('S'/0x53).

**is\_imbalance\_side\_none** boolean

Indicates if there is no imbalance ('N'/0x4e).

**extension\_number** int32

Number of extensions to the auction

**scheduled\_auction\_time\_seconds** int32

Scheduled auction time in seconds since epoch

**scheduled\_auction\_time** date-time

Scheduled time for the auction as DateTime

**auction\_book\_clearing\_price** double

Auction book clearing price as decimal

**collar\_reference\_price** double

Collar reference price as decimal

**lower\_auction\_collar** double

Lower auction collar as decimal

**upper\_auction\_collar** double

Upper auction collar as decimal

**short\_sale\_price\_test**

object

Represents the response DTO for short sale price test status information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the short sale price test status was recorded as DateTime

**short\_sale\_price\_test\_status** int32

Short sale price test status as byte value

**short\_sale\_price\_test\_status\_code** stringnullable

Short sale price test status as hex string

**short\_sale\_price\_test\_status\_text** stringnullable

Human-readable description of the short sale price test status

**is\_short\_sale\_price\_test\_not\_in\_effect** boolean

Indicates if the short sale price test is not in effect

**is\_short\_sale\_price\_test\_in\_effect** boolean

Indicates if the short sale price test is in effect

**detail** int32

Detail of the short sale price test as byte value

**detail\_code** stringnullable

Detail of the short sale price test as character string

**detail\_text** stringnullable

Human-readable description of the short sale price test detail

**is\_detail\_no\_price\_test** boolean

Indicates if there is no price test in place

**is\_detail\_activated** boolean

Indicates if the short sale price test restriction is in effect due to an intraday price drop

**is\_detail\_continued** boolean

Indicates if the short sale price test restriction remains in effect from prior day

**is\_detail\_deactivated** boolean

Indicates if the short sale price test restriction is deactivated

**is\_detail\_not\_available** boolean

Indicates if the detail is not available

**operational\_halt\_status**

object

Represents the response DTO for operational halt status information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the operational halt status was recorded as DateTime

**operational\_halt\_status** int32

Operational halt status as byte value

**operational\_halt\_status\_code** stringnullable

Operational halt status as character string

**operational\_halt\_status\_text** stringnullable

Human-readable description of the operational halt status

**is\_operationally\_halted** boolean

Indicates if the status is 'IEX specific operational trading halt' ('O'/0x4f).

**is\_not\_operationally\_halted** boolean

Indicates if the status is 'Not operationally halted on IEX' ('N'/0x4e).

**retail\_liquidity\_indicator**

object

Represents the response DTO for retail liquidity indicator information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the retail liquidity indicator was recorded as DateTime

**retail\_liquidity\_indicator** int32

Retail liquidity indicator as byte value

**retail\_liquidity\_indicator\_code** stringnullable

Retail liquidity indicator as character string

**retail\_liquidity\_indicator\_text** stringnullable

Human-readable description of the retail liquidity indicator

**is\_retail\_indicator\_not\_applicable** boolean

Indicates if the indicator is 'Not Applicable' (' '/0x20).

**is\_retail\_indicator\_buy\_interest** boolean

Indicates if there is 'Buy interest for Retail' ('A'/0x41).

**is\_retail\_indicator\_sell\_interest** boolean

Indicates if there is 'Sell interest for Retail' ('B'/0x42).

**is\_retail\_indicator\_buy\_and\_sell\_interest** boolean

Indicates if there is 'Buy and sell interest for Retail' ('C'/0x43).

**system\_event**

object

Represents the response DTO for system event information

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

**security\_directory**

object

Represents the response DTO for security directory information

**symbol** stringnullable

The stock symbol

**timestamp\_nanos** int64

Original timestamp in nanoseconds since epoch

**timestamp** date-time

Time when the security directory information was recorded as DateTime

**flags** int32

Flags for the security

**round\_lot\_size** int32

Number of shares that represent a round lot

**adjusted\_poc\_price** double

Adjusted previous official closing price as decimal

**luld\_tier** int32

LULD tier as byte value

**luld\_tier\_code** stringnullable

LULD tier as numeric string

**luld\_tier\_text** stringnullable

Human-readable description of the LULD tier

**is\_luld\_tier\_not\_applicable** boolean

Indicates if LULD Tier is 'Not applicable' (0x0).

**is\_luld\_tier1** boolean

Indicates if LULD Tier is 'Tier 1 NMS Stock' (0x1).

**is\_luld\_tier2** boolean

Indicates if LULD Tier is 'Tier 2 NMS Stock' (0x2).

* ]

```
[  
  {  
    "trading_status": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.154Z",  
      "is_trading_live": true,  
      "is_trading_halted": true,  
      "is_trading_in_order_acceptance_period": true,  
      "is_trading_paused": true,  
      "is_reason_halt_news_pending": true,  
      "is_reason_ipo_not_yet_trading": true,  
      "is_reason_ipo_deferred": true,  
      "is_reason_halt_news_dissemination": true,  
      "is_reason_ipo_order_acceptance_period": true,  
      "is_reason_ipo_pre_launch_period": true,  
      "is_reason_market_wide_circuit_breaker_level1": true,  
      "is_reason_market_wide_circuit_breaker_level2": true,  
      "is_reason_market_wide_circuit_breaker_level3": true,  
      "is_reason_not_applicable": true,  
      "is_reason_not_available": true  
    },  
    "official_price": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.154Z",  
      "price_type": 0,  
      "price_type_code": "string",  
      "price_type_text": "string",  
      "is_price_type_opening": true,  
      "is_price_type_closing": true,  
      "official_price": 0  
    },  
    "security_event": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "security_event": 0,  
      "security_event_code": "string",  
      "security_event_text": "string",  
      "is_opening_process_complete": true,  
      "is_closing_process_complete": true  
    },  
    "auction_information": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "auction_type": 0,  
      "auction_type_code": "string",  
      "auction_type_text": "string",  
      "is_auction_type_opening": true,  
      "is_auction_type_closing": true,  
      "is_auction_type_ipo": true,  
      "is_auction_type_halt": true,  
      "is_auction_type_volatility": true,  
      "paired_shares": 0,  
      "reference_price": 0,  
      "indicative_clearing_price": 0,  
      "imbalance_shares": 0,  
      "imbalance_side": 0,  
      "imbalance_side_code": "string",  
      "imbalance_side_text": "string",  
      "is_imbalance_side_buy": true,  
      "is_imbalance_side_sell": true,  
      "is_imbalance_side_none": true,  
      "extension_number": 0,  
      "scheduled_auction_time_seconds": 0,  
      "scheduled_auction_time": "2025-08-12T06:08:07.155Z",  
      "auction_book_clearing_price": 0,  
      "collar_reference_price": 0,  
      "lower_auction_collar": 0,  
      "upper_auction_collar": 0  
    },  
    "short_sale_price_test": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "short_sale_price_test_status": 0,  
      "short_sale_price_test_status_code": "string",  
      "short_sale_price_test_status_text": "string",  
      "is_short_sale_price_test_not_in_effect": true,  
      "is_short_sale_price_test_in_effect": true,  
      "detail": 0,  
      "detail_code": "string",  
      "detail_text": "string",  
      "is_detail_no_price_test": true,  
      "is_detail_activated": true,  
      "is_detail_continued": true,  
      "is_detail_deactivated": true,  
      "is_detail_not_available": true  
    },  
    "operational_halt_status": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "operational_halt_status": 0,  
      "operational_halt_status_code": "string",  
      "operational_halt_status_text": "string",  
      "is_operationally_halted": true,  
      "is_not_operationally_halted": true  
    },  
    "retail_liquidity_indicator": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "retail_liquidity_indicator": 0,  
      "retail_liquidity_indicator_code": "string",  
      "retail_liquidity_indicator_text": "string",  
      "is_retail_indicator_not_applicable": true,  
      "is_retail_indicator_buy_interest": true,  
      "is_retail_indicator_sell_interest": true,  
      "is_retail_indicator_buy_and_sell_interest": true  
    },  
    "system_event": {  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "system_event": 0,  
      "system_event_code": "string",  
      "system_event_text": "string",  
      "is_system_event_start_of_messages": true,  
      "is_system_event_start_of_system_hours": true,  
      "is_system_event_start_of_regular_market_hours": true,  
      "is_system_event_end_of_regular_market_hours": true,  
      "is_system_event_end_of_system_hours": true,  
      "is_system_event_end_of_messages": true  
    },  
    "security_directory": {  
      "symbol": "string",  
      "timestamp_nanos": 0,  
      "timestamp": "2025-08-12T06:08:07.155Z",  
      "flags": 0,  
      "round_lot_size": 0,  
      "adjusted_poc_price": 0,  
      "luld_tier": 0,  
      "luld_tier_code": "string",  
      "luld_tier_text": "string",  
      "is_luld_tier_not_applicable": true,  
      "is_luld_tier1": true,  
      "is_luld_tier2": true  
    }  
  }  
]
```

```
[  
  {  
    "trading_status": {  
      "symbol": "PYPL",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "is_trading_live": true,  
      "is_trading_halted": false,  
      "is_trading_in_order_acceptance_period": false,  
      "is_trading_paused": false,  
      "is_reason_halt_news_pending": false,  
      "is_reason_ipo_not_yet_trading": false,  
      "is_reason_ipo_deferred": false,  
      "is_reason_halt_news_dissemination": false,  
      "is_reason_ipo_order_acceptance_period": false,  
      "is_reason_ipo_pre_launch_period": false,  
      "is_reason_market_wide_circuit_breaker_level1": false,  
      "is_reason_market_wide_circuit_breaker_level2": false,  
      "is_reason_market_wide_circuit_breaker_level3": false,  
      "is_reason_not_applicable": true,  
      "is_reason_not_available": false  
    }  
  },  
  {  
    "official_price": {  
      "symbol": "AAPL",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "price_type": 81,  
      "price_type_code": "Q",  
      "price_type_text": "IEX Official Opening Price",  
      "is_price_type_opening": true,  
      "is_price_type_closing": false,  
      "official_price": 12.3456  
    }  
  },  
  {  
    "security_event": {  
      "symbol": "CRM",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "security_event": 79,  
      "security_event_code": "O",  
      "security_event_text": "Opening Process Complete",  
      "is_opening_process_complete": true,  
      "is_closing_process_complete": false  
    }  
  },  
  {  
    "auction_information": {  
      "symbol": "AAPL",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "auction_type": 79,  
      "auction_type_code": "O",  
      "auction_type_text": "Opening Auction",  
      "is_auction_type_opening": true,  
      "is_auction_type_closing": false,  
      "is_auction_type_ipo": false,  
      "is_auction_type_halt": false,  
      "is_auction_type_volatility": false,  
      "paired_shares": 12500,  
      "reference_price": 156.42,  
      "indicative_clearing_price": 156.5,  
      "imbalance_shares": 2300,  
      "imbalance_side": 66,  
      "imbalance_side_code": "B",  
      "imbalance_side_text": "Buy-side imbalance",  
      "is_imbalance_side_buy": true,  
      "is_imbalance_side_sell": false,  
      "is_imbalance_side_none": false,  
      "extension_number": 0,  
      "scheduled_auction_time_seconds": 1754978943,  
      "scheduled_auction_time": "2025-08-12T06:09:03.0000000Z",  
      "auction_book_clearing_price": 156.45,  
      "collar_reference_price": 157,  
      "lower_auction_collar": 152.5,  
      "upper_auction_collar": 161.5  
    }  
  },  
  {  
    "short_sale_price_test": {  
      "symbol": "MSFT",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "short_sale_price_test_status": 1,  
      "short_sale_price_test_status_code": "1",  
      "short_sale_price_test_status_text": "Short Sale Price Test in Effect",  
      "is_short_sale_price_test_not_in_effect": false,  
      "is_short_sale_price_test_in_effect": true,  
      "detail": 65,  
      "detail_code": "A",  
      "detail_text": "Short sale price test restriction in effect due to an intraday price drop (Activated)",  
      "is_detail_no_price_test": false,  
      "is_detail_activated": true,  
      "is_detail_continued": false,  
      "is_detail_deactivated": false,  
      "is_detail_not_available": false  
    }  
  },  
  {  
    "operational_halt_status": {  
      "symbol": "AAPL",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "operational_halt_status": 79,  
      "operational_halt_status_code": "O",  
      "operational_halt_status_text": "IEX specific operational trading halt",  
      "is_operationally_halted": true,  
      "is_not_operationally_halted": false  
    }  
  },  
  {  
    "retail_liquidity_indicator": {  
      "symbol": "GOOG",  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "retail_liquidity_indicator": 65,  
      "retail_liquidity_indicator_code": "A",  
      "retail_liquidity_indicator_text": "Buy interest for Retail",  
      "is_retail_indicator_not_applicable": false,  
      "is_retail_indicator_buy_interest": true,  
      "is_retail_indicator_sell_interest": false,  
      "is_retail_indicator_buy_and_sell_interest": false  
    }  
  },  
  {  
    "system_event": {  
      "timestamp_nanos": 1754978643537000000,  
      "timestamp": "2025-08-12T06:04:03.5370000Z",  
      "system_event": 79,  
      "system_event_code": "O",  
      "system_event_text": "Start of Messages – Outside of heartbeat messages on the lower level protocol, the start of day message is the first message sent in any trading session.",  
      "is_system_event_start_of_messages": true,  
      "is_system_event_start_of_system_hours": false,  
      "is_system_event_start_of_regular_market_hours": false,  
      "is_system_event_end_of_regular_market_hours": false,  
      "is_system_event_end_of_system_hours": false,  
      "is_system_event_end_of_messages": false  
    }  
  },  
  {  
    "security_directory": {  
      "symbol": "INTC",  
      "timestamp_nanos": 1754978643538000000,  
      "timestamp": "2025-08-12T06:04:03.5380000Z",  
      "flags": 0,  
      "round_lot_size": 100,  
      "adjusted_poc_price": 35.36,  
      "luld_tier": 1,  
      "luld_tier_code": "1",  
      "luld_tier_text": "Tier 1 NMS Stock",  
      "is_luld_tier_not_applicable": false,  
      "is_luld_tier1": true,  
      "is_luld_tier2": false  
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

Introduction](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)[Next

Get Level-3 Order Book](/stock-api/rest-api-historical/get-level-3-order-book)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.