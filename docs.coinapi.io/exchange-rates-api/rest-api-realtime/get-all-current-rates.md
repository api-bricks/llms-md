Get all current rates | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/rest-api-realtime/get-all-current-rates)

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

Request[​](/exchange-rates-api/rest-api-realtime/get-all-current-rates#request "Direct link to Request")
--------------------------------------------------------------------------------------------------------

### Path Parameters

**asset\_id\_base** stringrequired

Requested exchange rates base asset identifier (from the Metadata -> Assets)



### Query Parameters

**filter\_asset\_id** string

Comma or semicolon delimited asset identifiers used to filter response (optional)

**invert** boolean

True will invert all the rates (optional, if true then rates will be calculated as `rate = 1 / actual_rate` eg. `USD/BTC` as `BTC/USD`)

Responses[​](/exchange-rates-api/rest-api-realtime/get-all-current-rates#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------------------

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
      "time": "2025-08-12T06:09:08.583Z",  
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
      "time": "2025-08-12T06:09:08.583Z",  
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
      "time": "2025-08-12T06:09:08.584Z",  
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
      "time": "2025-08-12T06:09:08.584Z",  
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

Get specific rate](/exchange-rates-api/rest-api-realtime/get-specific-rate)[Next

Metadata](/exchange-rates-api/rest-api-realtime/metadata)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.