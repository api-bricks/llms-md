Timeseries data | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Currencies API](/currencies-api/)
* [Authentication](/currencies-api/authentication)
* [Metadata Tables](/currencies-api/metadata-tables/introduction)
* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)

  + [Introduction](/currencies-api/rest-api-historical/fx-historical-rest-api)
  + [Exchange Rates](/currencies-api/rest-api-historical/exchange-rates)

    - [Get specific rate](/currencies-api/rest-api-historical/get-specific-rate)
    - [Get all current rates](/currencies-api/rest-api-historical/get-all-current-rates)
    - [Timeseries periods](/currencies-api/rest-api-historical/timeseries-periods)
    - [Timeseries data](/currencies-api/rest-api-historical/timeseries-data)
  + [Metadata](/currencies-api/rest-api-historical/metadata)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Exchange Rates](/currencies-api/rest-api-historical/exchange-rates)
* Timeseries data

Timeseries data
===============

```
GET

/v1/exchangerate/:asset_id_base/:asset_id_quote/history
-------------------------------------------------------
```

Get the historical exchange rates between two assets in the form of the timeseries.

Request[​](/currencies-api/rest-api-historical/timeseries-data#request "Direct link to Request")
------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id\_base** stringrequired

Requested exchange rates base asset identifier (from the Metadata -> Assets)

**asset\_id\_quote** stringrequired

Requested exchange rates base asset identifier (from the Metadata -> Assets)



### Query Parameters

**period\_id** string

Identifier of requested timeseries period (required, e.g. `5SEC` or `1HRS`)

**time\_start** string

Timeseries starting time in ISO 8601 (required)

**time\_end** string

Timeseries ending time in ISO 8601 (required)

**limit** int32

**Default value:** `100`

Amount of items to return (optional, mininum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

Responses[​](/currencies-api/rest-api-historical/timeseries-data#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------

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

Gets or sets the start time of the period.

**time\_period\_end** date-time

Gets or sets the end time of the period.

**time\_open** date-timenullable

Gets or sets the opening time of the period.

**time\_close** date-timenullable

Gets or sets the closing time of the period.

**rate\_open** doublenullable

Gets or sets the opening rate for the period.

**rate\_high** doublenullable

Gets or sets the highest rate for the period.

**rate\_low** doublenullable

Gets or sets the lowest rate for the period.

**rate\_close** doublenullable

Gets or sets the closing rate for the period.

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.286Z",  
    "time_period_end": "2025-08-12T06:08:07.286Z",  
    "time_open": "2025-08-12T06:08:07.286Z",  
    "time_close": "2025-08-12T06:08:07.286Z",  
    "rate_open": 0,  
    "rate_high": 0,  
    "rate_low": 0,  
    "rate_close": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2016-01-01T00:00:00.0000000Z",  
    "time_period_end": "2016-01-01T00:01:00.0000000Z",  
    "time_open": "2016-01-01T00:00:00.0000000Z",  
    "time_close": "2016-01-01T00:00:00.0000000Z",  
    "rate_open": 430.586617904731,  
    "rate_high": 430.586617904731,  
    "rate_low": 430.586617904731,  
    "rate_close": 430.586617904731  
  },  
  {  
    "time_period_start": "2016-01-01T00:01:00.0000000Z",  
    "time_period_end": "2016-01-01T00:02:00.0000000Z",  
    "time_open": "2016-01-01T00:01:00.0000000Z",  
    "time_close": "2016-01-01T00:01:00.0000000Z",  
    "rate_open": 430.38999999999993,  
    "rate_high": 430.38999999999993,  
    "rate_low": 430.38999999999993,  
    "rate_close": 430.38999999999993  
  },  
  {  
    "time_period_start": "2016-01-01T00:02:00.0000000Z",  
    "time_period_end": "2016-01-01T00:03:00.0000000Z",  
    "time_open": "2016-01-01T00:02:00.0000000Z",  
    "time_close": "2016-01-01T00:02:00.0000000Z",  
    "rate_open": 430.6522189770523,  
    "rate_high": 430.6522189770523,  
    "rate_low": 430.6522189770523,  
    "rate_close": 430.6522189770523  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**time\_period\_start** date-time

Gets or sets the start time of the period.

**time\_period\_end** date-time

Gets or sets the end time of the period.

**time\_open** date-timenullable

Gets or sets the opening time of the period.

**time\_close** date-timenullable

Gets or sets the closing time of the period.

**rate\_open** doublenullable

Gets or sets the opening rate for the period.

**rate\_high** doublenullable

Gets or sets the highest rate for the period.

**rate\_low** doublenullable

Gets or sets the lowest rate for the period.

**rate\_close** doublenullable

Gets or sets the closing rate for the period.

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.286Z",  
    "time_period_end": "2025-08-12T06:08:07.286Z",  
    "time_open": "2025-08-12T06:08:07.286Z",  
    "time_close": "2025-08-12T06:08:07.286Z",  
    "rate_open": 0,  
    "rate_high": 0,  
    "rate_low": 0,  
    "rate_close": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2016-01-01T00:00:00.0000000Z",  
    "time_period_end": "2016-01-01T00:01:00.0000000Z",  
    "time_open": "2016-01-01T00:00:00.0000000Z",  
    "time_close": "2016-01-01T00:00:00.0000000Z",  
    "rate_open": 430.586617904731,  
    "rate_high": 430.586617904731,  
    "rate_low": 430.586617904731,  
    "rate_close": 430.586617904731  
  },  
  {  
    "time_period_start": "2016-01-01T00:01:00.0000000Z",  
    "time_period_end": "2016-01-01T00:02:00.0000000Z",  
    "time_open": "2016-01-01T00:01:00.0000000Z",  
    "time_close": "2016-01-01T00:01:00.0000000Z",  
    "rate_open": 430.38999999999993,  
    "rate_high": 430.38999999999993,  
    "rate_low": 430.38999999999993,  
    "rate_close": 430.38999999999993  
  },  
  {  
    "time_period_start": "2016-01-01T00:02:00.0000000Z",  
    "time_period_end": "2016-01-01T00:03:00.0000000Z",  
    "time_open": "2016-01-01T00:02:00.0000000Z",  
    "time_close": "2016-01-01T00:02:00.0000000Z",  
    "rate_open": 430.6522189770523,  
    "rate_high": 430.6522189770523,  
    "rate_low": 430.6522189770523,  
    "rate_close": 430.6522189770523  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**time\_period\_start** date-time

Gets or sets the start time of the period.

**time\_period\_end** date-time

Gets or sets the end time of the period.

**time\_open** date-timenullable

Gets or sets the opening time of the period.

**time\_close** date-timenullable

Gets or sets the closing time of the period.

**rate\_open** doublenullable

Gets or sets the opening rate for the period.

**rate\_high** doublenullable

Gets or sets the highest rate for the period.

**rate\_low** doublenullable

Gets or sets the lowest rate for the period.

**rate\_close** doublenullable

Gets or sets the closing rate for the period.

* ]

```
[  
  {  
    "time_period_start": "2025-08-12T06:08:07.287Z",  
    "time_period_end": "2025-08-12T06:08:07.287Z",  
    "time_open": "2025-08-12T06:08:07.287Z",  
    "time_close": "2025-08-12T06:08:07.287Z",  
    "rate_open": 0,  
    "rate_high": 0,  
    "rate_low": 0,  
    "rate_close": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2016-01-01T00:00:00.0000000Z",  
    "time_period_end": "2016-01-01T00:01:00.0000000Z",  
    "time_open": "2016-01-01T00:00:00.0000000Z",  
    "time_close": "2016-01-01T00:00:00.0000000Z",  
    "rate_open": 430.586617904731,  
    "rate_high": 430.586617904731,  
    "rate_low": 430.586617904731,  
    "rate_close": 430.586617904731  
  },  
  {  
    "time_period_start": "2016-01-01T00:01:00.0000000Z",  
    "time_period_end": "2016-01-01T00:02:00.0000000Z",  
    "time_open": "2016-01-01T00:01:00.0000000Z",  
    "time_close": "2016-01-01T00:01:00.0000000Z",  
    "rate_open": 430.38999999999993,  
    "rate_high": 430.38999999999993,  
    "rate_low": 430.38999999999993,  
    "rate_close": 430.38999999999993  
  },  
  {  
    "time_period_start": "2016-01-01T00:02:00.0000000Z",  
    "time_period_end": "2016-01-01T00:03:00.0000000Z",  
    "time_open": "2016-01-01T00:02:00.0000000Z",  
    "time_close": "2016-01-01T00:02:00.0000000Z",  
    "rate_open": 430.6522189770523,  
    "rate_high": 430.6522189770523,  
    "rate_low": 430.6522189770523,  
    "rate_close": 430.6522189770523  
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

Timeseries periods](/currencies-api/rest-api-historical/timeseries-periods)[Next

Metadata](/currencies-api/rest-api-historical/metadata)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.