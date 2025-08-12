WebSocket API V1 | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/websocket/)

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

* Websocket API V1

On this page

WebSocket API V1
================

Market Data - WebSocket API
===========================

WebSocket endpoint provides real-time market data streaming which works in Subscribe-Publish communication model.
After establishing a WebSocket connection with us, you will need to send a Hello message documented below.  
  
If everything is correct, we will provide you with a continuous stream of real-time market data updates.

Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)
* [HTTP/3 + QUIC](https://datatracker.ietf.org/doc/html/rfc9114)
* [WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)

caution

Your WebSocket client implementation must comply with the "v13" version of the protocol documented in the [RFC6455](http://www.ietf.org/rfc/rfc6455.txt), including responding with the "Pong" message each time we will send "Ping" (every minute), failure to respond with the "Pong" from your WebSocket client will cause a connection to be closed.

info

You may also want to use our REST API for a listing of available symbols, exchanges or assets that we support if you wish to receive a filtered stream.

Authentication[​](/market-data/websocket/#authentication "Direct link to Authentication")
-----------------------------------------------------------------------------------------

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](https://docs.coinapi.io/market-data/authentication) of this documentation.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Latest data](/market-data/rest-api/trades/latest-data)[Next

Introduction](/market-data/websocket/)

* [Authentication](/market-data/websocket/#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.