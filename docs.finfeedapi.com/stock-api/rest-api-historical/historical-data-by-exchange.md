Historical data by exchange | FinFeedAPI.com Documentation




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
  + [Metadata](/stock-api/rest-api-historical/list-of-exchanges)
  + [Ohlcv](/stock-api/rest-api-historical/list-all-periods)

    - [List all periods](/stock-api/rest-api-historical/list-all-periods)
    - [Historical data](/stock-api/rest-api-historical/historical-data)
    - [Historical data by exchange](/stock-api/rest-api-historical/historical-data-by-exchange)
    - [Latest data](/stock-api/rest-api-historical/latest-data)
* [JSON RPC](/stock-api/jsonrpc-api)

* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
* Ohlcv
* Historical data by exchange

Historical data by exchange
===========================

```
GET

/v1/ohlcv/exchange/:exchange_id/history
---------------------------------------
```

Get OHLCV timeseries data returned in time ascending order. Data can be requested by the period and for the specific exchange.

Request[​](/stock-api/rest-api-historical/historical-data-by-exchange#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------

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

Responses[​](/stock-api/rest-api-historical/historical-data-by-exchange#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

Gets or sets the start time of the time period.

**time\_period\_end** date-time

Gets or sets the end time of the time period.

**time\_open** date-timenullable

Gets or sets the time when the price opened.

**time\_close** date-timenullable

Gets or sets the time when the price closed.

**price\_open** doublenullable

Gets or sets the opening price.

**price\_high** doublenullable

Gets or sets the highest price during the time period.

**price\_low** doublenullable

Gets or sets the lowest price during the time period.

**price\_close** doublenullable

Gets or sets the closing price.

**volume\_traded** double

Gets or sets the total volume traded during the time period.

**trades\_count** int64

Gets or sets the number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.181Z",  
    "time_period_end": "2025-08-12T06:08:07.181Z",  
    "time_open": "2025-08-12T06:08:07.181Z",  
    "time_close": "2025-08-12T06:08:07.181Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string"  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

Gets or sets the start time of the time period.

**time\_period\_end** date-time

Gets or sets the end time of the time period.

**time\_open** date-timenullable

Gets or sets the time when the price opened.

**time\_close** date-timenullable

Gets or sets the time when the price closed.

**price\_open** doublenullable

Gets or sets the opening price.

**price\_high** doublenullable

Gets or sets the highest price during the time period.

**price\_low** doublenullable

Gets or sets the lowest price during the time period.

**price\_close** doublenullable

Gets or sets the closing price.

**volume\_traded** double

Gets or sets the total volume traded during the time period.

**trades\_count** int64

Gets or sets the number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.181Z",  
    "time_period_end": "2025-08-12T06:08:07.181Z",  
    "time_open": "2025-08-12T06:08:07.181Z",  
    "time_close": "2025-08-12T06:08:07.181Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string"  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**time\_period\_start** date-time

Gets or sets the start time of the time period.

**time\_period\_end** date-time

Gets or sets the end time of the time period.

**time\_open** date-timenullable

Gets or sets the time when the price opened.

**time\_close** date-timenullable

Gets or sets the time when the price closed.

**price\_open** doublenullable

Gets or sets the opening price.

**price\_high** doublenullable

Gets or sets the highest price during the time period.

**price\_low** doublenullable

Gets or sets the lowest price during the time period.

**price\_close** doublenullable

Gets or sets the closing price.

**volume\_traded** double

Gets or sets the total volume traded during the time period.

**trades\_count** int64

Gets or sets the number of trades executed during the time period.

**symbol\_id\_exchange** stringnullable

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.181Z",  
    "time_period_end": "2025-08-12T06:08:07.181Z",  
    "time_open": "2025-08-12T06:08:07.181Z",  
    "time_close": "2025-08-12T06:08:07.181Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0,  
    "symbol_id_exchange": "string"  
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

Historical data](/stock-api/rest-api-historical/historical-data)[Next

Latest data](/stock-api/rest-api-historical/latest-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.