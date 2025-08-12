Endpoints | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/websocket/endpoints)

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
* [Websocket API V1](/market-data/websocket/)

  + [Introduction](/market-data/websocket/)
  + [Endpoints](/market-data/websocket/endpoints)
  + [General](/market-data/websocket/general)
  + [Messages](/market-data/websocket/messages)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [Websocket API V1](/market-data/websocket/)
* Endpoints

Endpoints
=========

| Enviroment | Encryption | Value | Region |
| --- | --- | --- | --- |
| Production | Yes | `wss://ws.coinapi.io/v1/` | GeoDNS (auto-routing) |
| Production | No | `ws://ws.coinapi.io/v1/` | GeoDNS (auto-routing) |
| Production | Yes | `wss://api-ncsa.coinapi.io/v1/` | North & South America |
| Production | No | `ws://api-ncsa.coinapi.io/v1/` | North & South America |
| Production | Yes | `wss://api-emea.coinapi.io/v1/` | Europe, Middle East & Africa |
| Production | No | `ws://api-emea.coinapi.io/v1/` | Europe, Middle East & Africa |
| Production | Yes | `wss://api-apac.coinapi.io/v1/` | Asia Pacific |
| Production | No | `ws://api-apac.coinapi.io/v1/` | Asia Pacific |

info

The default endpoints (`ws.coinapi.io`) use GeoDNS to automatically route your WebSocket connections to the nearest datacenter. If you prefer to use a specific region, you can use the region-specific endpoints listed above.

For testing, debugging and development purposes we are recommending:

* `wscat` client from the `npm` package repository: <https://github.com/websockets/wscat>
* `sandy` standalone WebSocket client with our message templates available at: <https://app.gosandy.io/?url=https://raw.githubusercontent.com/coinapi/coinapi-sdk/master/data-api/sandy-ws-v1.json&u=Ar>

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/market-data/websocket/)[Next

General](/market-data/websocket/general)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.