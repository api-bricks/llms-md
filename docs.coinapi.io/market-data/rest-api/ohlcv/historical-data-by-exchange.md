Historical data by exchange | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/ohlcv/historical-data-by-exchange)

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

    - [Introduction](/market-data/rest-api/ohlcv/coinapi-market-data-rest-api)
    - [Historical data by exchange](/market-data/rest-api/ohlcv/historical-data-by-exchange)
    - [Historical data](/market-data/rest-api/ohlcv/historical-data)
    - [Latest data](/market-data/rest-api/ohlcv/latest-data)
    - [List all periods](/market-data/rest-api/ohlcv/list-all-periods)
  + [Options](/market-data/rest-api/options/)
  + [Order Book](/market-data/rest-api/order-book/)
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
* [Ohlcv](/market-data/rest-api/ohlcv/)
* Historical data by exchange

Historical data by exchange
===========================

```
GET

/v1/ohlcv/exchanges/:exchange_id/history
----------------------------------------
```

Get OHLCV timeseries data returned in time ascending order. Data can be requested by the period and for the specific exchange eg `BITSTAMP`

info

The OHLCV Historical endpoint data can be delayed a few seconds. Use OHLCV real-time data stream to get data without delay.
The difference between `time_end` and `time_start` cannot be higher than 1 day.
The `period_id` cannot be higher than `1DAY`.

Request[​](/market-data/rest-api/ohlcv/historical-data-by-exchange#request "Direct link to Request")
----------------------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

Exchange identifier of requested timeseries (from the Metadata -> Exchanges)



### Query Parameters

**period\_id** stringrequired

Identifier of requested timeseries period (e.g. `5SEC` or `1DAY`)

**time\_start** stringrequired

Timeseries starting time in ISO 8601

**time\_end** stringrequired

Timeseries ending time in ISO 8601

Responses[​](/market-data/rest-api/ohlcv/historical-data-by-exchange#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

The start time of the time period.

**time\_period\_end** date-time

The end time of the time period.

**time\_open** date-timenullable

The time when the price opened.

**time\_close** date-timenullable

The time when the price closed.

**price\_open** doublenullable

The opening price.

**price\_high** doublenullable

The highest price during the time period.

**price\_low** doublenullable

The lowest price during the time period.

**price\_close** doublenullable

The closing price.

**volume\_traded** double

The total volume traded during the time period.

**trades\_count** int64

The number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

**symbol\_id\_coinapi** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:09:08.910Z",  
    "time_period_end": "2025-08-12T06:09:08.910Z",  
    "time_open": "2025-08-12T06:09:08.910Z",  
    "time_close": "2025-08-12T06:09:08.910Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string",  
    "symbol_id_coinapi": "string"  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

The start time of the time period.

**time\_period\_end** date-time

The end time of the time period.

**time\_open** date-timenullable

The time when the price opened.

**time\_close** date-timenullable

The time when the price closed.

**price\_open** doublenullable

The opening price.

**price\_high** doublenullable

The highest price during the time period.

**price\_low** doublenullable

The lowest price during the time period.

**price\_close** doublenullable

The closing price.

**volume\_traded** double

The total volume traded during the time period.

**trades\_count** int64

The number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

**symbol\_id\_coinapi** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:09:08.910Z",  
    "time_period_end": "2025-08-12T06:09:08.910Z",  
    "time_open": "2025-08-12T06:09:08.910Z",  
    "time_close": "2025-08-12T06:09:08.910Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string",  
    "symbol_id_coinapi": "string"  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

The start time of the time period.

**time\_period\_end** date-time

The end time of the time period.

**time\_open** date-timenullable

The time when the price opened.

**time\_close** date-timenullable

The time when the price closed.

**price\_open** doublenullable

The opening price.

**price\_high** doublenullable

The highest price during the time period.

**price\_low** doublenullable

The lowest price during the time period.

**price\_close** doublenullable

The closing price.

**volume\_traded** double

The total volume traded during the time period.

**trades\_count** int64

The number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

**symbol\_id\_coinapi** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:09:08.910Z",  
    "time_period_end": "2025-08-12T06:09:08.910Z",  
    "time_open": "2025-08-12T06:09:08.910Z",  
    "time_close": "2025-08-12T06:09:08.910Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string",  
    "symbol_id_coinapi": "string"  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

The start time of the time period.

**time\_period\_end** date-time

The end time of the time period.

**time\_open** date-timenullable

The time when the price opened.

**time\_close** date-timenullable

The time when the price closed.

**price\_open** doublenullable

The opening price.

**price\_high** doublenullable

The highest price during the time period.

**price\_low** doublenullable

The lowest price during the time period.

**price\_close** doublenullable

The closing price.

**volume\_traded** double

The total volume traded during the time period.

**trades\_count** int64

The number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

**symbol\_id\_coinapi** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:09:08.910Z",  
    "time_period_end": "2025-08-12T06:09:08.910Z",  
    "time_open": "2025-08-12T06:09:08.910Z",  
    "time_close": "2025-08-12T06:09:08.910Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string",  
    "symbol_id_coinapi": "string"  
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

Introduction](/market-data/rest-api/ohlcv/coinapi-market-data-rest-api)[Next

Historical data](/market-data/rest-api/ohlcv/historical-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.