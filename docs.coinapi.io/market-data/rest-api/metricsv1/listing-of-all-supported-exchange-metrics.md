Listing of all supported exchange metrics | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metricsv1/listing-of-all-supported-exchange-metrics)

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
* Listing of all supported exchange metrics

Listing of all supported exchange metrics
=========================================

```
GET

/v1/metrics/exchange/listing
----------------------------
```

Get data metrics for exchange.

Request[​](/market-data/rest-api/metricsv1/listing-of-all-supported-exchange-metrics#request "Direct link to Request")
----------------------------------------------------------------------------------------------------------------------

### Query Parameters

**metric\_id** string

The metric identifier (from the Metrics -> Listing)

**exchange\_id** stringrequired

The exchange identifier (from the Metadata -> Exchanges)

Responses[​](/market-data/rest-api/metricsv1/listing-of-all-supported-exchange-metrics#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------------------------

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

**metric\_id** stringnullable

Gets or sets the metric ID.

**symbol\_id** stringnullable

Gets or sets the symbol ID.

**symbol\_id\_external** stringnullable

Gets or sets the symbol ID from the exchange.

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**asset\_id** stringnullable

Gets or sets the asset ID.

**asset\_id\_external** stringnullable

Gets or sets the asset ID from the exchange.

**chain\_id** stringnullable

Gets or sets the chain id.

**network\_id** stringnullable

Gets or sets the network id.

* ]

```
[  
  {  
    "metric_id": "string",  
    "symbol_id": "string",  
    "symbol_id_external": "string",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "asset_id_external": "string",  
    "chain_id": "string",  
    "network_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_TIME_IN_FORCE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_TYPE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_STATUS",  
    "exchange_id": "BINANCEFTS"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric ID.

**symbol\_id** stringnullable

Gets or sets the symbol ID.

**symbol\_id\_external** stringnullable

Gets or sets the symbol ID from the exchange.

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**asset\_id** stringnullable

Gets or sets the asset ID.

**asset\_id\_external** stringnullable

Gets or sets the asset ID from the exchange.

**chain\_id** stringnullable

Gets or sets the chain id.

**network\_id** stringnullable

Gets or sets the network id.

* ]

```
[  
  {  
    "metric_id": "string",  
    "symbol_id": "string",  
    "symbol_id_external": "string",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "asset_id_external": "string",  
    "chain_id": "string",  
    "network_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_TIME_IN_FORCE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_TYPE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_STATUS",  
    "exchange_id": "BINANCEFTS"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric ID.

**symbol\_id** stringnullable

Gets or sets the symbol ID.

**symbol\_id\_external** stringnullable

Gets or sets the symbol ID from the exchange.

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**asset\_id** stringnullable

Gets or sets the asset ID.

**asset\_id\_external** stringnullable

Gets or sets the asset ID from the exchange.

**chain\_id** stringnullable

Gets or sets the chain id.

**network\_id** stringnullable

Gets or sets the network id.

* ]

```
[  
  {  
    "metric_id": "string",  
    "symbol_id": "string",  
    "symbol_id_external": "string",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "asset_id_external": "string",  
    "chain_id": "string",  
    "network_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_TIME_IN_FORCE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_TYPE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_STATUS",  
    "exchange_id": "BINANCEFTS"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric ID.

**symbol\_id** stringnullable

Gets or sets the symbol ID.

**symbol\_id\_external** stringnullable

Gets or sets the symbol ID from the exchange.

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**asset\_id** stringnullable

Gets or sets the asset ID.

**asset\_id\_external** stringnullable

Gets or sets the asset ID from the exchange.

**chain\_id** stringnullable

Gets or sets the chain id.

**network\_id** stringnullable

Gets or sets the network id.

* ]

```
[  
  {  
    "metric_id": "string",  
    "symbol_id": "string",  
    "symbol_id_external": "string",  
    "exchange_id": "string",  
    "asset_id": "string",  
    "asset_id_external": "string",  
    "chain_id": "string",  
    "network_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_TIME_IN_FORCE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_TYPE",  
    "exchange_id": "BINANCEFTS"  
  },  
  {  
    "metric_id": "LIQUIDATION_ORDER_STATUS",  
    "exchange_id": "BINANCEFTS"  
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

Historical metrics for the exchange](/market-data/rest-api/metricsv1/historical-metrics-for-the-exchange)[Next

Listing of all supported metrics by CoinAPI](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-by-coin-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.