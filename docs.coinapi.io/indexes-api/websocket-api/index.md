WebSocket Index API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/websocket-api/)

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

* [Indexes API](/indexes-api/)
* [Introduction](/indexes-api/introduction/)

  + [Purpose and Scope](/indexes-api/introduction/purpose-and-scope)
  + [Key Principles](/indexes-api/introduction/key-principles)
  + [Quickstart](/indexes-api/introduction/quickstart)
  + [Governance and Oversight](/indexes-api/introduction/governance-and-oversight)
* [Index offerings](/category/index-offerings)

  + [Principal Market Price](/indexes-api/index-offerings/primkt-index)
  + [Volume Weighted Average Price](/indexes-api/index-offerings/vwap-index)
  + [Volatility Index](/indexes-api/index-offerings/capivix-index)
* [Introduction](/indexes-api/rest-api/coinapi-indexes-rest-api)
* [WebSocket Index API](/indexes-api/websocket-api/)

  + [Endpoints](/indexes-api/websocket-api/endpoints)
  + [General](/indexes-api/websocket-api/general)
  + [Messages](/indexes-api/websocket-api/messages)
* [Data Inputs and Sources](/indexes-api/data-inputs-and-sources/)
* [Index Calculation Methodologies](/category/index-calculation-methodologies)
* [Eligibility Criteria](/category/eligibility-criteria)
* [Index Maintenance](/category/index-maintenance)
* [Index policies](/indexes-api/index-policies/)
* [Governance](/category/governance)
* [Conflict of Interest Policies](/indexes-api/conflict-of-interest-policies)
* [Use of Expert Judgment](/indexes-api/use-of-expert-judgment)
* [Limitations of the Indexes](/indexes-api/limitations-of-the-indexes)
* [Disclaimer](/indexes-api/disclaimer)
* [MCP API](/indexes-api/mcp)

* WebSocket Index API

On this page

WebSocket Index API
===================

Market Data - WebSocket API
===========================

WebSocket endpoint provides real-time index value streaming which works in Subscribe-Publish communication model.
After establishing a WebSocket connection with us, you will need to send a Hello message documented below.  
  
If everything is correct, we will provide you with a continuous stream of real-time market data updates.

Implemented Standards:

* [HTTP/1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP/1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP/2](https://datatracker.ietf.org/doc/html/rfc7540)
* [HTTP/3 + QUIC](https://datatracker.ietf.org/doc/html/rfc9114)
* [WebSocket](https://datatracker.ietf.org/doc/html/rfc6455)

caution

Your WebSocket client implementation must comply with the "v13" version of the protocol documented in the [RFC6455](http://www.ietf.org/rfc/rfc6455.txt), including responding with the "Pong" message each time we will send "Ping" (every minute), failure to respond with the "Pong" from your WebSocket client will cause a connection to be closed.

info

You may also want to use our REST API for a listing of available symbols, exchanges or assets that we support if you wish to receive a filtered stream.

Authentication[​](/indexes-api/websocket-api/#authentication "Direct link to Authentication")
---------------------------------------------------------------------------------------------

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](/authentication) of this documentation.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/indexes-api/rest-api/coinapi-indexes-rest-api)[Next

Endpoints](/indexes-api/websocket-api/endpoints)

* [Authentication](/indexes-api/websocket-api/#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.