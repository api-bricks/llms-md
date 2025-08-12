Current quotes for a specific symbol | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol)

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
  + [Ohlcv](/market-data/rest-api/ohlcv/)
  + [Options](/market-data/rest-api/options/)
  + [Order Book](/market-data/rest-api/order-book/)
  + [Order Book L3](/market-data/rest-api/order-book-l3/)
  + [Quotes](/market-data/rest-api/quotes/)

    - [Introduction](/market-data/rest-api/quotes/coinapi-market-data-rest-api)
    - [Current data](/market-data/rest-api/quotes/current-data)
    - [Current quotes for a specific symbol](/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol)
    - [Historical data](/market-data/rest-api/quotes/historical-data)
    - [Latest data](/market-data/rest-api/quotes/latest-data)
    - [Latest quote updates for a specific symbol](/market-data/rest-api/quotes/latest-quote-updates-for-a-specific-symbol)
  + [Trades](/market-data/rest-api/trades/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* REST API
* [Quotes](/market-data/rest-api/quotes/)
* Current quotes for a specific symbol

Current quotes for a specific symbol
====================================

```
GET

/v1/quotes/:symbol_id/current
-----------------------------
```

Current quotes for a specific symbol

Request[​](/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol#request "Direct link to Request")
--------------------------------------------------------------------------------------------------------------

### Path Parameters

**symbol\_id** stringrequired

The symbol identifier (from the Metadata -> Symbols)

Responses[​](/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------------------------

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

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the quote trade.

**time\_coinapi** date-time

The CoinAPI time when the quote trade was received.

**ask\_price** doublenullable

The best asking price.

**ask\_size** doublenullable

The volume resting on the best ask. If the value is equal to zero, then the size is unknown.

**bid\_price** doublenullable

The best bidding price.

**bid\_size** doublenullable

The volume resting on the best bid. If the value is equal to zero, then the size is unknown.

**last\_trade**

object

Represents the last executed transaction.

**time\_exchange** date-time

The exchange time of the last trade.

**time\_coinapi** date-time

The CoinAPI time when the last trade was received.

**uuid** uuid

The UUID of the last trade.

**price** double

The price of the last trade.

**size** double

The size of the last trade.

**taker\_side** stringnullable

The taker side of the last trade.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:09.001Z",  
  "time_coinapi": "2025-08-12T06:09:09.001Z",  
  "ask_price": 0,  
  "ask_size": 0,  
  "bid_price": 0,  
  "bid_size": 0,  
  "last_trade": {  
    "time_exchange": "2025-08-12T06:09:09.002Z",  
    "time_coinapi": "2025-08-12T06:09:09.002Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string"  
  }  
}
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the quote trade.

**time\_coinapi** date-time

The CoinAPI time when the quote trade was received.

**ask\_price** doublenullable

The best asking price.

**ask\_size** doublenullable

The volume resting on the best ask. If the value is equal to zero, then the size is unknown.

**bid\_price** doublenullable

The best bidding price.

**bid\_size** doublenullable

The volume resting on the best bid. If the value is equal to zero, then the size is unknown.

**last\_trade**

object

Represents the last executed transaction.

**time\_exchange** date-time

The exchange time of the last trade.

**time\_coinapi** date-time

The CoinAPI time when the last trade was received.

**uuid** uuid

The UUID of the last trade.

**price** double

The price of the last trade.

**size** double

The size of the last trade.

**taker\_side** stringnullable

The taker side of the last trade.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:09.002Z",  
  "time_coinapi": "2025-08-12T06:09:09.002Z",  
  "ask_price": 0,  
  "ask_size": 0,  
  "bid_price": 0,  
  "bid_size": 0,  
  "last_trade": {  
    "time_exchange": "2025-08-12T06:09:09.002Z",  
    "time_coinapi": "2025-08-12T06:09:09.002Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string"  
  }  
}
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the quote trade.

**time\_coinapi** date-time

The CoinAPI time when the quote trade was received.

**ask\_price** doublenullable

The best asking price.

**ask\_size** doublenullable

The volume resting on the best ask. If the value is equal to zero, then the size is unknown.

**bid\_price** doublenullable

The best bidding price.

**bid\_size** doublenullable

The volume resting on the best bid. If the value is equal to zero, then the size is unknown.

**last\_trade**

object

Represents the last executed transaction.

**time\_exchange** date-time

The exchange time of the last trade.

**time\_coinapi** date-time

The CoinAPI time when the last trade was received.

**uuid** uuid

The UUID of the last trade.

**price** double

The price of the last trade.

**size** double

The size of the last trade.

**taker\_side** stringnullable

The taker side of the last trade.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:09.003Z",  
  "time_coinapi": "2025-08-12T06:09:09.003Z",  
  "ask_price": 0,  
  "ask_size": 0,  
  "bid_price": 0,  
  "bid_size": 0,  
  "last_trade": {  
    "time_exchange": "2025-08-12T06:09:09.003Z",  
    "time_coinapi": "2025-08-12T06:09:09.003Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string"  
  }  
}
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the quote trade.

**time\_coinapi** date-time

The CoinAPI time when the quote trade was received.

**ask\_price** doublenullable

The best asking price.

**ask\_size** doublenullable

The volume resting on the best ask. If the value is equal to zero, then the size is unknown.

**bid\_price** doublenullable

The best bidding price.

**bid\_size** doublenullable

The volume resting on the best bid. If the value is equal to zero, then the size is unknown.

**last\_trade**

object

Represents the last executed transaction.

**time\_exchange** date-time

The exchange time of the last trade.

**time\_coinapi** date-time

The CoinAPI time when the last trade was received.

**uuid** uuid

The UUID of the last trade.

**price** double

The price of the last trade.

**size** double

The size of the last trade.

**taker\_side** stringnullable

The taker side of the last trade.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:09.003Z",  
  "time_coinapi": "2025-08-12T06:09:09.003Z",  
  "ask_price": 0,  
  "ask_size": 0,  
  "bid_price": 0,  
  "bid_size": 0,  
  "last_trade": {  
    "time_exchange": "2025-08-12T06:09:09.003Z",  
    "time_coinapi": "2025-08-12T06:09:09.003Z",  
    "uuid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",  
    "price": 0,  
    "size": 0,  
    "taker_side": "string"  
  }  
}
```

```
[  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
  },  
  {  
    "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
    "time_exchange": "2013-09-28T22:40:50.0000000Z",  
    "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
    "ask_price": 770,  
    "ask_size": 3252,  
    "bid_price": 760,  
    "bid_size": 124,  
    "last_trade": {  
      "time_exchange": "2017-03-18T22:42:21.3763342Z",  
      "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
      "uuid": "1ea8adc5-6459-47ca-adbf-0c3f8c729bb2",  
      "price": 770,  
      "size": 0.05,  
      "taker_side": "SELL"  
    }  
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

Current data](/market-data/rest-api/quotes/current-data)[Next

Historical data](/market-data/rest-api/quotes/historical-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.