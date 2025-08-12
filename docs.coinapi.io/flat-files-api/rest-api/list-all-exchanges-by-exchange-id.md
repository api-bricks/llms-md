List all exchanges by exchange\_id | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/rest-api/list-all-exchanges-by-exchange-id)

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

* [Flat Files](/flat-files-api/)
* [Data & Structure](/flat-files-api/data-types/)
* [Snowflake Access](/flat-files-api/snowflake/)
* [S3 API](/flat-files-api/s3-api/)
* [Push API](/flat-files-api/rest-api/push-api)

  + [Introduction](/flat-files-api/rest-api/push-api)
  + [Metadata](/flat-files-api/rest-api/metadata)

    - [List all exchanges](/flat-files-api/rest-api/list-all-exchanges)
    - [List all exchanges by exchange\_id](/flat-files-api/rest-api/list-all-exchanges-by-exchange-id)
    - [List all schemas](/flat-files-api/rest-api/list-all-schemas)
    - [List of symbols for the exchange](/flat-files-api/rest-api/list-of-symbols-for-the-exchange)
  + [Data Storage](/flat-files-api/rest-api/data-storage)
  + [Orders](/flat-files-api/rest-api/orders)

* [Push API](/flat-files-api/rest-api/push-api)
* [Metadata](/flat-files-api/rest-api/metadata)
* List all exchanges by exchange\_id

List all exchanges by exchange\_id
==================================

```
GET

/api/metadata/exchanges/:exchange_id
------------------------------------
```

List all exchanges by exchange\_id

Request[​](/flat-files-api/rest-api/list-all-exchanges-by-exchange-id#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

The ID of the exchange.

Responses[​](/flat-files-api/rest-api/list-all-exchanges-by-exchange-id#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------

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

Gets or sets the exchange ID.

**website** stringnullable

Gets or sets the website URL of the exchange.

**name** stringnullable

Gets or sets the name of the exchange.

**data\_start** stringnullable

Gets the start date of the exchange's data.

**data\_end** stringnullable

Gets the end date of the exchange's data.

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

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:09.076Z",  
    "data_quote_end": "2025-08-12T06:09:09.076Z",  
    "data_orderbook_start": "2025-08-12T06:09:09.076Z",  
    "data_orderbook_end": "2025-08-12T06:09:09.076Z",  
    "data_trade_start": "2025-08-12T06:09:09.076Z",  
    "data_trade_end": "2025-08-12T06:09:09.076Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOIN_CNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.343+00:00",  
    "data_quote_end": "2018-03-09T23:34:52.58+00:00",  
    "data_orderbook_start": "2015-02-15T12:53:50.343+00:00",  
    "data_orderbook_end": "2018-03-09T23:34:52.58+00:00",  
    "data_trade_start": "2013-06-12T14:24:24+00:00",  
    "data_trade_end": "2017-11-01T16:30:39.7077259+00:00",  
    "data_symbols_count": 2  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.263+00:00",  
    "data_quote_end": "2019-11-03T18:22:29.1837496+00:00",  
    "data_orderbook_start": "2015-03-29T21:46:06.263+00:00",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878+00:00",  
    "data_trade_start": "2015-03-29T21:46:08.703+00:00",  
    "data_trade_end": "2019-11-03T18:21:48.277+00:00",  
    "data_symbols_count": 403  
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

Gets the start date of the exchange's data.

**data\_end** stringnullable

Gets the end date of the exchange's data.

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

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:09.076Z",  
    "data_quote_end": "2025-08-12T06:09:09.076Z",  
    "data_orderbook_start": "2025-08-12T06:09:09.076Z",  
    "data_orderbook_end": "2025-08-12T06:09:09.076Z",  
    "data_trade_start": "2025-08-12T06:09:09.076Z",  
    "data_trade_end": "2025-08-12T06:09:09.076Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOIN_CNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.343+00:00",  
    "data_quote_end": "2018-03-09T23:34:52.58+00:00",  
    "data_orderbook_start": "2015-02-15T12:53:50.343+00:00",  
    "data_orderbook_end": "2018-03-09T23:34:52.58+00:00",  
    "data_trade_start": "2013-06-12T14:24:24+00:00",  
    "data_trade_end": "2017-11-01T16:30:39.7077259+00:00",  
    "data_symbols_count": 2  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.263+00:00",  
    "data_quote_end": "2019-11-03T18:22:29.1837496+00:00",  
    "data_orderbook_start": "2015-03-29T21:46:06.263+00:00",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878+00:00",  
    "data_trade_start": "2015-03-29T21:46:08.703+00:00",  
    "data_trade_end": "2019-11-03T18:21:48.277+00:00",  
    "data_symbols_count": 403  
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

Gets the start date of the exchange's data.

**data\_end** stringnullable

Gets the end date of the exchange's data.

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

* ]

```
[  
  {  
    "exchange_id": "string",  
    "website": "string",  
    "name": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:09.077Z",  
    "data_quote_end": "2025-08-12T06:09:09.077Z",  
    "data_orderbook_start": "2025-08-12T06:09:09.077Z",  
    "data_orderbook_end": "2025-08-12T06:09:09.077Z",  
    "data_trade_start": "2025-08-12T06:09:09.077Z",  
    "data_trade_end": "2025-08-12T06:09:09.077Z",  
    "data_trade_count": 0,  
    "data_symbols_count": 0  
  }  
]
```

```
[  
  {  
    "exchange_id": "OKCOIN_CNY",  
    "website": "https://www.okcoin.cn/",  
    "name": "OKCoin CNY",  
    "data_quote_start": "2015-02-15T12:53:50.343+00:00",  
    "data_quote_end": "2018-03-09T23:34:52.58+00:00",  
    "data_orderbook_start": "2015-02-15T12:53:50.343+00:00",  
    "data_orderbook_end": "2018-03-09T23:34:52.58+00:00",  
    "data_trade_start": "2013-06-12T14:24:24+00:00",  
    "data_trade_end": "2017-11-01T16:30:39.7077259+00:00",  
    "data_symbols_count": 2  
  },  
  {  
    "exchange_id": "HUOBI",  
    "website": "https://www.huobi.com/",  
    "name": "Huobi (HBUS)",  
    "data_quote_start": "2015-03-29T21:46:06.263+00:00",  
    "data_quote_end": "2019-11-03T18:22:29.1837496+00:00",  
    "data_orderbook_start": "2015-03-29T21:46:06.263+00:00",  
    "data_orderbook_end": "2019-11-03T18:23:53.2859878+00:00",  
    "data_trade_start": "2015-03-29T21:46:08.703+00:00",  
    "data_trade_end": "2019-11-03T18:21:48.277+00:00",  
    "data_symbols_count": 403  
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

List all exchanges](/flat-files-api/rest-api/list-all-exchanges)[Next

List all schemas](/flat-files-api/rest-api/list-all-schemas)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.