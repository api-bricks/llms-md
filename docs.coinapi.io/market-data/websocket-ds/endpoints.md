Endpoints | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/websocket-ds/endpoints)

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
* [Websocket API DS](/market-data/websocket-ds/)

  + [Introduction](/market-data/websocket-ds/)
  + [Endpoints](/market-data/websocket-ds/endpoints)
  + [General](/market-data/websocket-ds/general)
  + [Messages](/market-data/websocket-ds/messages)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [Websocket API DS](/market-data/websocket-ds/)
* Endpoints

Endpoints
=========

| Enviroment | Encryption | Value |
| --- | --- | --- |
| Production | Yes | `wss://lowecase-exchange-name.ws-ds.md.coinapi.io/` (eg. `wss://coinbase.ws-ds.md.coinapi.io/`) |
| Production | Yes | `wss://cross-connect-endpoint/md/ws-ds-lowecase-exchange-name/` (eg. `wss://cross-connect-endpoint/md/ws-ds-coinbase/`) |
| Production | No | `ws://lowecase-exchange-name.ws-ds.md.coinapi.io/` (eg. `ws://coinbase.ws-ds.md.coinapi.io/`) |
| Production | No | `ws://cross-connect-endpoint/md/ws-ds-lowecase-exchange-name/` (eg. `ws://cross-connect-endpoint/md/ws-ds-coinbase/`) |

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

Introduction](/market-data/websocket-ds/)[Next

General](/market-data/websocket-ds/general)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.