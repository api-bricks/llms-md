Realtime WebSocket API | FinFeedAPI.com Documentation




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

  + [Introduction](/currencies-api/websocket/)
  + [Endpoints](/currencies-api/websocket/endpoints)
  + [General](/currencies-api/websocket/general)
  + [Messages](/currencies-api/websocket/messages)
* [JSON RPC](/currencies-api/jsonrpc-api)

* Websocket API

On this page

Realtime WebSocket API
======================

Exchange Rates - WebSocket API
==============================

WebSocket endpoint provides real-time exchange rates streaming which works in Subscribe-Publish communication model.
After establishing a WebSocket connection with us, you will need to send a Hello message documented below.  
  
If everything is correct, we will provide you with a continuous stream of real-time exchange rates updates.

Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)
* [HTTP/3 + QUIC](https://datatracker.ietf.org/doc/html/rfc9114)
* [WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)

caution

Your WebSocket client implementation must comply with the "v13" version of the protocol documented in the [RFC6455](http://www.ietf.org/rfc/rfc6455.txt), including responding with the "Pong" message each time we will send "Ping" (every minute), failure to respond with the "Pong" from your WebSocket client will cause a connection to be closed.

Authentication[​](/currencies-api/websocket/#authentication "Direct link to Authentication")
--------------------------------------------------------------------------------------------

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](https://docs.coinapi.io/market-data/authentication) of this documentation.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

List all asset icons](/currencies-api/rest-api-historical/list-all-asset-icons)[Next

Introduction](/currencies-api/websocket/)

* [Authentication](/currencies-api/websocket/#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.