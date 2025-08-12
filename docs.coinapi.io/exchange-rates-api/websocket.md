Realtime WebSocket API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/websocket/)

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

  + [Introduction](/exchange-rates-api/websocket/)
  + [Endpoints](/exchange-rates-api/websocket/endpoints)
  + [General](/exchange-rates-api/websocket/general)
  + [Messages](/exchange-rates-api/websocket/messages)
* [JSON RPC](/exchange-rates-api/jsonrpc-api)
* [How-to guides](/exchange-rates-api/how-to-guides/)

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

Authentication[​](/exchange-rates-api/websocket/#authentication "Direct link to Authentication")
------------------------------------------------------------------------------------------------

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](https://docs.coinapi.io/market-data/authentication) of this documentation.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

List all asset icons](/exchange-rates-api/rest-api-historical/list-all-asset-icons)[Next

Introduction](/exchange-rates-api/websocket/)

* [Authentication](/exchange-rates-api/websocket/#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.