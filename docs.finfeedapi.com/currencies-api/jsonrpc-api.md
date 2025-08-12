JSON RPC | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Currencies API](/currencies-api/)
* [Authentication](/currencies-api/authentication)
* [Metadata Tables](/currencies-api/metadata-tables/introduction)
* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* JSON RPC

On this page

JSON RPC
========

Exchange Rates - JSON RPC
=========================

### Introduction[​](/currencies-api/jsonrpc-api#introduction "Direct link to Introduction")

Our exchange rates API provides versatile access through `JSON-RPC`, and our REST endpoints are fully compatible with it, offering flexibility for developers.

* By specifying resource paths (such as `/v1/assets` or `/v1/exchangerates/BTC`) in the `method` property of the JSON-RPC, you can access all of our exchange rates resources.
* Additionally, the `params` property allows for the inclusion of query parameters.

### JSON-RPC[​](/currencies-api/jsonrpc-api#json-rpc "Direct link to JSON-RPC")

JSON-RPC is a lightweight remote procedure call protocol encoded in JSON.
It allows for efficient and straightforward communication between a client and a server over various transport protocols.

JSON-RPC is widely used in web services and APIs due to its simplicity and ease of use.

### JSON-RPC 2.0 Standard[​](/currencies-api/jsonrpc-api#json-rpc-20-standard "Direct link to JSON-RPC 2.0 Standard")

Before diving into the details of using JSON-RPC with the Exchange Rates API, it's important to understand the JSON-RPC standard.
You can find detailed information about the JSON-RPC specification on the official [JSON-RPC website](https://www.jsonrpc.org/specification).

### Endpoint[​](/currencies-api/jsonrpc-api#endpoint "Direct link to Endpoint")

To access exchange rates using JSON-RPC, you need to use following URL:

| Enviroment | Encryption | Value |
| --- | --- | --- |
| Production | Yes | `https://api-realtime.fx.finfeedapi.com/jsonrpc` |
| Production | Yes | `https://api-historical.fx.finfeedapi.com/jsonrpc` |

### Authentication[​](/currencies-api/jsonrpc-api#authentication "Direct link to Authentication")

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](/authentication) of this documentation.

### Request Format[​](/currencies-api/jsonrpc-api#request-format "Direct link to Request Format")

All requests should follow this format:

```
{  
  "jsonrpc": "2.0",  
  "method": "v1/methodName",  
  "params": [...],  
  "id": null  
}
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Messages](/currencies-api/websocket/messages)

* [Introduction](/currencies-api/jsonrpc-api#introduction)
* [JSON-RPC](/currencies-api/jsonrpc-api#json-rpc)
* [JSON-RPC 2.0 Standard](/currencies-api/jsonrpc-api#json-rpc-20-standard)
* [Endpoint](/currencies-api/jsonrpc-api#endpoint)
* [Authentication](/currencies-api/jsonrpc-api#authentication)
* [Request Format](/currencies-api/jsonrpc-api#request-format)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.