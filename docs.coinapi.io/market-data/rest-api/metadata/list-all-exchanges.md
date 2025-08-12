List all exchanges | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metadata/list-all-exchanges)

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
* List all exchanges

List all exchanges
==================

```
GET

/v1/exchanges
-------------
```

Get a detailed list of exchanges provided by the system.

info

Properties of the output are providing aggregated information from across all symbols related to the specific exchange. If you need to calculate your aggregation (e.g., limiting only the particular type of symbols), you should use /v1/symbols endpoint as a data source.

Request[​](/market-data/rest-api/metadata/list-all-exchanges#request "Direct link to Request")
----------------------------------------------------------------------------------------------

### Query Parameters

**filter\_exchange\_id** string

Comma or semicolon delimited exchange identifiers used to filter response. (optional, eg. `BITSTAMP;GEMINI`)

Responses[​](/market-data/rest-api/metadata/list-all-exchanges#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------

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

Gets or sets the exchange ID.

**website** stringnullable

Gets or sets the website URL of the exchange.

**name** stringnullable

Gets or sets the name of the exchange.

**data\_start** stringnullable

**data\_end** stringnullable

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

**data\_trade\_count** int64nullable

Gets or sets the number of trades.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**metric\_id** string[]nullable

Gets or sets the list of metric IDs.

**icons**

object[]

nullable

Gets or sets the list of icons for the exchange.

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

**rank** double

Rank of the exchange.

**integration\_status** stringnullable

Status of the integration

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.712Z",  
    "data_quote_end": "2025-08-12T06:09:08.712Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.712Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.712Z",  
    "data_trade_start": "2025-08-12T06:09:08.712Z",  
    "data_trade_end": "2025-08-12T06:09:08.712Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "metric_id": [  
      "string"  
    ],  
    "icons": [  
      {  
        "exchange_id": "string",  
        "asset_id": "string",  
        "url": "string"  
      }  
    ],  
    "rank": 0,  
    "integration_status": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOINCNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.3430000Z",  
    "data_quote_end": "2018-03-09T23:34:52.5800000Z",  
    "data_orderbook_start": "2015-02-15T12:53:50.3430000Z",  
    "data_orderbook_end": "2018-03-09T23:34:52.5800000Z",  
    "data_trade_start": "2013-06-12T14:24:24.0000000Z",  
    "data_trade_end": "2017-11-01T16:30:39.7077259Z",  
    "data_symbols_count": 2,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "rank": 1  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.2630000Z",  
    "data_quote_end": "2019-11-03T18:22:29.1837496Z",  
    "data_orderbook_start": "2015-03-29T21:46:06.2630000Z",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878Z",  
    "data_trade_start": "2015-03-29T21:46:08.7030000Z",  
    "data_trade_end": "2019-11-03T18:21:48.2770000Z",  
    "data_symbols_count": 403,  
    "volume_1hrs_usd": 1605.8,  
    "volume_1day_usd": 59957.44,  
    "volume_1mth_usd": 1259508.43,  
    "rank": 5  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**website** stringnullable

Gets or sets the website URL of the exchange.

**name** stringnullable

Gets or sets the name of the exchange.

**data\_start** stringnullable

**data\_end** stringnullable

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

**data\_trade\_count** int64nullable

Gets or sets the number of trades.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**metric\_id** string[]nullable

Gets or sets the list of metric IDs.

**icons**

object[]

nullable

Gets or sets the list of icons for the exchange.

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

**rank** double

Rank of the exchange.

**integration\_status** stringnullable

Status of the integration

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.713Z",  
    "data_quote_end": "2025-08-12T06:09:08.713Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.713Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.713Z",  
    "data_trade_start": "2025-08-12T06:09:08.713Z",  
    "data_trade_end": "2025-08-12T06:09:08.713Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "metric_id": [  
      "string"  
    ],  
    "icons": [  
      {  
        "exchange_id": "string",  
        "asset_id": "string",  
        "url": "string"  
      }  
    ],  
    "rank": 0,  
    "integration_status": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOINCNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.3430000Z",  
    "data_quote_end": "2018-03-09T23:34:52.5800000Z",  
    "data_orderbook_start": "2015-02-15T12:53:50.3430000Z",  
    "data_orderbook_end": "2018-03-09T23:34:52.5800000Z",  
    "data_trade_start": "2013-06-12T14:24:24.0000000Z",  
    "data_trade_end": "2017-11-01T16:30:39.7077259Z",  
    "data_symbols_count": 2,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "rank": 1  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.2630000Z",  
    "data_quote_end": "2019-11-03T18:22:29.1837496Z",  
    "data_orderbook_start": "2015-03-29T21:46:06.2630000Z",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878Z",  
    "data_trade_start": "2015-03-29T21:46:08.7030000Z",  
    "data_trade_end": "2019-11-03T18:21:48.2770000Z",  
    "data_symbols_count": 403,  
    "volume_1hrs_usd": 1605.8,  
    "volume_1day_usd": 59957.44,  
    "volume_1mth_usd": 1259508.43,  
    "rank": 5  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**website** stringnullable

