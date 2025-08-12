JSON RPC | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Stock Data API](/stock-api/)
* [Authentication](/stock-api/authentication)
* [Metadata Tables](/stock-api/metadata-tables/introduction)
* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
* [JSON RPC](/stock-api/jsonrpc-api)

* JSON RPC

On this page

JSON RPC
========

Stock Data - JSON RPC
=====================

### Introduction[​](/stock-api/jsonrpc-api#introduction "Direct link to Introduction")

Our stock data API provides versatile access through `JSON-RPC`, and our REST endpoints are fully compatible with it, offering flexibility for developers.

* By specifying resource paths (such as `/v1/stocks` or `/v1/prices/AAPL`) in the `method` property of the JSON-RPC, you can access all of our stock data resources.
* Additionally, the `params` property allows for the inclusion of query parameters.

### JSON-RPC[​](/stock-api/jsonrpc-api#json-rpc "Direct link to JSON-RPC")

JSON-RPC is a lightweight remote procedure call protocol encoded in JSON.
It allows for efficient and straightforward communication between a client and a server over various transport protocols.

JSON-RPC is widely used in web services and APIs due to its simplicity and ease of use.

### JSON-RPC 2.0 Standard[​](/stock-api/jsonrpc-api#json-rpc-20-standard "Direct link to JSON-RPC 2.0 Standard")

Before diving into the details of using JSON-RPC with the Stock Data API, it's important to understand the JSON-RPC standard.
You can find detailed information about the JSON-RPC specification on the official [JSON-RPC website](https://www.jsonrpc.org/specification).

### Endpoint[​](/stock-api/jsonrpc-api#endpoint "Direct link to Endpoint")

To access stock data using JSON-RPC, you need to use following URL:

| Enviroment | Encryption | Value |
| --- | --- | --- |
| Production | Yes | `https://api-historical.stock.finfeedapi.com/jsonrpc` |

### Authentication[​](/stock-api/jsonrpc-api#authentication "Direct link to Authentication")

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](/authentication) of this documentation.

### Request Format[​](/stock-api/jsonrpc-api#request-format "Direct link to Request Format")

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

Latest data](/stock-api/rest-api-historical/latest-data)

* [Introduction](/stock-api/jsonrpc-api#introduction)
* [JSON-RPC](/stock-api/jsonrpc-api#json-rpc)
* [JSON-RPC 2.0 Standard](/stock-api/jsonrpc-api#json-rpc-20-standard)
* [Endpoint](/stock-api/jsonrpc-api#endpoint)
* [Authentication](/stock-api/jsonrpc-api#authentication)
* [Request Format](/stock-api/jsonrpc-api#request-format)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.