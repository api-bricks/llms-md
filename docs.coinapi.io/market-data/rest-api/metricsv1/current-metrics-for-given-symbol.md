Current metrics for given symbol | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metricsv1/current-metrics-for-given-symbol)

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
* Current metrics for given symbol

Current metrics for given symbol
================================

```
GET

/v1/metrics/symbol/current
--------------------------
```

Get current symbol metrics.

Request[​](/market-data/rest-api/metricsv1/current-metrics-for-given-symbol#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------------

### Query Parameters

**metric\_id** string

Metric identifier (from the Metrics -> Listing)

**symbol\_id** string

Symbol identifier (from the Metadata -> Symbols)

**exchange\_id** string

Exchange id (from the Metadata -> Exchanges)

Responses[​](/market-data/rest-api/metricsv1/current-metrics-for-given-symbol#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------------

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

**entry\_time** date-time

Gets or sets the entry time for the data point.

**recv\_time** date-time

Gets or sets the received time for the data point.

**exchange\_id** stringnullable

Gets or sets the identifier for the exchange.

**asset\_id** stringnullable

Gets or sets the identifier for the asset.

**symbol\_id** stringnullable

Gets or sets the identifier for the symbol.

**metric\_id** stringnullable

Gets or sets the identifier for the metric.

**value\_decimal** doublenullable

Gets or sets the decimal value for the metric.

**value\_text** stringnullable

Gets or sets the textual representation of the value for the metric.

**value\_time** date-timenullable

Gets or sets the timestamp value for the metric.

* ]

```
[  
  {  
    "entry_time": "2025-08-12T06:09:08.800Z",  
    "recv_time": "2025-08-12T06:09:08.800Z",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "symbol_id": "string",  
    "metric_id": "string",  
    "value_decimal": 0,  
    "value_text": "string",  
    "value_time": "2025-08-12T06:09:08.800Z"  
  }  
]
```

```
[  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBITUAT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_RHO",  
    "value_decimal": -594.10357  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_VEGA",  
    "value_decimal": 49.31013  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_THETA",  
    "value_decimal": -6.14104  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "DERIVATIVES_INDEX_PRICE",  
    "value_decimal": 30027.74  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**entry\_time** date-time

Gets or sets the entry time for the data point.

**recv\_time** date-time

Gets or sets the received time for the data point.

**exchange\_id** stringnullable

Gets or sets the identifier for the exchange.

**asset\_id** stringnullable

Gets or sets the identifier for the asset.

**symbol\_id** stringnullable

Gets or sets the identifier for the symbol.

**metric\_id** stringnullable

Gets or sets the identifier for the metric.

**value\_decimal** doublenullable

Gets or sets the decimal value for the metric.

**value\_text** stringnullable

Gets or sets the textual representation of the value for the metric.

**value\_time** date-timenullable

Gets or sets the timestamp value for the metric.

* ]

```
[  
  {  
    "entry_time": "2025-08-12T06:09:08.800Z",  
    "recv_time": "2025-08-12T06:09:08.800Z",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "symbol_id": "string",  
    "metric_id": "string",  
    "value_decimal": 0,  
    "value_text": "string",  
    "value_time": "2025-08-12T06:09:08.800Z"  
  }  
]
```

```
[  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBITUAT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_RHO",  
    "value_decimal": -594.10357  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_VEGA",  
    "value_decimal": 49.31013  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_THETA",  
    "value_decimal": -6.14104  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "DERIVATIVES_INDEX_PRICE",  
    "value_decimal": 30027.74  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**entry\_time** date-time

Gets or sets the entry time for the data point.

**recv\_time** date-time

Gets or sets the received time for the data point.

**exchange\_id** stringnullable

Gets or sets the identifier for the exchange.

**asset\_id** stringnullable

Gets or sets the identifier for the asset.

**symbol\_id** stringnullable

Gets or sets the identifier for the symbol.

**metric\_id** stringnullable

Gets or sets the identifier for the metric.

**value\_decimal** doublenullable

Gets or sets the decimal value for the metric.

**value\_text** stringnullable

Gets or sets the textual representation of the value for the metric.

**value\_time** date-timenullable

Gets or sets the timestamp value for the metric.

* ]

```
[  
  {  
    "entry_time": "2025-08-12T06:09:08.800Z",  
    "recv_time": "2025-08-12T06:09:08.800Z",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "symbol_id": "string",  
    "metric_id": "string",  
    "value_decimal": 0,  
    "value_text": "string",  
    "value_time": "2025-08-12T06:09:08.800Z"  
  }  
]
```

```
[  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBITUAT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_RHO",  
    "value_decimal": -594.10357  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_VEGA",  
    "value_decimal": 49.31013  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_THETA",  
    "value_decimal": -6.14104  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "DERIVATIVES_INDEX_PRICE",  
    "value_decimal": 30027.74  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**entry\_time** date-time

Gets or sets the entry time for the data point.

**recv\_time** date-time

Gets or sets the received time for the data point.

**exchange\_id** stringnullable

Gets or sets the identifier for the exchange.

**asset\_id** stringnullable

Gets or sets the identifier for the asset.

**symbol\_id** stringnullable

Gets or sets the identifier for the symbol.

**metric\_id** stringnullable

Gets or sets the identifier for the metric.

**value\_decimal** doublenullable

Gets or sets the decimal value for the metric.

**value\_text** stringnullable

Gets or sets the textual representation of the value for the metric.

**value\_time** date-timenullable

Gets or sets the timestamp value for the metric.

* ]

```
[  
  {  
    "entry_time": "2025-08-12T06:09:08.801Z",  
    "recv_time": "2025-08-12T06:09:08.801Z",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "symbol_id": "string",  
    "metric_id": "string",  
    "value_decimal": 0,  
    "value_text": "string",  
    "value_time": "2025-08-12T06:09:08.801Z"  
  }  
]
```

```
[  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBITUAT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_RHO",  
    "value_decimal": -594.10357  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_VEGA",  
    "value_decimal": 49.31013  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "GREEKS_THETA",  
    "value_decimal": -6.14104  
  },  
  {  
    "entry_time": "2023-06-23T12:38:48.2782698Z",  
    "recv_time": "2023-06-23T12:38:48.0140000Z",  
    "exchange_id": "DERIBIT",  
    "symbol_id": "DERIBIT_OPT_BTC_USD_240329_80000_P",  
    "metric_id": "DERIVATIVES_INDEX_PRICE",  
    "value_decimal": 30027.74  
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

Current metrics for given exchange](/market-data/rest-api/metricsv1/current-metrics-for-given-exchange)[Next

Historical metrics for asset](/market-data/rest-api/metricsv1/historical-metrics-for-asset)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.