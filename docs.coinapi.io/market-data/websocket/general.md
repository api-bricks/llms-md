General | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/websocket/general)

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
* General

On this page

General
=======

Hello OUT[​](/market-data/websocket/general#hello-out "Direct link to hello-out")
---------------------------------------------------------------------------------

> Example hello message for trades subscription to all symbols from `COINBASE` and `ITBIT` exchange and additional for 2 selected symbols from `BITSTAMP` and `BITFINEX` exchange:

```
{  
  "type": "hello",  
  "heartbeat": false,  
  "subscribe_data_type": ["trade"],  
  "subscribe_filter_exchange_id": [  
    "COINBASE",  
    "ITBIT"  
  ],  
  "subscribe_filter_symbol_id": [  
    "BITSTAMP_SPOT_BTC_USD$",  
    "BITFINEX_SPOT_BTC_LTC$"  
    ]  
}
```

> Another example of a hello message for subscription to quotes related to the BTC or ETH assets:

```
{  
  "type": "hello",  
  "heartbeat": false,  
  "subscribe_data_type": ["quote"],  
  "subscribe_filter_asset_id": ["BTC", "ETH"]  
}
```

> Another example of a hello message for subscription to quotes related to the BTC/USD asset pair:

```
{  
  "type": "hello",  
  "heartbeat": false,  
  "subscribe_data_type": ["quote"],  
  "subscribe_filter_asset_id": ["BTC/USD"]  
}
```

> Another example of a hello message for subscription of multiple data types from specific exchange:

```
{  
  "type": "hello",  
  "heartbeat": false,  
  "subscribe_data_type": ["trade", "quote", "book20"]  
  "subscribe_filter_exchange_id": [  
    "BITSTAMP"  
  ]  
}
```

Subscribe OUT[​](/market-data/websocket/general#subscribe-out "Direct link to subscribe-out")
---------------------------------------------------------------------------------------------

The WebSocket API has been enhanced to support dynamic subscription management through subscribe and unsubscribe messages. These allow for more granular control over the data streams without the need to resend the entire subscription scope as previously required with the hello message.

To subscribe to additional data types or filters without overriding existing subscriptions, send a `subscribe` message:

> Example `subscribe` message for book data related to "BTC" and "ETH":

```
{  
  "type": "subscribe",  
  "heartbeat": true,  
  "subscribe_data_type": ["book"],  
  "subscribe_filter_asset_id": ["BTC", "ETH"]  
}
```

> This message adds subscriptions to the specified data types and filters, augmenting any existing subscriptions maintained in the session.

Unsubscribe OUT[​](/market-data/websocket/general#unsubscribe-out "Direct link to unsubscribe-out")
---------------------------------------------------------------------------------------------------

Similarly, to remove specific data types or filters from your current subscription, send an unsubscribe message:

> Example unsubscribe message to remove book data subscription for "BTC":

```
{  
  "type": "unsubscribe",  
  "heartbeat": true,  
  "subscribe_data_type": ["book"],  
  "subscribe_filter_asset_id": ["BTC"]  
}
```

> The unsubscribe message removes the specified subscriptions without affecting other existing subscriptions.

Subscribe vs Hello[​](/market-data/websocket/general#subscribe-vs-hello "Direct link to Subscribe vs Hello")
------------------------------------------------------------------------------------------------------------

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

Message parameters[​](/market-data/websocket/general#message-parameters "Direct link to Message parameters")
------------------------------------------------------------------------------------------------------------

| Parameter | Type | Description |
| --- | --- | --- |
| type | string | Message type, must be equal to one of the values: `hello`, `subscribe` or `unsubscribe` |
| heartbeat | bool | `true` to receive Heartbeat message every second, otherwise `false` |
| subscribe\_data\_type | string[] | List of data types you want to receive *(required, possible values listed in table below)* |
| subscribe\_filter\_symbol\_id | string[] | Filter data to symbols whose identifiers match at least one of the listed prefixes. If symbol is ended with `$` character then exact match is used instead of prefix match. *(optional, if not provided then stream will not filtered by symbols)* |
| subscribe\_filter\_asset\_id | string[] | Filter data to messages which are related to the at least one of the listed asset identifiers or to specific asset pair (e.g. BTC/USD) *(optional, if not provided then stream will not be filtered by assets)* |
| subscribe\_filter\_period\_id | string[] | Filter data to specific OHLCV periods *(optional, if not provided then OHLCV stream will not be filtered by periods)* |
| subscribe\_filter\_exchange\_id | string[] | Filter data to symbols from the listed exchange identifiers *(optional, if not provided then stream will not be filtered by exchanges)* |
| subscribe\_update\_limit\_ms\_quote | int | Minimum delay in milliseconds between quote updates for the same symbol *(optional)* |
| subscribe\_update\_limit\_ms\_book\_snapshot | int | Minumum delay in milliseconds between book snapshot *(book5, book20, book50)* updates for the same symbol *(optional)* |
| subscribe\_update\_limit\_ms\_exrate | int | Minumum delay in milliseconds between exchange rate updates for the same asset pair *(optional)* |

Data types[​](/market-data/websocket/general#data-types "Direct link to Data types")
------------------------------------------------------------------------------------

Listed below are all allowed values for `subscribe_data_type` variables from hello message.

| Data type | Description |
| --- | --- |
| `trade` | Executed transactions feed *(order book matches)* |
| `quote` | Quote updates feed *(order book level 1)* |
| `book` | Order book snapshots and updates feed *(order book level 2, full order book snapshot and real-time updates)*. To use this data type you need to define a filter in the hello or subscribe message. |
| `book5` | Order book snapshots feed *(order book level 2, 5 best levels from each side of book)*. To use this data type you need to define a filter in the hello or subscribe message. |
| `book20` | Order book snapshots feed *(order book level 2, 20 best levels from each side of book)*. To use this data type you need to define a filter in the hello or subscribe message. |
| `book50` | Order book snapshots feed *(order book level 2, 50 best levels from each side of book)*. To use this data type you need to define a filter in the hello or subscribe message. |
| `ohlcv` | OHLCV updates per symbol on periods between 1SEC and 1MIN |
| `exrate` | Exchange rate updates (VWAP-24H). To use this data type you need to define subscribe\_filter\_asset\_id in the hello or subscribe message (e.g. BTC/USD) |
| `asset` | Assets feed. |
| `exchange` | Exchanges feed. |
| `symbol` | Symbols feed. |

Error handling[​](/market-data/websocket/general#error-handling "Direct link to Error handling")
------------------------------------------------------------------------------------------------

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

Data buffering[​](/market-data/websocket/general#data-buffering "Direct link to Data buffering")
------------------------------------------------------------------------------------------------

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

Endpoints](/market-data/websocket/endpoints)[Next

Messages](/market-data/websocket/messages)

* [Hello OUT](/market-data/websocket/general#hello-out)
* [Subscribe OUT](/market-data/websocket/general#subscribe-out)
* [Unsubscribe OUT](/market-data/websocket/general#unsubscribe-out)
* [Subscribe vs Hello](/market-data/websocket/general#subscribe-vs-hello)
* [Message parameters](/market-data/websocket/general#message-parameters)
* [Data types](/market-data/websocket/general#data-types)
* [Error handling](/market-data/websocket/general#error-handling)
* [Data buffering](/market-data/websocket/general#data-buffering)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.