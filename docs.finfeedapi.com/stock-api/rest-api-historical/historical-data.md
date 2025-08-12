Historical data | FinFeedAPI.com Documentation




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
* Historical data

Historical data
===============

```
GET

/v1/ohlcv/exchange-symbol/:exchange_id/:symbol_id/history
---------------------------------------------------------
```

Get OHLCV timeseries data returned in time ascending order.

Request[​](/stock-api/rest-api-historical/historical-data#request "Direct link to Request")
-------------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

Exchange identifier of requested timeseries (from the Metadata -> Exchanges)

**symbol\_id** stringrequired

Symbol identifier of requested timeseries (from the Metadata -> Symbols)



### Query Parameters

**period\_id** stringrequired

Identifier of requested timeseries period (e.g. `5SEC` or `2MTH`)

**time\_start** string

Timeseries starting time in ISO 8601

**time\_end** string

Timeseries ending time in ISO 8601

**limit** int32

**Default value:** `100`

Amount of items to return (mininum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

Responses[​](/stock-api/rest-api-historical/historical-data#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------

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
    "time_period_start": "2025-08-12T06:08:07.176Z",  
    "time_period_end": "2025-08-12T06:08:07.176Z",  
    "time_open": "2025-08-12T06:08:07.176Z",  
    "time_close": "2025-08-12T06:08:07.177Z",  
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
    "time_period_start": "2017-01-01T00:00:00.0000000Z",  
    "time_period_end": "2017-01-02T00:00:00.0000000Z",  
    "time_open": "2017-01-01T00:01:08.0000000Z",  
    "time_close": "2017-01-01T23:59:46.0000000Z",  
    "price_open": 966.34,  
    "price_high": 1005,  
    "price_low": 960.53,  
    "price_close": 997.75,  
    "volume_traded": 6850.59330859,  
    "trades_count": 7815  
  },  
  {  
    "time_period_start": "2017-01-02T00:00:00.0000000Z",  
    "time_period_end": "2017-01-03T00:00:00.0000000Z",  
    "time_open": "2017-01-02T00:00:05.0000000Z",  
    "time_close": "2017-01-02T23:59:37.0000000Z",  
    "price_open": 997.75,  
    "price_high": 1032,  
    "price_low": 990.01,  
    "price_close": 1012.54,  
    "volume_traded": 8167.38103018,  
    "trades_count": 7871  
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
    "time_period_start": "2025-08-12T06:08:07.177Z",  
    "time_period_end": "2025-08-12T06:08:07.177Z",  
    "time_open": "2025-08-12T06:08:07.177Z",  
    "time_close": "2025-08-12T06:08:07.177Z",  
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
    "time_period_start": "2017-01-01T00:00:00.0000000Z",  
    "time_period_end": "2017-01-02T00:00:00.0000000Z",  
    "time_open": "2017-01-01T00:01:08.0000000Z",  
    "time_close": "2017-01-01T23:59:46.0000000Z",  
    "price_open": 966.34,  
    "price_high": 1005,  
    "price_low": 960.53,  
    "price_close": 997.75,  
    "volume_traded": 6850.59330859,  
    "trades_count": 7815  
  },  
  {  
    "time_period_start": "2017-01-02T00:00:00.0000000Z",  
    "time_period_end": "2017-01-03T00:00:00.0000000Z",  
    "time_open": "2017-01-02T00:00:05.0000000Z",  
    "time_close": "2017-01-02T23:59:37.0000000Z",  
    "price_open": 997.75,  
    "price_high": 1032,  
    "price_low": 990.01,  
    "price_close": 1012.54,  
    "volume_traded": 8167.38103018,  
    "trades_count": 7871  
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
    "time_period_start": "2025-08-12T06:08:07.177Z",  
    "time_period_end": "2025-08-12T06:08:07.177Z",  
    "time_open": "2025-08-12T06:08:07.177Z",  
    "time_close": "2025-08-12T06:08:07.177Z",  
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
    "time_period_start": "2017-01-01T00:00:00.0000000Z",  
    "time_period_end": "2017-01-02T00:00:00.0000000Z",  
    "time_open": "2017-01-01T00:01:08.0000000Z",  
    "time_close": "2017-01-01T23:59:46.0000000Z",  
    "price_open": 966.34,  
    "price_high": 1005,  
    "price_low": 960.53,  
    "price_close": 997.75,  
    "volume_traded": 6850.59330859,  
    "trades_count": 7815  
  },  
  {  
    "time_period_start": "2017-01-02T00:00:00.0000000Z",  
    "time_period_end": "2017-01-03T00:00:00.0000000Z",  
    "time_open": "2017-01-02T00:00:05.0000000Z",  
    "time_close": "2017-01-02T23:59:37.0000000Z",  
    "price_open": 997.75,  
    "price_high": 1032,  
    "price_low": 990.01,  
    "price_close": 1012.54,  
    "volume_traded": 8167.38103018,  
    "trades_count": 7871  
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

List all periods](/stock-api/rest-api-historical/list-all-periods)[Next

Historical data by exchange](/stock-api/rest-api-historical/historical-data-by-exchange)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.