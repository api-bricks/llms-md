General | FinFeedAPI.com Documentation




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

* [Websocket API](/sec-api/websocket/)
* General

On this page

General
=======

Connection flow[​](/sec-api/websocket/general#connection-flow "Direct link to Connection flow")
-----------------------------------------------------------------------------------------------

1. Establish a WebSocket connection to `wss://api.sec.finfeedapi.com`.
2. (Optional) Send a **Hello** message to enable Heartbeat messages (see below).
3. The server delivers a short backlog of recently discovered SEC filings first (`is_historical = true`).
4. As soon as the backlog is complete, every new filing is pushed to you in real-time with ≈ 100 ms latency (`is_historical = false`).
5. The connection remains open until it is closed by the client or a **Reconnect** instruction is received from the server.

---

Hello OUT[​](/sec-api/websocket/general#hello-out "Direct link to hello-out")
-----------------------------------------------------------------------------

Sending the Hello message is **optional**. It is required only when you want to receive periodic Heartbeat messages.

```
{  
  "type": "hello",  
  "heartbeat": true  
}
```

### Message parameters[​](/sec-api/websocket/general#message-parameters "Direct link to Message parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| `type` | string | Must be equal to `hello`. |
| `heartbeat` | bool | When `true`, the server will emit a `heartbeat` message every second whenever no other messages are produced. Defaults to `false`. |

---

Error handling[​](/sec-api/websocket/general#error-handling "Direct link to Error handling")
--------------------------------------------------------------------------------------------

If the server detects an invalid message, it responds with a JSON object of type `error` and immediately closes the connection.

```
{  
  "type": "error",  
  "message": "Invalid API key"  
}
```

Always log error messages for later inspection and re-establish the connection once the problem has been fixed.

---

Data buffering and flow control[​](/sec-api/websocket/general#data-buffering-and-flow-control "Direct link to Data buffering and flow control")
-----------------------------------------------------------------------------------------------------------------------------------------------

The server streams data as fast as your network connection permits. If the client cannot read messages quickly enough, TCP back-pressure will cause the server to build an internal buffer. When that buffer becomes full the server closes the connection using an `error` message similar to the one below:

```
{  
  "type": "error",  
  "message": "Reached maximum allowed buffered messages for this connection."  
}
```

To avoid disconnects:

* Make sure your receiving thread reads from the socket without doing any heavy processing.
* Off-load parsing and business logic to another thread or process.
* Monitor the delay between the `discovered_time` in the messages and your local clock – a growing gap indicates the client is falling behind.

The default per-connection buffer size is **131 072 messages**.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Endpoints](/sec-api/websocket/endpoints)[Next

Messages](/sec-api/websocket/messages)

* [Connection flow](/sec-api/websocket/general#connection-flow)
* [Hello OUT](/sec-api/websocket/general#hello-out)
  + [Message parameters](/sec-api/websocket/general#message-parameters)
* [Error handling](/sec-api/websocket/general#error-handling)
* [Data buffering and flow control](/sec-api/websocket/general#data-buffering-and-flow-control)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.