Gets or sets the website URL of the exchange.

**name** stringnullable

Gets or sets the name of the exchange.

**data\_start** stringnullable

**data\_end** stringnullable

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

**data\_trade\_count** int64nullable

Gets or sets the number of trades.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**metric\_id** string[]nullable

Gets or sets the list of metric IDs.

**icons**

object[]

nullable

Gets or sets the list of icons for the exchange.

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

**rank** double

Rank of the exchange.

**integration\_status** stringnullable

Status of the integration

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.713Z",  
    "data_quote_end": "2025-08-12T06:09:08.713Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.713Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.713Z",  
    "data_trade_start": "2025-08-12T06:09:08.713Z",  
    "data_trade_end": "2025-08-12T06:09:08.713Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "metric_id": [  
      "string"  
    ],  
    "icons": [  
      {  
        "exchange_id": "string",  
        "asset_id": "string",  
        "url": "string"  
      }  
    ],  
    "rank": 0,  
    "integration_status": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOINCNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.3430000Z",  
    "data_quote_end": "2018-03-09T23:34:52.5800000Z",  
    "data_orderbook_start": "2015-02-15T12:53:50.3430000Z",  
    "data_orderbook_end": "2018-03-09T23:34:52.5800000Z",  
    "data_trade_start": "2013-06-12T14:24:24.0000000Z",  
    "data_trade_end": "2017-11-01T16:30:39.7077259Z",  
    "data_symbols_count": 2,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "rank": 1  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.2630000Z",  
    "data_quote_end": "2019-11-03T18:22:29.1837496Z",  
    "data_orderbook_start": "2015-03-29T21:46:06.2630000Z",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878Z",  
    "data_trade_start": "2015-03-29T21:46:08.7030000Z",  
    "data_trade_end": "2019-11-03T18:21:48.2770000Z",  
    "data_symbols_count": 403,  
    "volume_1hrs_usd": 1605.8,  
    "volume_1day_usd": 59957.44,  
    "volume_1mth_usd": 1259508.43,  
    "rank": 5  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID.

**website** stringnullable

Gets or sets the website URL of the exchange.

**name** stringnullable

Gets or sets the name of the exchange.

**data\_start** stringnullable

**data\_end** stringnullable

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

**data\_trade\_count** int64nullable

Gets or sets the number of trades.

**data\_symbols\_count** int64nullable

Gets or sets the number of symbols.

**volume\_1hrs\_usd** doublenullable

Gets or sets the USD volume in the last 1 hour.

**volume\_1day\_usd** doublenullable

Gets or sets the USD volume in the last 1 day.

**volume\_1mth\_usd** doublenullable

Gets or sets the USD volume in the last 1 month.

**metric\_id** string[]nullable

Gets or sets the list of metric IDs.

**icons**

object[]

nullable

Gets or sets the list of icons for the exchange.

* Array [

**exchange\_id** stringnullable

Gets or sets the exchange ID associated with the icon.

**asset\_id** stringnullable

Gets or sets the asset ID associated with the icon.

**url** stringnullable

Gets or sets the URL of the icon.

* ]

**rank** double

Rank of the exchange.

**integration\_status** stringnullable

Status of the integration

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.714Z",  
    "data_quote_end": "2025-08-12T06:09:08.714Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.714Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.714Z",  
    "data_trade_start": "2025-08-12T06:09:08.714Z",  
    "data_trade_end": "2025-08-12T06:09:08.714Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "metric_id": [  
      "string"  
    ],  
    "icons": [  
      {  
        "exchange_id": "string",  
        "asset_id": "string",  
        "url": "string"  
      }  
    ],  
    "rank": 0,  
    "integration_status": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOINCNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.3430000Z",  
    "data_quote_end": "2018-03-09T23:34:52.5800000Z",  
    "data_orderbook_start": "2015-02-15T12:53:50.3430000Z",  
    "data_orderbook_end": "2018-03-09T23:34:52.5800000Z",  
    "data_trade_start": "2013-06-12T14:24:24.0000000Z",  
    "data_trade_end": "2017-11-01T16:30:39.7077259Z",  
    "data_symbols_count": 2,  
    "volume_1hrs_usd": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth_usd": 0,  
    "rank": 1  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.2630000Z",  
    "data_quote_end": "2019-11-03T18:22:29.1837496Z",  
    "data_orderbook_start": "2015-03-29T21:46:06.2630000Z",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878Z",  
    "data_trade_start": "2015-03-29T21:46:08.7030000Z",  
    "data_trade_end": "2019-11-03T18:21:48.2770000Z",  
    "data_symbols_count": 403,  
    "volume_1hrs_usd": 1605.8,  
    "volume_1day_usd": 59957.44,  
    "volume_1mth_usd": 1259508.43,  
    "rank": 5  
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

List all exchanges by exchange\_id](/market-data/rest-api/metadata/list-all-exchanges-by-exchange-id)[Next

List all historical symbols for an exchange.](/market-data/rest-api/metadata/list-all-historical-symbols-for-an-exchange)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.