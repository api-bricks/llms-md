Historical metrics for the asset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metricsv2/historical-metrics-for-the-asset)

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

    - [Introduction](/market-data/rest-api/metricsv2/coinapi-market-data-rest-api)
    - [Historical metrics for the asset](/market-data/rest-api/metricsv2/historical-metrics-for-the-asset)
    - [Historical metrics for the chain](/market-data/rest-api/metricsv2/historical-metrics-for-the-chain)
    - [Historical metrics for the exchange](/market-data/rest-api/metricsv2/historical-metrics-for-the-exchange)
    - [Listing of all supported metrics](/market-data/rest-api/metricsv2/listing-of-all-supported-metrics)
    - [Listing of metrics available for specific asset](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-asset)
    - [Listing of metrics available for specific chain](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-chain)
    - [Listing of metrics available for specific exchange](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-exchange)
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
* [MetricsV2](/market-data/rest-api/metricsv2/)
* Historical metrics for the asset

Historical metrics for the asset
================================

```
GET

/v2/metrics/asset/history
-------------------------
```

Get asset metrics history.

Request[​](/market-data/rest-api/metricsv2/historical-metrics-for-the-asset#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------------

### Query Parameters

**metric\_id** stringrequired

Metric identifier (e.g., `TVL`, `STABLES_BRIDGED_USD`)

**asset\_id** stringrequired

Asset identifier (e.g., `USDC`, `USDT`)

**time\_start** date-time

Starting time in ISO 8601

**time\_end** date-time

Ending time in ISO 8601

**time\_format** string

If set, returned values will be in unix timestamp format (valid values: unix\_sec, unix\_millisec, unix\_microsec, unix\_nanosec)

**period\_id** string

Identifier of requested timeseries period (e.g. `1MIN` or `2MTH`), default value is `1MIN`

**limit** int32

**Default value:** `100`

Amount of items to return (optional, mininum is 1, maximum is 100000, default value is 100, if the parameter is used then every 100 output items are counted as one request)

Responses[​](/market-data/rest-api/metricsv2/historical-metrics-for-the-asset#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------------

* 200
* 400
* 500

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)
* Example asset metrics response

**Schema**

* Array [
* ]

```
[  
  {}  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T00:00:00.0000000Z",  
    "time_period_end": "2023-07-04T00:00:00.0000000Z",  
    "time_open": "2023-07-03T00:00:00.0000000Z",  
    "time_close": "2023-07-03T23:59:59.9990000Z",  
    "first_value": 15000000000,  
    "last_value": 15500000000,  
    "min_value": 14800000000,  
    "max_value": 15600000000,  
    "count_values": 24,  
    "sum_values": 370000000000  
  },  
  {  
    "time_period_start": "2023-07-04T00:00:00.0000000Z",  
    "time_period_end": "2023-07-05T00:00:00.0000000Z",  
    "time_open": "2023-07-04T00:00:00.0000000Z",  
    "time_close": "2023-07-04T23:59:59.9990000Z",  
    "first_value": 15500000000,  
    "last_value": 15300000000,  
    "min_value": 15200000000,  
    "max_value": 15700000000,  
    "count_values": 24,  
    "sum_values": 372000000000  
  }  
]
```

* Schema
* Example (from schema)
* Example asset metrics response

**Schema**

* Array [
* ]

```
[  
  {}  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T00:00:00.0000000Z",  
    "time_period_end": "2023-07-04T00:00:00.0000000Z",  
    "time_open": "2023-07-03T00:00:00.0000000Z",  
    "time_close": "2023-07-03T23:59:59.9990000Z",  
    "first_value": 15000000000,  
    "last_value": 15500000000,  
    "min_value": 14800000000,  
    "max_value": 15600000000,  
    "count_values": 24,  
    "sum_values": 370000000000  
  },  
  {  
    "time_period_start": "2023-07-04T00:00:00.0000000Z",  
    "time_period_end": "2023-07-05T00:00:00.0000000Z",  
    "time_open": "2023-07-04T00:00:00.0000000Z",  
    "time_close": "2023-07-04T23:59:59.9990000Z",  
    "first_value": 15500000000,  
    "last_value": 15300000000,  
    "min_value": 15200000000,  
    "max_value": 15700000000,  
    "count_values": 24,  
    "sum_values": 372000000000  
  }  
]
```

* Schema
* Example (from schema)
* Example asset metrics response

**Schema**

* Array [
* ]

```
[  
  {}  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T00:00:00.0000000Z",  
    "time_period_end": "2023-07-04T00:00:00.0000000Z",  
    "time_open": "2023-07-03T00:00:00.0000000Z",  
    "time_close": "2023-07-03T23:59:59.9990000Z",  
    "first_value": 15000000000,  
    "last_value": 15500000000,  
    "min_value": 14800000000,  
    "max_value": 15600000000,  
    "count_values": 24,  
    "sum_values": 370000000000  
  },  
  {  
    "time_period_start": "2023-07-04T00:00:00.0000000Z",  
    "time_period_end": "2023-07-05T00:00:00.0000000Z",  
    "time_open": "2023-07-04T00:00:00.0000000Z",  
    "time_close": "2023-07-04T23:59:59.9990000Z",  
    "first_value": 15500000000,  
    "last_value": 15300000000,  
    "min_value": 15200000000,  
    "max_value": 15700000000,  
    "count_values": 24,  
    "sum_values": 372000000000  
  }  
]
```

* Schema
* Example (from schema)
* Example asset metrics response

**Schema**

* Array [
* ]

```
[  
  {}  
]
```

```
[  
  {  
    "time_period_start": "2023-07-03T00:00:00.0000000Z",  
    "time_period_end": "2023-07-04T00:00:00.0000000Z",  
    "time_open": "2023-07-03T00:00:00.0000000Z",  
    "time_close": "2023-07-03T23:59:59.9990000Z",  
    "first_value": 15000000000,  
    "last_value": 15500000000,  
    "min_value": 14800000000,  
    "max_value": 15600000000,  
    "count_values": 24,  
    "sum_values": 370000000000  
  },  
  {  
    "time_period_start": "2023-07-04T00:00:00.0000000Z",  
    "time_period_end": "2023-07-05T00:00:00.0000000Z",  
    "time_open": "2023-07-04T00:00:00.0000000Z",  
    "time_close": "2023-07-04T23:59:59.9990000Z",  
    "first_value": 15500000000,  
    "last_value": 15300000000,  
    "min_value": 15200000000,  
    "max_value": 15700000000,  
    "count_values": 24,  
    "sum_values": 372000000000  
  }  
]
```

Invalid input, e.g., missing required parameters, invalid asset\_id.

Internal server error.

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/market-data/rest-api/metricsv2/coinapi-market-data-rest-api)[Next

Historical metrics for the chain](/market-data/rest-api/metricsv2/historical-metrics-for-the-chain)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.