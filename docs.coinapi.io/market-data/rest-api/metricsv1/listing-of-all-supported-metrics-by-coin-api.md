Listing of all supported metrics by CoinAPI | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-by-coin-api)

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
* Listing of all supported metrics by CoinAPI

Listing of all supported metrics by CoinAPI
===========================================

```
GET

/v1/metrics/listing
-------------------
```

Get all data metrics.

Responses[​](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-by-coin-api#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------------------------

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

**description** stringnullable

Gets or sets the metric description.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_QUANTITY",  
    "description": "The liquidation quantity metric calculates the specific amount of the asset that must be sold to settle the trader's obligations and bring their position back to a manageable level. It helps ensure that the trader's losses are covered and that their account remains in good standing."  
  },  
  {  
    "metric_id": "DERIVATIVES_LAST_PRICE",  
    "description": "The last price represents the price at which the most recent trade of the derivative contract occurred. It provides traders and investors with the latest information on the market value of the derivative, allowing them to assess the current market sentiment, track price movements, and make informed decisions regarding their derivative positions. The derivatives last price metric is crucial for monitoring real-time market conditions and managing derivative trading strategies effectively."  
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

**description** stringnullable

Gets or sets the metric description.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_QUANTITY",  
    "description": "The liquidation quantity metric calculates the specific amount of the asset that must be sold to settle the trader's obligations and bring their position back to a manageable level. It helps ensure that the trader's losses are covered and that their account remains in good standing."  
  },  
  {  
    "metric_id": "DERIVATIVES_LAST_PRICE",  
    "description": "The last price represents the price at which the most recent trade of the derivative contract occurred. It provides traders and investors with the latest information on the market value of the derivative, allowing them to assess the current market sentiment, track price movements, and make informed decisions regarding their derivative positions. The derivatives last price metric is crucial for monitoring real-time market conditions and managing derivative trading strategies effectively."  
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

**description** stringnullable

Gets or sets the metric description.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_QUANTITY",  
    "description": "The liquidation quantity metric calculates the specific amount of the asset that must be sold to settle the trader's obligations and bring their position back to a manageable level. It helps ensure that the trader's losses are covered and that their account remains in good standing."  
  },  
  {  
    "metric_id": "DERIVATIVES_LAST_PRICE",  
    "description": "The last price represents the price at which the most recent trade of the derivative contract occurred. It provides traders and investors with the latest information on the market value of the derivative, allowing them to assess the current market sentiment, track price movements, and make informed decisions regarding their derivative positions. The derivatives last price metric is crucial for monitoring real-time market conditions and managing derivative trading strategies effectively."  
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

**description** stringnullable

Gets or sets the metric description.

* ]

```
[  
  {  
    "metric_id": "string",  
    "description": "string"  
  }  
]
```

```
[  
  {  
    "metric_id": "LIQUIDATION_QUANTITY",  
    "description": "The liquidation quantity metric calculates the specific amount of the asset that must be sold to settle the trader's obligations and bring their position back to a manageable level. It helps ensure that the trader's losses are covered and that their account remains in good standing."  
  },  
  {  
    "metric_id": "DERIVATIVES_LAST_PRICE",  
    "description": "The last price represents the price at which the most recent trade of the derivative contract occurred. It provides traders and investors with the latest information on the market value of the derivative, allowing them to assess the current market sentiment, track price movements, and make informed decisions regarding their derivative positions. The derivatives last price metric is crucial for monitoring real-time market conditions and managing derivative trading strategies effectively."  
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

Listing of all supported exchange metrics](/market-data/rest-api/metricsv1/listing-of-all-supported-exchange-metrics)[Next

Listing of all supported metrics for asset](/market-data/rest-api/metricsv1/listing-of-all-supported-metrics-for-asset)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.