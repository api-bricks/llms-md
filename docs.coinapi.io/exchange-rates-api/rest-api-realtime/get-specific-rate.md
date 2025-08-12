Get specific rate | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/rest-api-realtime/get-specific-rate)

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

  + [Introduction](/exchange-rates-api/rest-api-realtime/exchange-rates-realtime-rest-api)
  + [Exchange Rates](/exchange-rates-api/rest-api-realtime/exchange-rates)

    - [Get specific rate](/exchange-rates-api/rest-api-realtime/get-specific-rate)
    - [Get all current rates](/exchange-rates-api/rest-api-realtime/get-all-current-rates)
  + [Metadata](/exchange-rates-api/rest-api-realtime/metadata)
* [Historical REST API](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)
* [Websocket API](/exchange-rates-api/websocket/)
* [JSON RPC](/exchange-rates-api/jsonrpc-api)
* [How-to guides](/exchange-rates-api/how-to-guides/)

* [Realtime REST API](/exchange-rates-api/rest-api-realtime/exchange-rates-realtime-rest-api)
* [Exchange Rates](/exchange-rates-api/rest-api-realtime/exchange-rates)
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

Request[​](/exchange-rates-api/rest-api-realtime/get-specific-rate#request "Direct link to Request")
----------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id\_base** stringrequired

Requested exchange rate base asset identifier (from the Metadata -> Assets)

**asset\_id\_quote** stringrequired

Requested exchange rate quote asset identifier (from the Metadata -> Assets)

Responses[​](/exchange-rates-api/rest-api-realtime/get-specific-rate#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------

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
  "time": "2025-08-12T06:09:08.580Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:04:53.1923010Z",  
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
  "time": "2025-08-12T06:09:08.580Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:04:53.1923010Z",  
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
  "time": "2025-08-12T06:09:08.581Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:04:53.1923010Z",  
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
  "time": "2025-08-12T06:09:08.581Z",  
  "asset_id_base": "string",  
  "asset_id_quote": "string",  
  "rate": 0  
}
```

```
{  
  "time": "2025-08-12T06:04:53.1923010Z",  
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

Exchange Rates](/exchange-rates-api/rest-api-realtime/exchange-rates)[Next

Get all current rates](/exchange-rates-api/rest-api-realtime/get-all-current-rates)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.