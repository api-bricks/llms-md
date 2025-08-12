List all asset icons | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metadata/list-all-asset-icons)

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

    - [Introduction](/market-data/rest-api/metadata/coinapi-market-data-rest-api)
    - [List active symbol mapping for the exchange](/market-data/rest-api/metadata/list-active-symbol-mapping-for-the-exchange)
    - [List all active symbols](/market-data/rest-api/metadata/list-all-active-symbols)
    - [List all asset icons](/market-data/rest-api/metadata/list-all-asset-icons)
    - [List all assets by asset ID](/market-data/rest-api/metadata/list-all-assets-by-asset-id)
    - [List all assets](/market-data/rest-api/metadata/list-all-assets)
    - [List all blockchain chains](/market-data/rest-api/metadata/list-all-blockchain-chains)
    - [List all chains by chain ID](/market-data/rest-api/metadata/list-all-chains-by-chain-id)
    - [List all exchanges by exchange\_id](/market-data/rest-api/metadata/list-all-exchanges-by-exchange-id)
    - [List all exchanges](/market-data/rest-api/metadata/list-all-exchanges)
    - [List all historical symbols for an exchange.](/market-data/rest-api/metadata/list-all-historical-symbols-for-an-exchange)
    - [List of active symbols for the exchange](/market-data/rest-api/metadata/list-of-active-symbols-for-the-exchange)
    - [List of icons for the exchanges](/market-data/rest-api/metadata/list-of-icons-for-the-exchanges)
  + [MetricsV1](/market-data/rest-api/metricsv1/)
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
* [Metadata](/market-data/rest-api/metadata/)
* List all asset icons

List all asset icons
====================

```
GET

/v1/assets/icons/:size
----------------------
```

Gets the list of icons (of the given size) for all the assets.

Request[​](/market-data/rest-api/metadata/list-all-asset-icons#request "Direct link to Request")
------------------------------------------------------------------------------------------------

### Path Parameters

**size** int32required

The size of the icons.

Responses[​](/market-data/rest-api/metadata/list-all-asset-icons#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------

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

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

```
[  
  {  
    "exchange_id": "string",  
    "asset_id": "string",  
    "url": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/f231d7382689406f9a50dde841418c64.png"  
  },  
  {  
    "asset_id": "ETH",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/04836ff3bc4d4d95820e0155594dca86.png"  
  },  
  {  
    "asset_id": "USD",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/4873707f25fe4de3b4bca6fa5c631011.png"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

```
[  
  {  
    "exchange_id": "string",  
    "asset_id": "string",  
    "url": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/f231d7382689406f9a50dde841418c64.png"  
  },  
  {  
    "asset_id": "ETH",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/04836ff3bc4d4d95820e0155594dca86.png"  
  },  
  {  
    "asset_id": "USD",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/4873707f25fe4de3b4bca6fa5c631011.png"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

```
[  
  {  
    "exchange_id": "string",  
    "asset_id": "string",  
    "url": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/f231d7382689406f9a50dde841418c64.png"  
  },  
  {  
    "asset_id": "ETH",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/04836ff3bc4d4d95820e0155594dca86.png"  
  },  
  {  
    "asset_id": "USD",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/4873707f25fe4de3b4bca6fa5c631011.png"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

```
[  
  {  
    "exchange_id": "string",  
    "asset_id": "string",  
    "url": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/f231d7382689406f9a50dde841418c64.png"  
  },  
  {  
    "asset_id": "ETH",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/04836ff3bc4d4d95820e0155594dca86.png"  
  },  
  {  
    "asset_id": "USD",  
    "url": "https://s3.eu-central-1.amazonaws.com/bbxt-static-icons/type-id/png_16/4873707f25fe4de3b4bca6fa5c631011.png"  
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

List all active symbols](/market-data/rest-api/metadata/list-all-active-symbols)[Next

List all assets by asset ID](/market-data/rest-api/metadata/list-all-assets-by-asset-id)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.