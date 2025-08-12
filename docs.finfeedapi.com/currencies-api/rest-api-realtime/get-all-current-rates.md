Get all current rates | FinFeedAPI.com Documentation




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
* Get all current rates

Get all current rates
=====================

```
GET

/v1/exchangerate/:asset_id_base
-------------------------------
```

Get the current exchange rate between requested asset and all other assets.

info

If you are using an exchange rate for mission-critical operations, then for best reliability, you should measure the difference between current time and the time returned from the response to ensure that value of the difference between those meets your internal requirements.

info

You can invert the rates by using Y = 1 / X equation, for example BTC/USD = 1 / (USD/BTC);

Request[​](/currencies-api/rest-api-realtime/get-all-current-rates#request "Direct link to Request")
----------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id\_base** stringrequired

Requested exchange rates base asset identifier (from the Metadata -> Assets)



### Query Parameters

**filter\_asset\_id** string

Comma or semicolon delimited asset identifiers used to filter response (optional)

**invert** boolean

True will invert all the rates (optional, if true then rates will be calculated as `rate = 1 / actual_rate` eg. `USD/BTC` as `BTC/USD`)

Responses[​](/currencies-api/rest-api-realtime/get-all-current-rates#responses "Direct link to Responses")
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

**asset\_id\_base** stringnullable

Gets or sets the base asset ID.

**rates**

object[]

nullable

Gets or sets the list of exchange rates.

* Array [

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

* ]

```
{  
  "asset_id_base": "string",  
  "rates": [  
    {  
      "time": "2025-08-12T06:08:07.226Z",  
      "asset_id_quote": "string",  
      "rate": 0  
    }  
  ]  
}
```

```
{  
  "asset_id_base": "BTC",  
  "rates": [  
    {  
      "time": "2017-08-09T14:31:37.0520000Z",  
      "asset_id_quote": "USD",  
      "rate": 3258.887541779804  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "EUR",  
      "rate": 2782.5255080599272  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "CNY",  
      "rate": 21756.295595926054  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "GBP",  
      "rate": 2509.602420379958  
    }  
  ]  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**asset\_id\_base** stringnullable

Gets or sets the base asset ID.

**rates**

object[]

nullable

Gets or sets the list of exchange rates.

* Array [

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

* ]

```
{  
  "asset_id_base": "string",  
  "rates": [  
    {  
      "time": "2025-08-12T06:08:07.227Z",  
      "asset_id_quote": "string",  
      "rate": 0  
    }  
  ]  
}
```

```
{  
  "asset_id_base": "BTC",  
  "rates": [  
    {  
      "time": "2017-08-09T14:31:37.0520000Z",  
      "asset_id_quote": "USD",  
      "rate": 3258.887541779804  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "EUR",  
      "rate": 2782.5255080599272  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "CNY",  
      "rate": 21756.295595926054  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "GBP",  
      "rate": 2509.602420379958  
    }  
  ]  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**asset\_id\_base** stringnullable

Gets or sets the base asset ID.

**rates**

object[]

nullable

Gets or sets the list of exchange rates.

* Array [

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

* ]

```
{  
  "asset_id_base": "string",  
  "rates": [  
    {  
      "time": "2025-08-12T06:08:07.227Z",  
      "asset_id_quote": "string",  
      "rate": 0  
    }  
  ]  
}
```

```
{  
  "asset_id_base": "BTC",  
  "rates": [  
    {  
      "time": "2017-08-09T14:31:37.0520000Z",  
      "asset_id_quote": "USD",  
      "rate": 3258.887541779804  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "EUR",  
      "rate": 2782.5255080599272  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "CNY",  
      "rate": 21756.295595926054  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "GBP",  
      "rate": 2509.602420379958  
    }  
  ]  
}
```

* Schema
* Example (from schema)
* Example response

**Schema**

**asset\_id\_base** stringnullable

Gets or sets the base asset ID.

**rates**

object[]

nullable

Gets or sets the list of exchange rates.

* Array [

**time** date-time

Gets or sets the time of the exchange rate.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset ID of the exchange rate.

**rate** double

Gets or sets the exchange rate value.

* ]

```
{  
  "asset_id_base": "string",  
  "rates": [  
    {  
      "time": "2025-08-12T06:08:07.227Z",  
      "asset_id_quote": "string",  
      "rate": 0  
    }  
  ]  
}
```

```
{  
  "asset_id_base": "BTC",  
  "rates": [  
    {  
      "time": "2017-08-09T14:31:37.0520000Z",  
      "asset_id_quote": "USD",  
      "rate": 3258.887541779804  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "EUR",  
      "rate": 2782.5255080599272  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "CNY",  
      "rate": 21756.295595926054  
    },  
    {  
      "time": "2017-08-09T14:31:36.7570000Z",  
      "asset_id_quote": "GBP",  
      "rate": 2509.602420379958  
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

Get specific rate](/currencies-api/rest-api-realtime/get-specific-rate)[Next

Metadata](/currencies-api/rest-api-realtime/metadata)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.