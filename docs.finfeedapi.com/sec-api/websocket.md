Realtime WebSocket API | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [SEC Filings API](/sec-api/)
* [Authentication](/sec-api/authentication)
* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)
* [Websocket API](/sec-api/websocket/)

  + [Introduction](/sec-api/websocket/)
  + [Endpoints](/sec-api/websocket/endpoints)
  + [General](/sec-api/websocket/general)
  + [Messages](/sec-api/websocket/messages)
* [JSON RPC](/sec-api/jsonrpc-api)

* Websocket API

On this page

Realtime WebSocket API
======================

SEC Filings – WebSocket API
===========================

The WebSocket endpoint provides a real-time stream of SEC filings discovered by our platform. As soon as the connection is open, the server sends a short backlog of the most recent filings and then pushes every new filing with an average latency of **100 ms**.

Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)
* [HTTP/3 + QUIC](https://datatracker.ietf.org/doc/html/rfc9114)
* [WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)

caution

Your WebSocket client implementation must comply with the "v13" version of the protocol documented in the [RFC6455](http://www.ietf.org/rfc/rfc6455.txt), including responding with the **Pong** message each time we send **Ping** (every minute). Failure to respond results in the connection being closed.

Authentication[​](/sec-api/websocket/#authentication "Direct link to Authentication")
-------------------------------------------------------------------------------------

The stream requires the same API key as the rest of the FinFeed SEC API platform. Refer to the [authentication section](/market-data/authentication) for detailed instructions.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Convert XBRL data to JSON format](/sec-api/rest-api/convert-xbrl-data-to-json-format)[Next

Introduction](/sec-api/websocket/)

* [Authentication](/sec-api/websocket/#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.