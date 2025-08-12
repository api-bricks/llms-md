Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/websocket-api/messages)

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

* [WebSocket Index API](/indexes-api/websocket-api/)
* Messages

On this page

Messages
========

Index  IN[​](/indexes-api/websocket-api/messages#index--in "Direct link to index--in")
--------------------------------------------------------------------------------------

> Index value message JSON is structured like this:

```
{  
  "type": "index",  
  "index_id": "IDX_REFRATE_PRIMKT_BTC_USD",  
  "time_coinapi": "2017-03-18T22:42:21.0000000Z",  
  "value": 1085.72276,  
}
```

Index value message is sent for each update of certain .

### Message variables[​](/indexes-api/websocket-api/messages#message-variables "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `index` |
| index\_id | Index identifier |
| time\_coinapi | CoinAPI time for which value of index was calulated |
| value | Value of index |

Reconnect IN[​](/indexes-api/websocket-api/messages#reconnect-in "Direct link to reconnect-in")
-----------------------------------------------------------------------------------------------

Reconnect message is sent by the server to all connected clients when the server will be restarted or shut down at the defined exact time included in the message content.
After the period specified in message passes, the client must expect that the underlying WebSocket connection will be closed from the server-side.
A new connection will automatically be established to a different server.

The correct way of handling this event depends on the specific requirements of the integration, but we can define standard ways how to handle it:

* Wait for the connection to be closed and reconnect
* Reconnect immediately after receiving the message
* Upon receiving the message, establish a second connection, and subscribe to the same scope of data. When the first connection is disconnected, do not reconnect it and instead transparently switch the data streams between connections. This method requires more implementation as a transparent switch of the data stream must not break the sequence for streams published using the initial snapshot and update messages.

> Example JSON reconnect message is structured like this:

```
{  
  "type": "reconnect",  
  "within_seconds": 10,  
  "before_time": "2020-08-06T19:19:09.7035429Z",  
}
```

### Message variables[​](/indexes-api/websocket-api/messages#message-variables-1 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `reconnect` |
| within\_seconds | Seconds within which reconnection should be performed. |
| before\_time | Time before which reconnection should be performed. |

Heartbeat IN[​](/indexes-api/websocket-api/messages#heartbeat-in "Direct link to heartbeat-in")
-----------------------------------------------------------------------------------------------

> Heartbeat message JSON is structured like this:

```
{  
  "type": "heartbeat"  
}
```

Heartbeat message is sent to you every time there is one second of silence in communication between us, if you agreed on this feature in Hello message.

tip

WebSocket working on TCP protocol which doesn’t have the feature indicating that the connection is broken
without trying exchange data over it.
As you will not be actively sending messages to us,
with Heartbeat you can distinguish a situation where there are no market data updates for you
(Heartbeat is delivered but no market data updates) or connection between us is broken (Heartbeat and market data updates are not delivered).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

General](/indexes-api/websocket-api/general)[Next

Data Inputs and Sources](/indexes-api/data-inputs-and-sources/)

* [Index  IN](/indexes-api/websocket-api/messages#index--in)
  + [Message variables](/indexes-api/websocket-api/messages#message-variables)
* [Reconnect IN](/indexes-api/websocket-api/messages#reconnect-in)
  + [Message variables](/indexes-api/websocket-api/messages#message-variables-1)
* [Heartbeat IN](/indexes-api/websocket-api/messages#heartbeat-in)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.