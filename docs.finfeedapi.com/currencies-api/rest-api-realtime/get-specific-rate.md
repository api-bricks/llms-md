Get specific rate | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Currencies API](/currencies-api/)
* [Authentication](/currencies-api/authentication)
* [Metadata Tables](/currencies-api/metadata-tables/introduction)
* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)

  + [Introduction](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
  + [Exchange Rates](/currencies-api/rest-api-realtime/exchange-rates)

    - [Get specific rate](/currencies-api/rest-api-realtime/get-specific-rate)
    - [Get all current rates](/currencies-api/rest-api-realtime/get-all-current-rates)
  + [Metadata](/currencies-api/rest-api-realtime/metadata)
* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
* [Exchange Rates](/currencies-api/rest-api-realtime/exchange-rates)
* Get specific rate

Get specific rate
=================

```
GET

/v1/exchangerate/:asset_id_base/:asset_id_quote
-----------------------------------------------
```

Retrieves the exchange rate for a specific base and quote asset at a given time or the current rate.

info

If you are using an exchange rate for mission-critical operations, then for best reliability, you should measure the difference between current time and the time returned from the response to ensure that value of the difference between those meets your internal requirements.

Request[​](/currencies-api/rest-api-realtime/get-specific-rate#request "Direct link to Request")
------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id\_base** stringrequired

Requested exchange rate base asset identifier (from the Metadata -> Assets)

**asset\_id\_quote** stringrequired

Requested exchange rate quote asset identifier (from the Metadata -> Assets)

Responses[​](/currencies-api/rest-api-realtime/get-specific-rate#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------

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

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_base** stringnullable

Gets or sets the base asset ID of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

```
{  
  "time": "2025-08-12T06:08:07.224Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:06:46.4310520Z",  
  "asset_id_base": "BTC",  
  "asset_id_quote": "USD",  
  "rate": 10000  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_base** stringnullable

Gets or sets the base asset ID of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

```
{  
  "time": "2025-08-12T06:08:07.225Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:06:46.4310520Z",  
  "asset_id_base": "BTC",  
  "asset_id_quote": "USD",  
  "rate": 10000  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_base** stringnullable

Gets or sets the base asset ID of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

```
{  
  "time": "2025-08-12T06:08:07.225Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:06:46.4310520Z",  
  "asset_id_base": "BTC",  
  "asset_id_quote": "USD",  
  "rate": 10000  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_base** stringnullable

Gets or sets the base asset ID of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

```
{  
  "time": "2025-08-12T06:08:07.225Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:06:46.4310520Z",  
  "asset_id_base": "BTC",  
  "asset_id_quote": "USD",  
  "rate": 10000  
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

Exchange Rates](/currencies-api/rest-api-realtime/exchange-rates)[Next

Get all current rates](/currencies-api/rest-api-realtime/get-all-current-rates)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.