JSON RPC | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/jsonrpc-api)

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
* [Historical REST API](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)
* [Websocket API](/exchange-rates-api/websocket/)
* [JSON RPC](/exchange-rates-api/jsonrpc-api)
* [How-to guides](/exchange-rates-api/how-to-guides/)

* JSON RPC

On this page

JSON RPC
========

Exchange Rates - JSON RPC
=========================

### Introduction[​](/exchange-rates-api/jsonrpc-api#introduction "Direct link to Introduction")

Our exchange rates API provides versatile access through `JSON-RPC`, and our REST endpoints are fully compatible with it, offering flexibility for developers.

* By specifying resource paths (such as `/v1/assets` or `/v1/exchangerates/BTC`) in the `method` property of the JSON-RPC, you can access all of our exchange rates resources.
* Additionally, the `params` property allows for the inclusion of query parameters.

### JSON-RPC[​](/exchange-rates-api/jsonrpc-api#json-rpc "Direct link to JSON-RPC")

JSON-RPC is a lightweight remote procedure call protocol encoded in JSON.
It allows for efficient and straightforward communication between a client and a server over various transport protocols.

JSON-RPC is widely used in web services and APIs due to its simplicity and ease of use.

### JSON-RPC 2.0 Standard[​](/exchange-rates-api/jsonrpc-api#json-rpc-20-standard "Direct link to JSON-RPC 2.0 Standard")

Before diving into the details of using JSON-RPC with the Exchange Rates API, it's important to understand the JSON-RPC standard.
You can find detailed information about the JSON-RPC specification on the official [JSON-RPC website](https://www.jsonrpc.org/specification).

### Endpoint[​](/exchange-rates-api/jsonrpc-api#endpoint "Direct link to Endpoint")

To access exchange rates using JSON-RPC, you need to use following URL:

| Enviroment | Encryption | Value |
| --- | --- | --- |
| Production | Yes | `https://api-realtime.exrates.coinapi.io/jsonrpc` |
| Production | Yes | `https://api-historical.exrates.coinapi.io/jsonrpc` |

### Authentication[​](/exchange-rates-api/jsonrpc-api#authentication "Direct link to Authentication")

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](/authentication) of this documentation.

### Request Format[​](/exchange-rates-api/jsonrpc-api#request-format "Direct link to Request Format")

All requests should follow this format:

```
{  
  "jsonrpc": "2.0",  
  "method": "v1/methodName",  
  "params": [...],  
  "id": null  
}
```

### Examples[​](/exchange-rates-api/jsonrpc-api#examples "Direct link to Examples")

Here are a few examples demonstrating how the Exchange Rates API is accessed through JSON-RPC, along with their corresponding responses.

#### Get assets[​](/exchange-rates-api/jsonrpc-api#get-assets "Direct link to Get assets")

**Request**

`https://api-realtime.exrates.coinapi.io/jsonrpc?apikey=YOUR-API-KEY`

```
{  
  "jsonrpc": "2.0",  
  "method": "v1/getAssets",  
  "params": [],  
  "id": null  
}
```

**Response**

```
{  
    "jsonrpc": "2.0",  
    "result": [  
        {  
            "asset_id": "BTC",  
            "name": "Bitcoin",  
            "type_is_crypto": 1,  
            "price_usd": 105214.96709335800000000041745,  
            "id_icon": "4caf2b16-a017-4e26-a348-2cea69c34cba",  
            "chain_addresses":   
        },  
        //other result entries  
    ],  
    "id": "my-tracking-id-001"  
}
```

#### Get BTC historical exchange rates[​](/exchange-rates-api/jsonrpc-api#get-btc-historical-exchange-rates "Direct link to Get BTC historical exchange rates")

**Request**

`https://api-historical.exrates.coinapi.io/jsonrpc/apikey-YOUR-API-KEY`

```
{  
  "jsonrpc": "2.0",  
  "method": "v1/getHistoricalExchangeRates",  
  "params": [  
    {"asset_id_base": "BTC"},  
    {"asset_id_quote": "USD"},  
    {"period_id": "1SEC"},  
    {"time_start": "2025-01-24T00:00:00"},  
    {"time_end": "2025-01-24T01:00:00"}  
  ],  
  "id": null  
}
```

**Response**

```
{  
    "jsonrpc": "2.0",  
    "result": [  
        {  
            "time_period_start": "2025-01-24T00:00:00.0000000Z",  
            "time_period_end": "2025-01-24T00:00:01.0000000Z",  
            "time_open": "2025-01-24T00:00:00.0000000Z",  
            "time_close": "2025-01-24T00:00:00.9000000Z",  
            "rate_open": 103926.242257415,  
            "rate_high": 103927.063940168,  
            "rate_low": 103926.242257415,  
            "rate_close": 103927.063940168  
        },  
        //other result entries  
    ],  
  "id": "my-tracking-id-001"  
}
```

#### Get Current Exchange Rate[​](/exchange-rates-api/jsonrpc-api#get-current-exchange-rate "Direct link to Get Current Exchange Rate")

**Request**

`https://api-realtime.exrates.coinapi.io/jsonrpc/apikey-YOUR-API-KEY`

```
{  
  "jsonrpc": "2.0",  
  "method": "v1/getCurrentExchangeRates",  
  "params": [  
    {"asset_id_base": "BTC"},  
    {"asset_id_quote": "USD"}  
  ],  
  "id": null  
}
```

**Response**

```
{  
        "jsonrpc": "2.0",  
    "result": {  
        "time": "2025-01-30T11:18:06.2000000Z",  
        "asset_id_base": "BTC",  
        "asset_id_quote": "USD",  
        "rate": 105179.172048761  
        },  
        //other result entries  
}
```

### Error Responses[​](/exchange-rates-api/jsonrpc-api#error-responses "Direct link to Error Responses")

* An incorrectly defined request may result in the following error response:

  ```
  {  
      "jsonrpc": "2.0",  
      "id": "my-tracking-id-001"  
      "error": {  
          "code": 400,  
          "message": "Bad request (failed to parse json rpc)"  
      }  
  }
  ```
* If a resource is not found, you can expect the following error response:

  ```
  {  
      "jsonrpc": "2.0",  
      "id": "my-tracking-id-001"  
      "error": {  
          "code": 404,  
          "message": "Resource not found"  
      }  
  }
  ```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Messages](/exchange-rates-api/websocket/messages)[Next

Introduction](/exchange-rates-api/how-to-guides/)

* [Introduction](/exchange-rates-api/jsonrpc-api#introduction)
* [JSON-RPC](/exchange-rates-api/jsonrpc-api#json-rpc)
* [JSON-RPC 2.0 Standard](/exchange-rates-api/jsonrpc-api#json-rpc-20-standard)
* [Endpoint](/exchange-rates-api/jsonrpc-api#endpoint)
* [Authentication](/exchange-rates-api/jsonrpc-api#authentication)
* [Request Format](/exchange-rates-api/jsonrpc-api#request-format)
* [Examples](/exchange-rates-api/jsonrpc-api#examples)
* [Error Responses](/exchange-rates-api/jsonrpc-api#error-responses)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.