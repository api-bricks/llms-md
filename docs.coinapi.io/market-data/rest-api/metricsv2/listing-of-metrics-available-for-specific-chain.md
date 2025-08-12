Listing of metrics available for specific chain | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-chain)

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
* Listing of metrics available for specific chain

Listing of metrics available for specific chain
===============================================

```
GET

/v2/metrics/chain/listing
-------------------------
```

Get all metrics that are actually available for the specified blockchain chain.

Request[​](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-chain#request "Direct link to Request")
----------------------------------------------------------------------------------------------------------------------------

### Query Parameters

**chain\_id** stringrequired

Chain identifier (e.g., ETHEREUM, ARBITRUM)

Responses[​](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-chain#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)
* Example external metrics for chain

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric identifier.

**description** stringnullable

Gets or sets the description of the metric.

**source\_id** stringnullable

Gets or sets the source identifier of the metric.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string",  
    "source_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "TVL",  
    "description": "Total Value Locked in the protocol"  
  },  
  {  
    "metric_id": "STABLES_BRIDGED_USD",  
    "description": "Total USD stablecoins bridged to USD value"  
  },  
  {  
    "metric_id": "STABLES_CIRCULATING_USD",  
    "description": "Total circulating USD stablecoins"  
  }  
]
```

* Schema
* Example (from schema)
* Example external metrics for chain

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric identifier.

**description** stringnullable

Gets or sets the description of the metric.

**source\_id** stringnullable

Gets or sets the source identifier of the metric.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string",  
    "source_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "TVL",  
    "description": "Total Value Locked in the protocol"  
  },  
  {  
    "metric_id": "STABLES_BRIDGED_USD",  
    "description": "Total USD stablecoins bridged to USD value"  
  },  
  {  
    "metric_id": "STABLES_CIRCULATING_USD",  
    "description": "Total circulating USD stablecoins"  
  }  
]
```

* Schema
* Example (from schema)
* Example external metrics for chain

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric identifier.

**description** stringnullable

Gets or sets the description of the metric.

**source\_id** stringnullable

Gets or sets the source identifier of the metric.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string",  
    "source_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "TVL",  
    "description": "Total Value Locked in the protocol"  
  },  
  {  
    "metric_id": "STABLES_BRIDGED_USD",  
    "description": "Total USD stablecoins bridged to USD value"  
  },  
  {  
    "metric_id": "STABLES_CIRCULATING_USD",  
    "description": "Total circulating USD stablecoins"  
  }  
]
```

* Schema
* Example (from schema)
* Example external metrics for chain

**Schema**

* Array [

**metric\_id** stringnullable

Gets or sets the metric identifier.

**description** stringnullable

Gets or sets the description of the metric.

**source\_id** stringnullable

Gets or sets the source identifier of the metric.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string",  
    "source_id": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "TVL",  
    "description": "Total Value Locked in the protocol"  
  },  
  {  
    "metric_id": "STABLES_BRIDGED_USD",  
    "description": "Total USD stablecoins bridged to USD value"  
  },  
  {  
    "metric_id": "STABLES_CIRCULATING_USD",  
    "description": "Total circulating USD stablecoins"  
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

Listing of metrics available for specific asset](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-asset)[Next

Listing of metrics available for specific exchange](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-exchange)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.