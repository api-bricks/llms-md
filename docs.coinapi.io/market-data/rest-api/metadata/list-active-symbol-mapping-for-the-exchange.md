List active symbol mapping for the exchange | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metadata/list-active-symbol-mapping-for-the-exchange)

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
* List active symbol mapping for the exchange

List active symbol mapping for the exchange
===========================================

```
GET

/v1/symbols/map/:exchange_id
----------------------------
```

List active symbol mapping for the exchange

Request[​](/market-data/rest-api/metadata/list-active-symbol-mapping-for-the-exchange#request "Direct link to Request")
-----------------------------------------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

The ID of the exchange (from the Metadata -> Exchanges)

Responses[​](/market-data/rest-api/metadata/list-active-symbol-mapping-for-the-exchange#responses "Direct link to Responses")
-----------------------------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

* Schema
* Example (from schema)

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol ID.

**symbol\_id\_exchange** stringnullable

The exchange-specific symbol ID.

**coinapi\_datainfo\_id** int32

The CoinAPI DataInfo ID.

**asset\_id\_base\_exchange** stringnullable

The exchange-specific base asset ID.

**asset\_id\_quote\_exchange** stringnullable

The exchange-specific quote asset ID.

**asset\_id\_base** stringnullable

The base asset ID.

**asset\_id\_quote** stringnullable

The quote asset ID.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "symbol_id_exchange": "string",  
    "coinapi_datainfo_id": 0,  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "price_precision": 0,  
    "size_precision": 0  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol ID.

**symbol\_id\_exchange** stringnullable

The exchange-specific symbol ID.

**coinapi\_datainfo\_id** int32

The CoinAPI DataInfo ID.

**asset\_id\_base\_exchange** stringnullable

The exchange-specific base asset ID.

**asset\_id\_quote\_exchange** stringnullable

The exchange-specific quote asset ID.

**asset\_id\_base** stringnullable

The base asset ID.

**asset\_id\_quote** stringnullable

The quote asset ID.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "symbol_id_exchange": "string",  
    "coinapi_datainfo_id": 0,  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "price_precision": 0,  
    "size_precision": 0  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol ID.

**symbol\_id\_exchange** stringnullable

The exchange-specific symbol ID.

**coinapi\_datainfo\_id** int32

The CoinAPI DataInfo ID.

**asset\_id\_base\_exchange** stringnullable

The exchange-specific base asset ID.

**asset\_id\_quote\_exchange** stringnullable

The exchange-specific quote asset ID.

**asset\_id\_base** stringnullable

The base asset ID.

**asset\_id\_quote** stringnullable

The quote asset ID.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "symbol_id_exchange": "string",  
    "coinapi_datainfo_id": 0,  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "price_precision": 0,  
    "size_precision": 0  
  }  
]
```

* Schema
* Example (from schema)

**Schema**

* Array [

**symbol\_id** stringnullable

The symbol ID.

**symbol\_id\_exchange** stringnullable

The exchange-specific symbol ID.

**coinapi\_datainfo\_id** int32

The CoinAPI DataInfo ID.

**asset\_id\_base\_exchange** stringnullable

The exchange-specific base asset ID.

**asset\_id\_quote\_exchange** stringnullable

The exchange-specific quote asset ID.

**asset\_id\_base** stringnullable

The base asset ID.

**asset\_id\_quote** stringnullable

The quote asset ID.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "symbol_id_exchange": "string",  
    "coinapi_datainfo_id": 0,  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "price_precision": 0,  
    "size_precision": 0  
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

Introduction](/market-data/rest-api/metadata/coinapi-market-data-rest-api)[Next

List all active symbols](/market-data/rest-api/metadata/list-all-active-symbols)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.