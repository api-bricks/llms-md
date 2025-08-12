List of exchanges | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Stock Data API](/stock-api/)
* [Authentication](/stock-api/authentication)
* [Metadata Tables](/stock-api/metadata-tables/introduction)
* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)

  + [Introduction](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
  + [Native IEX](/stock-api/rest-api-historical/get-admin-messages)
  + [Metadata](/stock-api/rest-api-historical/list-of-exchanges)

    - [List of exchanges](/stock-api/rest-api-historical/list-of-exchanges)
    - [List of symbols for the exchange](/stock-api/rest-api-historical/list-of-symbols-for-the-exchange)
  + [Ohlcv](/stock-api/rest-api-historical/list-all-periods)
* [JSON RPC](/stock-api/jsonrpc-api)

* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
* Metadata
* List of exchanges

List of exchanges
=================

```
GET

/v1/exchanges
-------------
```

List of exchanges

Responses[​](/stock-api/rest-api-historical/list-of-exchanges#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------------

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

**last\_datapoint\_date** stringnullable

**mic** stringnullable

**operating\_mic** stringnullable

**oprt\_sgmt** stringnullable

**market\_name\_institution\_description** stringnullable

**legal\_entity\_name** stringnullable

**lei** stringnullable

**market\_category\_code** stringnullable

**acronym** stringnullable

**iso\_country\_code** stringnullable

**city** stringnullable

**website** stringnullable

**status** stringnullable

**creation\_date** date-timenullable

**last\_update\_date** date-timenullable

**last\_validation\_date** date-timenullable

**expiry\_date** date-timenullable

**comments** stringnullable

* ]

```
[  
  {  
    "exchange_id": "string",  
    "last_datapoint_date": "string",  
    "mic": "string",  
    "operating_mic": "string",  
    "oprt_sgmt": "string",  
    "market_name_institution_description": "string",  
    "legal_entity_name": "string",  
    "lei": "string",  
    "market_category_code": "string",  
    "acronym": "string",  
    "iso_country_code": "string",  
    "city": "string",  
    "website": "string",  
    "status": "string",  
    "creation_date": "2025-08-12T06:08:07.160Z",  
    "last_update_date": "2025-08-12T06:08:07.160Z",  
    "last_validation_date": "2025-08-12T06:08:07.160Z",  
    "expiry_date": "2025-08-12T06:08:07.160Z",  
    "comments": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "IEXG",  
    "mic": "IEXG",  
    "operating_mic": "IEXG",  
    "oprt_sgmt": "OPRT",  
    "market_name_institution_description": "INVESTORS EXCHANGE",  
    "legal_entity_name": "INVESTORS EXCHANGE LLC",  
    "market_category_code": "NSPD",  
    "acronym": "IEX",  
    "iso_country_code": "US",  
    "city": "NEW YORK",  
    "website": "WWW.IEX.IO",  
    "status": "ACTIVE",  
    "creation_date": "2013-10-28T00:00:00.0000000Z",  
    "last_update_date": "2022-10-24T00:00:00.0000000Z"  
  },  
  {  
    "exchange_id": "XNAS",  
    "mic": "XNAS",  
    "operating_mic": "XNAS",  
    "oprt_sgmt": "OPRT",  
    "market_name_institution_description": "NASDAQ - ALL MARKETS",  
    "market_category_code": "NSPD",  
    "acronym": "NASDAQ",  
    "iso_country_code": "US",  
    "city": "NEW YORK",  
    "website": "WWW.NASDAQ.COM",  
    "status": "ACTIVE",  
    "creation_date": "2005-06-27T00:00:00.0000000Z",  
    "last_update_date": "2005-06-27T00:00:00.0000000Z"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

**last\_datapoint\_date** stringnullable

**mic** stringnullable

**operating\_mic** stringnullable

**oprt\_sgmt** stringnullable

**market\_name\_institution\_description** stringnullable

**legal\_entity\_name** stringnullable

**lei** stringnullable

**market\_category\_code** stringnullable

**acronym** stringnullable

**iso\_country\_code** stringnullable

**city** stringnullable

**website** stringnullable

**status** stringnullable

**creation\_date** date-timenullable

**last\_update\_date** date-timenullable

**last\_validation\_date** date-timenullable

**expiry\_date** date-timenullable

**comments** stringnullable

* ]

```
[  
  {  
    "exchange_id": "string",  
    "last_datapoint_date": "string",  
    "mic": "string",  
    "operating_mic": "string",  
    "oprt_sgmt": "string",  
    "market_name_institution_description": "string",  
    "legal_entity_name": "string",  
    "lei": "string",  
    "market_category_code": "string",  
    "acronym": "string",  
    "iso_country_code": "string",  
    "city": "string",  
    "website": "string",  
    "status": "string",  
    "creation_date": "2025-08-12T06:08:07.161Z",  
    "last_update_date": "2025-08-12T06:08:07.161Z",  
    "last_validation_date": "2025-08-12T06:08:07.161Z",  
    "expiry_date": "2025-08-12T06:08:07.161Z",  
    "comments": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "IEXG",  
    "mic": "IEXG",  
    "operating_mic": "IEXG",  
    "oprt_sgmt": "OPRT",  
    "market_name_institution_description": "INVESTORS EXCHANGE",  
    "legal_entity_name": "INVESTORS EXCHANGE LLC",  
    "market_category_code": "NSPD",  
    "acronym": "IEX",  
    "iso_country_code": "US",  
    "city": "NEW YORK",  
    "website": "WWW.IEX.IO",  
    "status": "ACTIVE",  
    "creation_date": "2013-10-28T00:00:00.0000000Z",  
    "last_update_date": "2022-10-24T00:00:00.0000000Z"  
  },  
  {  
    "exchange_id": "XNAS",  
    "mic": "XNAS",  
    "operating_mic": "XNAS",  
    "oprt_sgmt": "OPRT",  
    "market_name_institution_description": "NASDAQ - ALL MARKETS",  
    "market_category_code": "NSPD",  
    "acronym": "NASDAQ",  
    "iso_country_code": "US",  
    "city": "NEW YORK",  
    "website": "WWW.NASDAQ.COM",  
    "status": "ACTIVE",  
    "creation_date": "2005-06-27T00:00:00.0000000Z",  
    "last_update_date": "2005-06-27T00:00:00.0000000Z"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**exchange\_id** stringnullable

**last\_datapoint\_date** stringnullable

**mic** stringnullable

**operating\_mic** stringnullable

**oprt\_sgmt** stringnullable

**market\_name\_institution\_description** stringnullable

**legal\_entity\_name** stringnullable

**lei** stringnullable

**market\_category\_code** stringnullable

**acronym** stringnullable

**iso\_country\_code** stringnullable

**city** stringnullable

**website** stringnullable

**status** stringnullable

**creation\_date** date-timenullable

**last\_update\_date** date-timenullable

**last\_validation\_date** date-timenullable

**expiry\_date** date-timenullable

**comments** stringnullable

* ]

```
[  
  {  
    "exchange_id": "string",  
    "last_datapoint_date": "string",  
    "mic": "string",  
    "operating_mic": "string",  
    "oprt_sgmt": "string",  
    "market_name_institution_description": "string",  
    "legal_entity_name": "string",  
    "lei": "string",  
    "market_category_code": "string",  
    "acronym": "string",  
    "iso_country_code": "string",  
    "city": "string",  
    "website": "string",  
    "status": "string",  
    "creation_date": "2025-08-12T06:08:07.161Z",  
    "last_update_date": "2025-08-12T06:08:07.161Z",  
    "last_validation_date": "2025-08-12T06:08:07.161Z",  
    "expiry_date": "2025-08-12T06:08:07.161Z",  
    "comments": "string"  
  }  
]
```

```
[  
  {  
    "exchange_id": "IEXG",  
    "mic": "IEXG",  
    "operating_mic": "IEXG",  
    "oprt_sgmt": "OPRT",  
    "market_name_institution_description": "INVESTORS EXCHANGE",  
    "legal_entity_name": "INVESTORS EXCHANGE LLC",  
    "market_category_code": "NSPD",  
    "acronym": "IEX",  
    "iso_country_code": "US",  
    "city": "NEW YORK",  
    "website": "WWW.IEX.IO",  
    "status": "ACTIVE",  
    "creation_date": "2013-10-28T00:00:00.0000000Z",  
    "last_update_date": "2022-10-24T00:00:00.0000000Z"  
  },  
  {  
    "exchange_id": "XNAS",  
    "mic": "XNAS",  
    "operating_mic": "XNAS",  
    "oprt_sgmt": "OPRT",  
    "market_name_institution_description": "NASDAQ - ALL MARKETS",  
    "market_category_code": "NSPD",  
    "acronym": "NASDAQ",  
    "iso_country_code": "US",  
    "city": "NEW YORK",  
    "website": "WWW.NASDAQ.COM",  
    "status": "ACTIVE",  
    "creation_date": "2005-06-27T00:00:00.0000000Z",  
    "last_update_date": "2005-06-27T00:00:00.0000000Z"  
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

Get Trades](/stock-api/rest-api-historical/get-trades)[Next

List of symbols for the exchange](/stock-api/rest-api-historical/list-of-symbols-for-the-exchange)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.