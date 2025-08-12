List of symbols for the exchange | FinFeedAPI.com Documentation




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
* List of symbols for the exchange

List of symbols for the exchange
================================

```
GET

/v1/symbols/:exchange_id
------------------------
```

List of symbols for the exchange

Request[​](/stock-api/rest-api-historical/list-of-symbols-for-the-exchange#request "Direct link to Request")
------------------------------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

Responses[​](/stock-api/rest-api-historical/list-of-symbols-for-the-exchange#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------------------

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

**symbol\_id** stringnullable

**exchange\_id** stringnullable

**security\_category** stringnullable

**name** stringnullable

**date** stringnullable

**asset\_class** stringnullable

**cfi\_code** stringnullable

**cfi\_category** stringnullable

**cfi\_group** stringnullable

**cfi\_attribute1** stringnullable

**cfi\_attribute2** stringnullable

**cfi\_attribute3** stringnullable

**cfi\_attribute4** stringnullable

**cfi\_category\_desc** stringnullable

**cfi\_group\_desc** stringnullable

**cfi\_attribute1\_desc** stringnullable

**cfi\_attribute2\_desc** stringnullable

**cfi\_attribute3\_desc** stringnullable

**cfi\_attribute4\_desc** stringnullable

* ]

```
[  
  {  
    "symbol_id": "string",  
    "exchange_id": "string",  
    "security_category": "string",  
    "name": "string",  
    "date": "string",  
    "asset_class": "string",  
    "cfi_code": "string",  
    "cfi_category": "string",  
    "cfi_group": "string",  
    "cfi_attribute1": "string",  
    "cfi_attribute2": "string",  
    "cfi_attribute3": "string",  
    "cfi_attribute4": "string",  
    "cfi_category_desc": "string",  
    "cfi_group_desc": "string",  
    "cfi_attribute1_desc": "string",  
    "cfi_attribute2_desc": "string",  
    "cfi_attribute3_desc": "string",  
    "cfi_attribute4_desc": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "TSLA",  
    "exchange_id": "IEXG",  
    "security_category": "Common Stock",  
    "name": "TESLA INC",  
    "date": "2025-08-12"  
  },  
  {  
    "symbol_id": "NVDA",  
    "exchange_id": "IEXG",  
    "security_category": "Common Stock",  
    "name": "NVIDIA CORP",  
    "date": "2025-08-12"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

**exchange\_id** stringnullable

**security\_category** stringnullable

**name** stringnullable

**date** stringnullable

**asset\_class** stringnullable

**cfi\_code** stringnullable

**cfi\_category** stringnullable

**cfi\_group** stringnullable

**cfi\_attribute1** stringnullable

**cfi\_attribute2** stringnullable

**cfi\_attribute3** stringnullable

**cfi\_attribute4** stringnullable

**cfi\_category\_desc** stringnullable

**cfi\_group\_desc** stringnullable

**cfi\_attribute1\_desc** stringnullable

**cfi\_attribute2\_desc** stringnullable

**cfi\_attribute3\_desc** stringnullable

**cfi\_attribute4\_desc** stringnullable

* ]

```
[  
  {  
    "symbol_id": "string",  
    "exchange_id": "string",  
    "security_category": "string",  
    "name": "string",  
    "date": "string",  
    "asset_class": "string",  
    "cfi_code": "string",  
    "cfi_category": "string",  
    "cfi_group": "string",  
    "cfi_attribute1": "string",  
    "cfi_attribute2": "string",  
    "cfi_attribute3": "string",  
    "cfi_attribute4": "string",  
    "cfi_category_desc": "string",  
    "cfi_group_desc": "string",  
    "cfi_attribute1_desc": "string",  
    "cfi_attribute2_desc": "string",  
    "cfi_attribute3_desc": "string",  
    "cfi_attribute4_desc": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "TSLA",  
    "exchange_id": "IEXG",  
    "security_category": "Common Stock",  
    "name": "TESLA INC",  
    "date": "2025-08-12"  
  },  
  {  
    "symbol_id": "NVDA",  
    "exchange_id": "IEXG",  
    "security_category": "Common Stock",  
    "name": "NVIDIA CORP",  
    "date": "2025-08-12"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

**exchange\_id** stringnullable

**security\_category** stringnullable

**name** stringnullable

**date** stringnullable

**asset\_class** stringnullable

**cfi\_code** stringnullable

**cfi\_category** stringnullable

**cfi\_group** stringnullable

**cfi\_attribute1** stringnullable

**cfi\_attribute2** stringnullable

**cfi\_attribute3** stringnullable

**cfi\_attribute4** stringnullable

**cfi\_category\_desc** stringnullable

**cfi\_group\_desc** stringnullable

**cfi\_attribute1\_desc** stringnullable

**cfi\_attribute2\_desc** stringnullable

**cfi\_attribute3\_desc** stringnullable

**cfi\_attribute4\_desc** stringnullable

* ]

```
[  
  {  
    "symbol_id": "string",  
    "exchange_id": "string",  
    "security_category": "string",  
    "name": "string",  
    "date": "string",  
    "asset_class": "string",  
    "cfi_code": "string",  
    "cfi_category": "string",  
    "cfi_group": "string",  
    "cfi_attribute1": "string",  
    "cfi_attribute2": "string",  
    "cfi_attribute3": "string",  
    "cfi_attribute4": "string",  
    "cfi_category_desc": "string",  
    "cfi_group_desc": "string",  
    "cfi_attribute1_desc": "string",  
    "cfi_attribute2_desc": "string",  
    "cfi_attribute3_desc": "string",  
    "cfi_attribute4_desc": "string"  
  }  
]
```

```
[  
  {  
    "symbol_id": "TSLA",  
    "exchange_id": "IEXG",  
    "security_category": "Common Stock",  
    "name": "TESLA INC",  
    "date": "2025-08-12"  
  },  
  {  
    "symbol_id": "NVDA",  
    "exchange_id": "IEXG",  
    "security_category": "Common Stock",  
    "name": "NVIDIA CORP",  
    "date": "2025-08-12"  
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

List of exchanges](/stock-api/rest-api-historical/list-of-exchanges)[Next

List all periods](/stock-api/rest-api-historical/list-all-periods)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.