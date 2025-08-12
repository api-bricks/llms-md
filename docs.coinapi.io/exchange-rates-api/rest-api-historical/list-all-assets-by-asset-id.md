List all assets by asset ID | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/rest-api-historical/list-all-assets-by-asset-id)

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
* [Historical REST API](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)

  + [Introduction](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)
  + [Exchange Rates](/exchange-rates-api/rest-api-historical/exchange-rates)
  + [Metadata](/exchange-rates-api/rest-api-historical/metadata)

    - [List all assets](/exchange-rates-api/rest-api-historical/list-all-assets)
    - [List all assets by asset ID](/exchange-rates-api/rest-api-historical/list-all-assets-by-asset-id)
    - [List all asset icons](/exchange-rates-api/rest-api-historical/list-all-asset-icons)
* [Websocket API](/exchange-rates-api/websocket/)
* [JSON RPC](/exchange-rates-api/jsonrpc-api)
* [How-to guides](/exchange-rates-api/how-to-guides/)

* [Historical REST API](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)
* [Metadata](/exchange-rates-api/rest-api-historical/metadata)
* List all assets by asset ID

List all assets by asset ID
===========================

```
GET

/v1/assets/:asset_id
--------------------
```

List all assets by asset ID

Request[​](/exchange-rates-api/rest-api-historical/list-all-assets-by-asset-id#request "Direct link to Request")
----------------------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id** stringrequired

The asset ID.

Responses[​](/exchange-rates-api/rest-api-historical/list-all-assets-by-asset-id#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------------------

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

**asset\_id** stringnullable

Gets or sets the asset ID.

**name** stringnullable

Gets or sets the name of the asset.

**type\_is\_crypto** int32

Gets or sets a value indicating whether the asset is a cryptocurrency.

**data\_quote\_start** date-timenullable

Gets or sets the start date of quote data.

**data\_quote\_end** date-timenullable

Gets or sets the end date of quote data.

**data\_orderbook\_start** date-timenullable

Gets or sets the start date of order book data.

**data\_orderbook\_end** date-timenullable

Gets or sets the end date of order book data.

**data\_trade\_start** date-timenullable

Gets or sets the start date of trade data.

**data\_trade\_end** date-timenullable

Gets or sets the end date of trade data.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**price\_usd** doublenullable

Gets or sets the USD price of the asset.

**id\_icon** uuidnullable

Gets or sets the ID of the icon for the asset.

**supply\_current** doublenullable

Gets or sets the current supply of the asset.

**supply\_total** doublenullable

Gets or sets the total supply of the asset.

**supply\_max** doublenullable

Gets or sets the maximum supply of the asset.

**chain\_addresses**

object[]

nullable

* Array [

**chain\_id** stringnullable

Gets or sets chain id

**network\_id** stringnullable

Gets or sets network id

**address** stringnullable

Gets or sets chain address

* ]

**data\_start** stringnullable

**data\_end** stringnullable

* ]

```
[  
  {  
    "asset_id": "string",  
    "name": "string",  
    "type_is_crypto": 0,  
    "data_quote_start": "2025-08-12T06:09:08.514Z",  
    "data_quote_end": "2025-08-12T06:09:08.514Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.514Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.514Z",  
    "data_trade_start": "2025-08-12T06:09:08.514Z",  
    "data_trade_end": "2025-08-12T06:09:08.514Z",  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "price_usd": 0,  
    "id_icon": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "supply_current": 0,  
    "supply_total": 0,  
    "supply_max": 0,  
    "chain_addresses": [  
      {  
        "chain_id": "string",  
        "network_id": "string",  
        "address": "string"  
      }  
    ],  
    "data_start": "string",  
    "data_end": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "name": "Bitcoin",  
    "type_is_crypto": 1,  
    "data_quote_start": "2014-02-24T17:43:05.0000000Z",  
    "data_quote_end": "2019-11-03T17:55:07.6724523Z",  
    "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",  
    "data_orderbook_end": "2019-11-03T17:55:17.8592413Z",  
    "data_trade_start": "2010-07-17T23:09:17.0000000Z",  
    "data_trade_end": "2019-11-03T17:55:11.8220000Z",  
    "data_symbols_count": 22711,  
    "volume_1hrs_usd": 102894431436.49,  
    "volume_1day_usd": 2086392323256.16,  
    "volume_1mth_usd": 57929168359984.54,  
    "price_usd": 9166.207274778093,  
    "chain_addresses": [  
      {  
        "chain_id": "ARBITRUM",  
        "network_id": "MAINNET",  
        "address": "0x2f2a2543b76a4166549f7aab2e75bef0aefc5b0f"  
      },  
      {  
        "chain_id": "ETHEREUM",  
        "network_id": "MAINNET",  
        "address": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599"  
      }  
    ],  
    "data_start": "2010-07-17",  
    "data_end": "2019-11-03"  
  },  
  {  
    "asset_id": "USD",  
    "name": "US Dollar",  
    "type_is_crypto": 0,  
    "data_quote_start": "2014-02-24T17:43:05.0000000Z",  
    "data_quote_end": "2019-11-03T17:54:49.3807706Z",  
    "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",  
    "data_orderbook_end": "2019-11-03T17:55:13.1863931Z",  
    "data_trade_start": "2010-07-17T23:09:17.0000000Z",  
    "data_trade_end": "2019-11-03T17:55:07.7870000Z",  
    "data_symbols_count": 10728,  
    "volume_1hrs_usd": 9466454016.52,  
    "volume_1day_usd": 221580758173.49,  
    "volume_1mth_usd": 11816685174661.7,  
    "price_usd": 1,  
    "chain_addresses": [  
      {  
        "chain_id": "ETHEREUM",  
        "network_id": "MAINNET",  
        "address": "0xd233d1f6fd11640081abb8db125f722b5dc729dc"  
      }  
    ],  
    "data_start": "2010-07-17",  
    "data_end": "2019-11-03"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**asset\_id** stringnullable

Gets or sets the asset ID.

**name** stringnullable

Gets or sets the name of the asset.

**type\_is\_crypto** int32

Gets or sets a value indicating whether the asset is a cryptocurrency.

**data\_quote\_start** date-timenullable

Gets or sets the start date of quote data.

**data\_quote\_end** date-timenullable

Gets or sets the end date of quote data.

**data\_orderbook\_start** date-timenullable

Gets or sets the start date of order book data.

**data\_orderbook\_end** date-timenullable

Gets or sets the end date of order book data.

**data\_trade\_start** date-timenullable

Gets or sets the start date of trade data.

**data\_trade\_end** date-timenullable

Gets or sets the end date of trade data.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**price\_usd** doublenullable

Gets or sets the USD price of the asset.

**id\_icon** uuidnullable

Gets or sets the ID of the icon for the asset.

**supply\_current** doublenullable

Gets or sets the current supply of the asset.

**supply\_total** doublenullable

Gets or sets the total supply of the asset.

**supply\_max** doublenullable

Gets or sets the maximum supply of the asset.

**chain\_addresses**

object[]

nullable

* Array [

**chain\_id** stringnullable

Gets or sets chain id

**network\_id** stringnullable

Gets or sets network id

**address** stringnullable

Gets or sets chain address

* ]

**data\_start** stringnullable

**data\_end** stringnullable

* ]

```
[  
  {  
    "asset_id": "string",  
    "name": "string",  
    "type_is_crypto": 0,  
    "data_quote_start": "2025-08-12T06:09:08.515Z",  
    "data_quote_end": "2025-08-12T06:09:08.515Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.515Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.515Z",  
    "data_trade_start": "2025-08-12T06:09:08.515Z",  
    "data_trade_end": "2025-08-12T06:09:08.515Z",  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "price_usd": 0,  
    "id_icon": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "supply_current": 0,  
    "supply_total": 0,  
    "supply_max": 0,  
    "chain_addresses": [  
      {  
        "chain_id": "string",  
        "network_id": "string",  
        "address": "string"  
      }  
    ],  
    "data_start": "string",  
    "data_end": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "name": "Bitcoin",  
    "type_is_crypto": 1,  
    "data_quote_start": "2014-02-24T17:43:05.0000000Z",  
    "data_quote_end": "2019-11-03T17:55:07.6724523Z",  
    "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",  
    "data_orderbook_end": "2019-11-03T17:55:17.8592413Z",  
    "data_trade_start": "2010-07-17T23:09:17.0000000Z",  
    "data_trade_end": "2019-11-03T17:55:11.8220000Z",  
    "data_symbols_count": 22711,  
    "volume_1hrs_usd": 102894431436.49,  
    "volume_1day_usd": 2086392323256.16,  
    "volume_1mth_usd": 57929168359984.54,  
    "price_usd": 9166.207274778093,  
    "chain_addresses": [  
      {  
        "chain_id": "ARBITRUM",  
        "network_id": "MAINNET",  
        "address": "0x2f2a2543b76a4166549f7aab2e75bef0aefc5b0f"  
      },  
      {  
        "chain_id": "ETHEREUM",  
        "network_id": "MAINNET",  
        "address": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599"  
      }  
    ],  
    "data_start": "2010-07-17",  
    "data_end": "2019-11-03"  
  },  
  {  
    "asset_id": "USD",  
    "name": "US Dollar",  
    "type_is_crypto": 0,  
    "data_quote_start": "2014-02-24T17:43:05.0000000Z",  
    "data_quote_end": "2019-11-03T17:54:49.3807706Z",  
    "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",  
    "data_orderbook_end": "2019-11-03T17:55:13.1863931Z",  
    "data_trade_start": "2010-07-17T23:09:17.0000000Z",  
    "data_trade_end": "2019-11-03T17:55:07.7870000Z",  
    "data_symbols_count": 10728,  
    "volume_1hrs_usd": 9466454016.52,  
    "volume_1day_usd": 221580758173.49,  
    "volume_1mth_usd": 11816685174661.7,  
    "price_usd": 1,  
    "chain_addresses": [  
      {  
        "chain_id": "ETHEREUM",  
        "network_id": "MAINNET",  
        "address": "0xd233d1f6fd11640081abb8db125f722b5dc729dc"  
      }  
    ],  
    "data_start": "2010-07-17",  
    "data_end": "2019-11-03"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**asset\_id** stringnullable

Gets or sets the asset ID.

**name** stringnullable

Gets or sets the name of the asset.

**type\_is\_crypto** int32

Gets or sets a value indicating whether the asset is a cryptocurrency.

**data\_quote\_start** date-timenullable

Gets or sets the start date of quote data.

**data\_quote\_end** date-timenullable

Gets or sets the end date of quote data.

**data\_orderbook\_start** date-timenullable

Gets or sets the start date of order book data.

**data\_orderbook\_end** date-timenullable

Gets or sets the end date of order book data.

**data\_trade\_start** date-timenullable

Gets or sets the start date of trade data.

**data\_trade\_end** date-timenullable

Gets or sets the end date of trade data.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**price\_usd** doublenullable

Gets or sets the USD price of the asset.

**id\_icon** uuidnullable

Gets or sets the ID of the icon for the asset.

**supply\_current** doublenullable

Gets or sets the current supply of the asset.

**supply\_total** doublenullable

Gets or sets the total supply of the asset.

**supply\_max** doublenullable

Gets or sets the maximum supply of the asset.

**chain\_addresses**

object[]

nullable

* Array [

**chain\_id** stringnullable

Gets or sets chain id

**network\_id** stringnullable

Gets or sets network id

**address** stringnullable

Gets or sets chain address

* ]

**data\_start** stringnullable

**data\_end** stringnullable

* ]

```
[  
  {  
    "asset_id": "string",  
    "name": "string",  
    "type_is_crypto": 0,  
    "data_quote_start": "2025-08-12T06:09:08.515Z",  
    "data_quote_end": "2025-08-12T06:09:08.515Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.515Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.515Z",  
    "data_trade_start": "2025-08-12T06:09:08.515Z",  
    "data_trade_end": "2025-08-12T06:09:08.515Z",  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "price_usd": 0,  
    "id_icon": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "supply_current": 0,  
    "supply_total": 0,  
    "supply_max": 0,  
    "chain_addresses": [  
      {  
        "chain_id": "string",  
        "network_id": "string",  
        "address": "string"  
      }  
    ],  
    "data_start": "string",  
    "data_end": "string"  
  }  
]
```

```
[  
  {  
    "asset_id": "BTC",  
    "name": "Bitcoin",  
    "type_is_crypto": 1,  
    "data_quote_start": "2014-02-24T17:43:05.0000000Z",  
    "data_quote_end": "2019-11-03T17:55:07.6724523Z",  
    "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",  
    "data_orderbook_end": "2019-11-03T17:55:17.8592413Z",  
    "data_trade_start": "2010-07-17T23:09:17.0000000Z",  
    "data_trade_end": "2019-11-03T17:55:11.8220000Z",  
    "data_symbols_count": 22711,  
    "volume_1hrs_usd": 102894431436.49,  
    "volume_1day_usd": 2086392323256.16,  
    "volume_1mth_usd": 57929168359984.54,  
    "price_usd": 9166.207274778093,  
    "chain_addresses": [  
      {  
        "chain_id": "ARBITRUM",  
        "network_id": "MAINNET",  
        "address": "0x2f2a2543b76a4166549f7aab2e75bef0aefc5b0f"  
      },  
      {  
        "chain_id": "ETHEREUM",  
        "network_id": "MAINNET",  
        "address": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599"  
      }  
    ],  
    "data_start": "2010-07-17",  
    "data_end": "2019-11-03"  
  },  
  {  
    "asset_id": "USD",  
    "name": "US Dollar",  
    "type_is_crypto": 0,  
    "data_quote_start": "2014-02-24T17:43:05.0000000Z",  
    "data_quote_end": "2019-11-03T17:54:49.3807706Z",  
    "data_orderbook_start": "2014-02-24T17:43:05.0000000Z",  
    "data_orderbook_end": "2019-11-03T17:55:13.1863931Z",  
    "data_trade_start": "2010-07-17T23:09:17.0000000Z",  
    "data_trade_end": "2019-11-03T17:55:07.7870000Z",  
    "data_symbols_count": 10728,  
    "volume_1hrs_usd": 9466454016.52,  
    "volume_1day_usd": 221580758173.49,  
    "volume_1mth_usd": 11816685174661.7,  
    "price_usd": 1,  
    "chain_addresses": [  
      {  
        "chain_id": "ETHEREUM",  
        "network_id": "MAINNET",  
        "address": "0xd233d1f6fd11640081abb8db125f722b5dc729dc"  
      }  
    ],  
    "data_start": "2010-07-17",  
    "data_end": "2019-11-03"  
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

List all assets](/exchange-rates-api/rest-api-historical/list-all-assets)[Next

List all asset icons](/exchange-rates-api/rest-api-historical/list-all-asset-icons)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.