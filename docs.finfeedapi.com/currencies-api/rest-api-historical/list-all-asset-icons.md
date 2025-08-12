List all asset icons | FinFeedAPI.com Documentation




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
  + [Metadata](/currencies-api/rest-api-historical/metadata)

    - [List all assets](/currencies-api/rest-api-historical/list-all-assets)
    - [List all assets by asset ID](/currencies-api/rest-api-historical/list-all-assets-by-asset-id)
    - [List all asset icons](/currencies-api/rest-api-historical/list-all-asset-icons)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Metadata](/currencies-api/rest-api-historical/metadata)
* List all asset icons

List all asset icons
====================

```
GET

/v1/assets/icons/:size
----------------------
```

Gets the list of icons (of the given size) for all the assets.

Request[​](/currencies-api/rest-api-historical/list-all-asset-icons#request "Direct link to Request")
-----------------------------------------------------------------------------------------------------

### Path Parameters

**size** int32required

The size of the icons.

Responses[​](/currencies-api/rest-api-historical/list-all-asset-icons#responses "Direct link to Responses")
-----------------------------------------------------------------------------------------------------------

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

List all assets by asset ID](/currencies-api/rest-api-historical/list-all-assets-by-asset-id)[Next

Introduction](/currencies-api/websocket/)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.