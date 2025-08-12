List all asset icons | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/rest-api-realtime/list-all-asset-icons)

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

* [Exchange Rates API](/exchange-rates-api/)
* [Authentication](/exchange-rates-api/authentication)
* [Realtime REST API](/exchange-rates-api/rest-api-realtime/exchange-rates-realtime-rest-api)

  + [Introduction](/exchange-rates-api/rest-api-realtime/exchange-rates-realtime-rest-api)
  + [Exchange Rates](/exchange-rates-api/rest-api-realtime/exchange-rates)
  + [Metadata](/exchange-rates-api/rest-api-realtime/metadata)

    - [List all assets](/exchange-rates-api/rest-api-realtime/list-all-assets)
    - [List all assets by asset ID](/exchange-rates-api/rest-api-realtime/list-all-assets-by-asset-id)
    - [List all asset icons](/exchange-rates-api/rest-api-realtime/list-all-asset-icons)
* [Historical REST API](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)
* [Websocket API](/exchange-rates-api/websocket/)
* [JSON RPC](/exchange-rates-api/jsonrpc-api)
* [How-to guides](/exchange-rates-api/how-to-guides/)

* [Realtime REST API](/exchange-rates-api/rest-api-realtime/exchange-rates-realtime-rest-api)
* [Metadata](/exchange-rates-api/rest-api-realtime/metadata)
* List all asset icons

List all asset icons
====================

```
GET

/v1/assets/icons/:size
----------------------
```

Gets the list of icons (of the given size) for all the assets.

Request[​](/exchange-rates-api/rest-api-realtime/list-all-asset-icons#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------

### Path Parameters

**size** int32required

The size of the icons.

Responses[​](/exchange-rates-api/rest-api-realtime/list-all-asset-icons#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------

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

List all assets by asset ID](/exchange-rates-api/rest-api-realtime/list-all-assets-by-asset-id)[Next

Introduction](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.