General | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/websocket/general)

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

* [Websocket API](/exchange-rates-api/websocket/)
* General

On this page

General
=======

Hello OUT[​](/exchange-rates-api/websocket/general#hello-out "Direct link to hello-out")
----------------------------------------------------------------------------------------

> Another example of a hello message for subscription to exchange rates related to the BTC/USD asset pair:

```
{  
  "type": "hello",  
  "heartbeat": false,  
  "subscribe_filter_asset_id": ["BTC/EUR"]  
}
```

Subscribe OUT[​](/exchange-rates-api/websocket/general#subscribe-out "Direct link to subscribe-out")
----------------------------------------------------------------------------------------------------

The WebSocket API has been enhanced to support dynamic subscription management through subscribe and unsubscribe messages. These allow for more granular control over the data streams without the need to resend the entire subscription scope as previously required with the hello message.

To subscribe to additional data types or filters without overriding existing subscriptions, send a `subscribe` message:

> Example `subscribe` message for book data related to "BTC" and "ETH":

```
{  
  "type": "subscribe",  
  "heartbeat": true,  
  "subscribe_filter_asset_id": ["ETH/CNY"]  
}
```

> This message adds subscriptions to the specified data types and filters, augmenting any existing subscriptions maintained in the session.

Unsubscribe OUT[​](/exchange-rates-api/websocket/general#unsubscribe-out "Direct link to unsubscribe-out")
----------------------------------------------------------------------------------------------------------

Similarly, to remove specific data types or filters from your current subscription, send an unsubscribe message:

> Example unsubscribe message to remove book data subscription for "BTC":

```
{  
  "type": "unsubscribe",  
  "heartbeat": true,  
  "subscribe_filter_asset_id": ["BTC/EUR"]  
}
```

> The unsubscribe message removes the specified subscriptions without affecting other existing subscriptions.

Subscribe vs Hello[​](/exchange-rates-api/websocket/general#subscribe-vs-hello "Direct link to Subscribe vs Hello")
-------------------------------------------------------------------------------------------------------------------

In the realm of subscription management, three key actions allow you to fine-tune your information feed according to evolving requirements:

* Subscribe: This action expands your current subscription scope by adding new elements without discarding any existing ones. It's particularly useful for tailoring your feed as your interests or information needs grow.
* Unsubscribe: Through this option, you can selectively remove specific elements from your current subscription. It's an efficient way to declutter your feed by eliminating content that no longer serves your needs, without affecting the rest of your subscriptions.
* Hello: Use this command to initiate a fresh start. It clears your existing subscription slate and sets up a new scope from scratch. Opt for this when a complete overhaul of your subscriptions is needed, rather than just an adjustment.

---

After your WebSocket connection is established, you must send us a `hello` or `subscribe` message which contains:

* Stream preferences (Heartbeat and subscription details)
* API key for authorization

If your message will be incorrect, we will send you error message and disconnect connection afterwards.

Hello message can be repeated, each one will cause subscription scope override without interruption of your WebSocket connection.

Message parameters[​](/exchange-rates-api/websocket/general#message-parameters "Direct link to Message parameters")
-------------------------------------------------------------------------------------------------------------------

| Parameter | Type | Description |
| --- | --- | --- |
| type | string | Message type, must be equal to one of the values: `hello`, `subscribe` or `unsubscribe` |
| heartbeat | bool | `true` to receive Heartbeat message every second, otherwise `false` |
| subscribe\_filter\_asset\_id | string[] | Filter data to messages which are related to the at least one of the listed asset identifiers or to specific asset pair (e.g. BTC/USD) *(optional, if not provided then stream will not be filtered by assets)* |
| subscribe\_update\_limit\_ms\_exrate | int | Minumum delay in milliseconds between exchange rate updates for the same asset pair *(optional)* |

Error handling[​](/exchange-rates-api/websocket/general#error-handling "Direct link to Error handling")
-------------------------------------------------------------------------------------------------------

> Example JSON error message is structured like this:

```
{  
  "type": "error",  
  "message": "Invalid API key"  
}
```

You need to be prepared to receive an error message from us when you send something wrong;
all errors are permanent and you should expect that the underlying WebSocket connection will be closed by us after sending an error message.

info

Good practice is to store all error messages somewhere for further manual review.

Data buffering[​](/exchange-rates-api/websocket/general#data-buffering "Direct link to Data buffering")
-------------------------------------------------------------------------------------------------------

> Data buffering JSON error message is structured like this:

```
{  
  "type": "error",  
  "message": "Reached maximum allowed buffered messages for this connection."  
}
```

The stream will send the data to the client as fast as possible; this can result in a high volume of data in cases where the subscription scope is broad. If our server cannot write data to the stream because of the TCP backpressure most likely caused by your client is not reading the data fast enough, or there is not enough network bandwidth available, we will buffer the messages to allow your client to catch up. However, when the buffer is full, a disconnect will be initiated from the server-side, and the buffered messages are dropped, and they will not be resent to the client.

One way to identify when your client is falling behind is to compare the CoinAPI time of the messages being received with your current time on the client and track this metric over time. Make sure your clock is synchronized correctly and do not have a drift.

The possible causes of the buffering are limited and are related to:

* Bandwidth bottleneck, eg.
* Internet connection instability
* Not enough bandwidth to receive a full stream.
* Network card or link saturation.
* I am not receiving messages fast enough, eg.
* Lack of the thread separation between the (a) receiving thread or (b) parsing or (c) processing operations.
* No CPU affinity on the receiving thread.
* CPU bottleneck on the receiving thread.
* Infrequent collection of the data from the TCP stack.
* Heap allocation per message and Garbage Collector pressure.

If your client is unable to receive messages fast enough because of the issues listed above, then these things will happen:

1. Your client TCP stack will be full, and TCP window will be closed to inform us that you can't receive more data and we should not send to you
2. Our TCP stack queue will be full because we couldn't send you more data
3. We will internally create a limited queue of the messages to deliver when the channel is available again (this could cause the delay on the real-time data before the gaps will appear)
4. If the queue is full, then we will disconnect you.

To minimize the occurrence of disconnects:

* Make sure that your client is reading the stream fast enough. Typically you should not do any real processing work as you read the stream. Read the stream and hand the activity to another thread/process/data store to do your processing asynchronously.
* Make sure that your data center has inbound bandwidth sufficient to accomodate large sustained data volumes as well as significantly larger spikes (e.g. 10x normal volume).

The current default queue size per connection is `131 072` messages.

For more information please google: `TCP Flow Control`.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Endpoints](/exchange-rates-api/websocket/endpoints)[Next

Messages](/exchange-rates-api/websocket/messages)

* [Hello OUT](/exchange-rates-api/websocket/general#hello-out)
* [Subscribe OUT](/exchange-rates-api/websocket/general#subscribe-out)
* [Unsubscribe OUT](/exchange-rates-api/websocket/general#unsubscribe-out)
* [Subscribe vs Hello](/exchange-rates-api/websocket/general#subscribe-vs-hello)
* [Message parameters](/exchange-rates-api/websocket/general#message-parameters)
* [Error handling](/exchange-rates-api/websocket/general#error-handling)
* [Data buffering](/exchange-rates-api/websocket/general#data-buffering)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.