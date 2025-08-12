List all assets by asset ID | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metadata/list-all-assets-by-asset-id)

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
* List all assets by asset ID

List all assets by asset ID
===========================

```
GET

/v1/assets/:asset_id
--------------------
```

List all assets by asset ID

Request[​](/market-data/rest-api/metadata/list-all-assets-by-asset-id#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id** stringrequired

The asset ID.

Responses[​](/market-data/rest-api/metadata/list-all-assets-by-asset-id#responses "Direct link to Responses")
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
    "data_quote_start": "2025-08-12T06:09:08.702Z",  
    "data_quote_end": "2025-08-12T06:09:08.702Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.702Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.702Z",  
    "data_trade_start": "2025-08-12T06:09:08.702Z",  
    "data_trade_end": "2025-08-12T06:09:08.702Z",  
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
    "data_quote_start": "2025-08-12T06:09:08.703Z",  
    "data_quote_end": "2025-08-12T06:09:08.703Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.703Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.703Z",  
    "data_trade_start": "2025-08-12T06:09:08.703Z",  
    "data_trade_end": "2025-08-12T06:09:08.703Z",  
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
    "data_quote_start": "2025-08-12T06:09:08.704Z",  
    "data_quote_end": "2025-08-12T06:09:08.704Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.704Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.704Z",  
    "data_trade_start": "2025-08-12T06:09:08.704Z",  
    "data_trade_end": "2025-08-12T06:09:08.704Z",  
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
    "data_quote_start": "2025-08-12T06:09:08.705Z",  
    "data_quote_end": "2025-08-12T06:09:08.705Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.705Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.705Z",  
    "data_trade_start": "2025-08-12T06:09:08.705Z",  
    "data_trade_end": "2025-08-12T06:09:08.705Z",  
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

List all asset icons](/market-data/rest-api/metadata/list-all-asset-icons)[Next

List all assets](/market-data/rest-api/metadata/list-all-assets)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.