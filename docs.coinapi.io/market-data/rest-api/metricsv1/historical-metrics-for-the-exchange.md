Historical metrics for the exchange | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metricsv1/historical-metrics-for-the-exchange)

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

    - [Introduction](/market-data/rest-api/metricsv1/coinapi-market-data-rest-api)
    - [Current metrics for given asset](/market-data/rest-api/metricsv1/current-metrics-for-given-asset)
    - [Current metrics for given exchange](/market-data/rest-api/metricsv1/current-metrics-for-given-exchange)
    - [Current metrics for given symbol](/market-data/rest-api/metricsv1/current-metrics-for-given-symbol)
    - [Historical metrics for asset](/market-data/rest-api/metricsv1/historical-metrics-for-asset)
    - [Historical metrics for symbol](/market-data/rest-api/metricsv1/historical-metrics-for-symbol)
    - [Historical metrics for the exchange](/market-data/rest-api/metricsv1/historical-metrics-for-the-exchange)
    - [Listing of all supported exchange metrics](/market-data/rest-api/metricsv1/listing-of-all-supported-exchange-metrics)
    - [Listing of all supported metrics by CoinAPI](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-by-coin-api)
    - [Listing of all supported metrics for asset](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-for-asset)
    - [Listing of all supported metrics for symbol](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-for-symbol)
  + [MetricsV2](/market-data/rest-api/metricsv2/)
  + [Ohlcv](/market-data/rest-api/ohlcv/)
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
* [MetricsV1](/market-data/rest-api/metricsv1/)
* Historical metrics for the exchange

Historical metrics for the exchange
===================================

```
GET

/v1/metrics/exchange/history
----------------------------
```

Get exchange metrics history.

Request[​](/market-data/rest-api/metricsv1/historical-metrics-for-the-exchange#request "Direct link to Request")
----------------------------------------------------------------------------------------------------------------

### Query Parameters

**metric\_id** stringrequired

Metric identifier (from the Metrics -> Listing)

**exchange\_id** stringrequired

Exchange identifier (from the Metadata -> Exchanges)

**time\_start** date-time

Starting time in ISO 8601

**time\_end** date-time

Ending time in ISO 8601

**time\_format** string

If set, returned values will be in unix timestamp format (valid values: unix\_sec, unix\_millisec, unix\_microsec, unix\_nanosec)

**period\_id** string

Identifier of requested timeseries period (e.g. `5SEC` or `2MTH`), default value is `1SEC`

**limit** int32

**Default value:** `100`

Amount of items to return (optional, mininum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

Responses[​](/market-data/rest-api/metricsv1/historical-metrics-for-the-exchange#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol id.

**time** date-time

Gets or sets the time at which the value is recorded.

**value** double

Gets or sets the value of the metric.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time": "2025-08-12T06:09:08.795Z",  
    "value": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T14:29:02.0000000Z",  
    "time_period_end": "2023-07-03T14:29:03.0000000Z",  
    "time_open": "2023-07-03T14:29:02.5699837Z",  
    "time_close": "2023-07-03T14:29:02.5699837Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 30668.476938  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:03.0000000Z",  
    "time_period_end": "2023-07-03T14:29:04.0000000Z",  
    "time_open": "2023-07-03T14:29:03.1076159Z",  
    "time_close": "2023-07-03T14:29:03.1076159Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 0.05485331  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:04.0000000Z",  
    "time_period_end": "2023-07-03T14:29:05.0000000Z",  
    "time_open": "2023-07-03T14:29:04.5792149Z",  
    "time_close": "2023-07-03T14:29:04.9459786Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 7.0257000000000005  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol id.

**time** date-time

Gets or sets the time at which the value is recorded.

**value** double

Gets or sets the value of the metric.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time": "2025-08-12T06:09:08.795Z",  
    "value": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T14:29:02.0000000Z",  
    "time_period_end": "2023-07-03T14:29:03.0000000Z",  
    "time_open": "2023-07-03T14:29:02.5699837Z",  
    "time_close": "2023-07-03T14:29:02.5699837Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 30668.476938  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:03.0000000Z",  
    "time_period_end": "2023-07-03T14:29:04.0000000Z",  
    "time_open": "2023-07-03T14:29:03.1076159Z",  
    "time_close": "2023-07-03T14:29:03.1076159Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 0.05485331  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:04.0000000Z",  
    "time_period_end": "2023-07-03T14:29:05.0000000Z",  
    "time_open": "2023-07-03T14:29:04.5792149Z",  
    "time_close": "2023-07-03T14:29:04.9459786Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 7.0257000000000005  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol id.

**time** date-time

Gets or sets the time at which the value is recorded.

**value** double

Gets or sets the value of the metric.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time": "2025-08-12T06:09:08.795Z",  
    "value": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T14:29:02.0000000Z",  
    "time_period_end": "2023-07-03T14:29:03.0000000Z",  
    "time_open": "2023-07-03T14:29:02.5699837Z",  
    "time_close": "2023-07-03T14:29:02.5699837Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 30668.476938  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:03.0000000Z",  
    "time_period_end": "2023-07-03T14:29:04.0000000Z",  
    "time_open": "2023-07-03T14:29:03.1076159Z",  
    "time_close": "2023-07-03T14:29:03.1076159Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 0.05485331  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:04.0000000Z",  
    "time_period_end": "2023-07-03T14:29:05.0000000Z",  
    "time_open": "2023-07-03T14:29:04.5792149Z",  
    "time_close": "2023-07-03T14:29:04.9459786Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 7.0257000000000005  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol id.

**time** date-time

Gets or sets the time at which the value is recorded.

**value** double

Gets or sets the value of the metric.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "time": "2025-08-12T06:09:08.795Z",  
    "value": 0  
  }  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T14:29:02.0000000Z",  
    "time_period_end": "2023-07-03T14:29:03.0000000Z",  
    "time_open": "2023-07-03T14:29:02.5699837Z",  
    "time_close": "2023-07-03T14:29:02.5699837Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 30668.476938  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:03.0000000Z",  
    "time_period_end": "2023-07-03T14:29:04.0000000Z",  
    "time_open": "2023-07-03T14:29:03.1076159Z",  
    "time_close": "2023-07-03T14:29:03.1076159Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 0.05485331  
  },  
  {  
    "time_period_start": "2023-07-03T14:29:04.0000000Z",  
    "time_period_end": "2023-07-03T14:29:05.0000000Z",  
    "time_open": "2023-07-03T14:29:04.5792149Z",  
    "time_close": "2023-07-03T14:29:04.9459786Z",  
    "first": 0,  
    "last": 0,  
    "min": 0,  
    "max": 0,  
    "count": 0,  
    "sum": 7.0257000000000005  
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

Historical metrics for symbol](/market-data/rest-api/metricsv1/historical-metrics-for-symbol)[Next

Listing of all supported exchange metrics](/market-data/rest-api/metricsv1/listing-of-all-supported-exchange-metrics)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.