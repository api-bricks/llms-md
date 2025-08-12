Current order book by symbol\_id | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/order-book-l3/current-order-book-by-symbol-id)

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

    - [Introduction](/market-data/rest-api/order-book-l3/coinapi-market-data-rest-api)
    - [Current order book by symbol\_id](/market-data/rest-api/order-book-l3/current-order-book-by-symbol-id)
    - [Current order books](/market-data/rest-api/order-book-l3/current-order-books)
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
* [Order Book L3](/market-data/rest-api/order-book-l3/)
* Current order book by symbol\_id

Current order book by symbol\_id
================================

```
GET

/v1/orderbooks3/:symbol_id/current
----------------------------------
```

Retrieves the current order book for the specified symbol.

Request[​](/market-data/rest-api/order-book-l3/current-order-book-by-symbol-id#request "Direct link to Request")
----------------------------------------------------------------------------------------------------------------

### Path Parameters

**symbol\_id** stringrequired

The symbol ID (from the Metadata -> Symbols)



### Query Parameters

**limit\_levels** int32

The maximum number of levels to include in the response.

Responses[​](/market-data/rest-api/order-book-l3/current-order-book-by-symbol-id#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------------------

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

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.932Z",  
  "time_coinapi": "2025-08-12T06:09:08.932Z"  
}
```

```
{  
  "symbol_id": "COINBASE_SPOT_BCH_USD",  
  "time_exchange": "2020-08-27T10:28:35.6111130Z",  
  "time_coinapi": "2020-08-27T10:28:35.6766461Z",  
  "asks": [  
    {  
      "id": "3c5e789c-4c84-448a-9c5d-50532ea1ccbb",  
      "price": 272.89,  
      "size": 1  
    },  
    {  
      "id": "c64a76ba-5107-4c1b-b788-271ee88df318",  
      "price": 272.9,  
      "size": 18  
    }  
  ],  
  "bids": [  
    {  
      "id": "100d5004-f4e0-4e92-a571-392403d5b073",  
      "price": 272.83,  
      "size": 18  
    },  
    {  
      "id": "0889cf06-4a9d-4519-98e6-fac5dcb7afbf",  
      "price": 272.83,  
      "size": 0.64185083  
    }  
  ]  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.932Z",  
  "time_coinapi": "2025-08-12T06:09:08.932Z"  
}
```

```
{  
  "symbol_id": "COINBASE_SPOT_BCH_USD",  
  "time_exchange": "2020-08-27T10:28:35.6111130Z",  
  "time_coinapi": "2020-08-27T10:28:35.6766461Z",  
  "asks": [  
    {  
      "id": "3c5e789c-4c84-448a-9c5d-50532ea1ccbb",  
      "price": 272.89,  
      "size": 1  
    },  
    {  
      "id": "c64a76ba-5107-4c1b-b788-271ee88df318",  
      "price": 272.9,  
      "size": 18  
    }  
  ],  
  "bids": [  
    {  
      "id": "100d5004-f4e0-4e92-a571-392403d5b073",  
      "price": 272.83,  
      "size": 18  
    },  
    {  
      "id": "0889cf06-4a9d-4519-98e6-fac5dcb7afbf",  
      "price": 272.83,  
      "size": 0.64185083  
    }  
  ]  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.932Z",  
  "time_coinapi": "2025-08-12T06:09:08.932Z"  
}
```

```
{  
  "symbol_id": "COINBASE_SPOT_BCH_USD",  
  "time_exchange": "2020-08-27T10:28:35.6111130Z",  
  "time_coinapi": "2020-08-27T10:28:35.6766461Z",  
  "asks": [  
    {  
      "id": "3c5e789c-4c84-448a-9c5d-50532ea1ccbb",  
      "price": 272.89,  
      "size": 1  
    },  
    {  
      "id": "c64a76ba-5107-4c1b-b788-271ee88df318",  
      "price": 272.9,  
      "size": 18  
    }  
  ],  
  "bids": [  
    {  
      "id": "100d5004-f4e0-4e92-a571-392403d5b073",  
      "price": 272.83,  
      "size": 18  
    },  
    {  
      "id": "0889cf06-4a9d-4519-98e6-fac5dcb7afbf",  
      "price": 272.83,  
      "size": 0.64185083  
    }  
  ]  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**symbol\_id** stringnullable

The symbol identifier.

**time\_exchange** date-time

The exchange time of the order book.

**time\_coinapi** date-time

The CoinAPI time when the order book was received.

**asks** nullable

The asks made by market makers.

**bids** nullable

The bids made by market makers.

```
{  
  "symbol_id": "string",  
  "time_exchange": "2025-08-12T06:09:08.932Z",  
  "time_coinapi": "2025-08-12T06:09:08.932Z"  
}
```

```
{  
  "symbol_id": "COINBASE_SPOT_BCH_USD",  
  "time_exchange": "2020-08-27T10:28:35.6111130Z",  
  "time_coinapi": "2020-08-27T10:28:35.6766461Z",  
  "asks": [  
    {  
      "id": "3c5e789c-4c84-448a-9c5d-50532ea1ccbb",  
      "price": 272.89,  
      "size": 1  
    },  
    {  
      "id": "c64a76ba-5107-4c1b-b788-271ee88df318",  
      "price": 272.9,  
      "size": 18  
    }  
  ],  
  "bids": [  
    {  
      "id": "100d5004-f4e0-4e92-a571-392403d5b073",  
      "price": 272.83,  
      "size": 18  
    },  
    {  
      "id": "0889cf06-4a9d-4519-98e6-fac5dcb7afbf",  
      "price": 272.83,  
      "size": 0.64185083  
    }  
  ]  
}
```

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/market-data/rest-api/order-book-l3/coinapi-market-data-rest-api)[Next

Current order books](/market-data/rest-api/order-book-l3/current-order-books)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.