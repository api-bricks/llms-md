Latest data | FinFeedAPI.com Documentation




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
* Latest data

Latest data
===========

```
GET

/v1/ohlcv/exchange-symbol/:exchange_id/:symbol_id/latest
--------------------------------------------------------
```

Get OHLCV latest timeseries data returned in time descending order. Data can be requested by the period and for the specific symbol eg `BITSTAMP_SPOT_BTC_USD`, if you need to query timeseries by asset pairs eg. `BTC/USD`, then please reffer to the Exchange Rates Timeseries data

info

OHLCV Latest endpoint is just the shortcut to the OHLCV Historical endpoint with substituted `time_start` and `time_end` parameters.
The OHLCV Historical endpoint data can be delayed a few seconds. Use OHLCV real-time data stream to get data without delay.

Request[​](/stock-api/rest-api-historical/latest-data#request "Direct link to Request")
---------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

Exchange identifier of requested timeseries (from the Metadata -> Exchanges)

**symbol\_id** stringrequired

Symbol identifier of requested timeseries (from the Metadata -> Symbols)



### Query Parameters

**period\_id** stringrequired

Identifier of requested timeseries period (e.g. `5SEC` or `2MTH`)

**limit** int32

**Default value:** `100`

Amount of items to return (mininum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

Responses[​](/stock-api/rest-api-historical/latest-data#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json

* Schema
* Example (from schema)
* Example response

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

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.183Z",  
    "time_period_end": "2025-08-12T06:08:07.183Z",  
    "time_open": "2025-08-12T06:08:07.183Z",  
    "time_close": "2025-08-12T06:08:07.183Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2017-08-09T14:31:00.0000000Z",  
    "time_period_end": "2017-08-09T14:32:00.0000000Z",  
    "time_open": "2017-08-09T14:31:01.0000000Z",  
    "time_close": "2017-08-09T14:31:46.0000000Z",  
    "price_open": 3255.59,  
    "price_high": 3255.59,  
    "price_low": 3244.74,  
    "price_close": 3244.74,  
    "volume_traded": 16.90327455,  
    "trades_count": 31  
  },  
  {  
    "time_period_start": "2017-08-09T14:30:00.0000000Z",  
    "time_period_end": "2017-08-09T14:31:00.0000000Z",  
    "time_open": "2017-08-09T14:30:05.0000000Z",  
    "time_close": "2017-08-09T14:30:35.0000000Z",  
    "price_open": 3256,  
    "price_high": 3256.01,  
    "price_low": 3247,  
    "price_close": 3255.6,  
    "volume_traded": 58.13139792,  
    "trades_count": 33  
  }  
]
```

* Schema
* Example (from schema)
* Example response

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

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.183Z",  
    "time_period_end": "2025-08-12T06:08:07.183Z",  
    "time_open": "2025-08-12T06:08:07.183Z",  
    "time_close": "2025-08-12T06:08:07.183Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2017-08-09T14:31:00.0000000Z",  
    "time_period_end": "2017-08-09T14:32:00.0000000Z",  
    "time_open": "2017-08-09T14:31:01.0000000Z",  
    "time_close": "2017-08-09T14:31:46.0000000Z",  
    "price_open": 3255.59,  
    "price_high": 3255.59,  
    "price_low": 3244.74,  
    "price_close": 3244.74,  
    "volume_traded": 16.90327455,  
    "trades_count": 31  
  },  
  {  
    "time_period_start": "2017-08-09T14:30:00.0000000Z",  
    "time_period_end": "2017-08-09T14:31:00.0000000Z",  
    "time_open": "2017-08-09T14:30:05.0000000Z",  
    "time_close": "2017-08-09T14:30:35.0000000Z",  
    "price_open": 3256,  
    "price_high": 3256.01,  
    "price_low": 3247,  
    "price_close": 3255.6,  
    "volume_traded": 58.13139792,  
    "trades_count": 33  
  }  
]
```

* Schema
* Example (from schema)
* Example response

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

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.184Z",  
    "time_period_end": "2025-08-12T06:08:07.184Z",  
    "time_open": "2025-08-12T06:08:07.184Z",  
    "time_close": "2025-08-12T06:08:07.184Z",  
    "price_open": 0,  
    "price_high": 0,  
    "price_low": 0,  
    "price_close": 0,  
    "volume_traded": 0,  
    "trades_count": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2017-08-09T14:31:00.0000000Z",  
    "time_period_end": "2017-08-09T14:32:00.0000000Z",  
    "time_open": "2017-08-09T14:31:01.0000000Z",  
    "time_close": "2017-08-09T14:31:46.0000000Z",  
    "price_open": 3255.59,  
    "price_high": 3255.59,  
    "price_low": 3244.74,  
    "price_close": 3244.74,  
    "volume_traded": 16.90327455,  
    "trades_count": 31  
  },  
  {  
    "time_period_start": "2017-08-09T14:30:00.0000000Z",  
    "time_period_end": "2017-08-09T14:31:00.0000000Z",  
    "time_open": "2017-08-09T14:30:05.0000000Z",  
    "time_close": "2017-08-09T14:30:35.0000000Z",  
    "price_open": 3256,  
    "price_high": 3256.01,  
    "price_low": 3247,  
    "price_close": 3255.6,  
    "volume_traded": 58.13139792,  
    "trades_count": 33  
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

Historical data by exchange](/stock-api/rest-api-historical/historical-data-by-exchange)[Next

JSON RPC](/stock-api/jsonrpc-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.