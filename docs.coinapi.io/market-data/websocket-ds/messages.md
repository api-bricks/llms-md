Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/websocket-ds/messages)

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
* Messages

On this page

Messages
========

Trades  IN[​](/market-data/websocket-ds/messages#trades--in "Direct link to trades--in")
----------------------------------------------------------------------------------------

> Trade message JSON is structured like this:

```
{  
  "type": "trade",  
  "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
  "sequence": 2323346,  
  "time_exchange": "2013-09-28T22:40:50.0000000Z",  
  "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
  "uuid": "770C7A3B-7258-4441-8182-83740F3E2457",  
  "price": 770.000000000,  
  "size": 0.050000000,  
  "taker_side": "BUY"  
}
```

Trade message is sent for every executed transaction *(orderbook match)*.

### Message variables[​](/market-data/websocket-ds/messages#message-variables "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `trade` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get) |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Time of trade reported by exchange |
| time\_coinapi | Time when coinapi first received trade from exchange |
| uuid | Our unique trade identifier in form of UUIDv4 |
| price | Price of the transaction |
| size | Base asset amount traded in transaction *(if a value is equal to zero, then transaction price just marking a data point eg. in the index time series)* |
| taker\_side | Aggressor side of the transaction *(BUY/SELL/BUY\_ESTIMATED/SELL\_ESTIMATED/UNKNOWN)* |

### Possible `taker_side` values[​](/market-data/websocket-ds/messages#possible-taker_side-values "Direct link to possible-taker_side-values")

If exchange has not reported who the aggressor side of the transaction was, then we will classNameify who it most probably was based on current market view.

| `taker_side` | Description |
| --- | --- |
| `BUY` | Exchange has reported that transaction aggressor was buying |
| `SELL` | Exchange has reported that transaction aggressor was selling |
| `BUY_ESTIMATED` | Exchange has not reported transaction aggressor, we estimated that more likely it was buying |
| `SELL_ESTIMATED` | Exchange has not reported transaction aggressor, we estimated that more likely it was selling |
| `UNKNOWN` | Exchange has not reported transaction aggressor and we have not estimated who it was |

tip

To classNameify who the aggressor of the transaction was, we use a proprietary algorithm that extends the method described in the paper
"Inferring trade direction from intraday data (1991) by Lee and Ready"

Quotes  IN[​](/market-data/websocket-ds/messages#quotes--in "Direct link to quotes--in")
----------------------------------------------------------------------------------------

> Quote message JSON is structured like this:

```
{  
  "type": "quote",  
  "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
  "sequence": 2323346,  
  "time_exchange": "2013-09-28T22:40:50.0000000Z",  
  "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
  "ask_price": 770.000000000,  
  "ask_size": 3252,  
  "bid_price": 760,  
  "bid_size": 124  
}
```

Quote message is sent for each update on orderbook first best bid or ask level.

### Message variables[​](/market-data/websocket-ds/messages#message-variables-1 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `quote` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Exchange time of orderbook |
| time\_coinapi | CoinAPI time when orderbook received from exchange |
| ask\_price | Best asking price |
| ask\_size | Volume resting on best ask *(if a value is equal to zero then size is unknown)* |
| bid\_price | Best bidding price |
| bid\_size | Volume resting on best bid *(if a value is equal to zero then size is unknown)* |

Orderbook L2 (Full)  IN[​](/market-data/websocket-ds/messages#orderbook-l2-full--in "Direct link to orderbook-l2-full--in")
---------------------------------------------------------------------------------------------------------------------------

A Book message is sent for each snapshot or update of the order book.
After subscription to this data type is initialized, we immediately start delivering updates to the order book and at least one snapshot will be provided as soon as possible with the nearest update of the book.
Book message represents total ammount of bids and asks aggregated by price level.

```
{  
  "type": "book",  
  "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
  "sequence": 2323346,  
  "time_exchange": "2013-09-28T22:40:50.0000000Z",  
  "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
  "is_snapshot": true,  
  "asks": [  
    {  
      "price": 456.35,  
      "size": 123  
    },  
    {  
      "price": 456.36,  
      "size": 23  
    },  
    ... cut ...  
  ],  
  "bids": [  
    {  
      "price": 456.10,  
      "size": 42  
    },  
    {  
      "price": 456.09,  
      "size": 5  
    },  
    ... cut ...  
  ]  
}
```

### Message variables[​](/market-data/websocket-ds/messages#message-variables-2 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `book` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Exchange time of orderbook |
| time\_coinapi | CoinAPI time when orderbook received from exchange |
| is\_snapshot | Is message a snapshot? If `true` then all bid and ask levels are listed, otherwise only changed since the last message. |
| asks | All ask levels for snapshot message, otherwise only changed ask levels since the last message. Data will be in order from the best to the worst price. |
| bids | All bid levels for snapshot message, otherwise only changed bid levels since the last message. Data will be in order from the best to the worst price. |
| price | Price of bid/ask |
| size | Volume resting on bid/ask level in base amount |

Orderbook L2 (max 2x5)  IN[​](/market-data/websocket-ds/messages#orderbook-l2-max-2x5---in "Direct link to orderbook-l2-max-2x5---in")
--------------------------------------------------------------------------------------------------------------------------------------

A Book5 message contain first 5 best bid or ask levels.

info

Updates in this data type are sent as soon as possible if orderbook changed (outside or inside levels covered by the snapshot visibility). To reduce amount of updates please use the `subscribe_update_limit_ms_book_snapshot` parameter.

```
{  
  "type": "book5",  
  "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
  "sequence": 2323346,  
  "time_exchange": "2013-09-28T22:40:50.0000000Z",  
  "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
  "asks": [  
    {  
      "price": 456.35,  
      "size": 123  
    },  
    {  
      "price": 456.36,  
      "size": 23  
    },  
    ... cut ...  
  ],  
  "bids": [  
    {  
      "price": 456.10,  
      "size": 42  
    },  
    {  
      "price": 456.09,  
      "size": 5  
    },  
    ... cut ...  
  ]  
}
```

### Message variables[​](/market-data/websocket-ds/messages#message-variables-3 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `book5` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Exchange time of orderbook |
| time\_coinapi | CoinAPI time when orderbook received from exchange |
| asks | Best 5 ask levels in order from best to worst. |
| bids | Best 5 bid levels in order from best to worst. |
| price | Price of bid/ask |
| size | Volume resting on bid/ask level in base amount |

Orderbook L2 (max 2x20)  IN[​](/market-data/websocket-ds/messages#orderbook-l2-max-2x20---in "Direct link to orderbook-l2-max-2x20---in")
-----------------------------------------------------------------------------------------------------------------------------------------

A Book20 message contain first 20 best bid or ask levels.

info

Updates in this data type are sent every 1 second if orderbook changed (outside or inside levels covered by the snapshot visibility). To reduce amount of updates please use the `subscribe_update_limit_ms_book_snapshot` parameter.

```
{  
  "type": "book20",  
  "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
  "sequence": 2323346,  
  "time_exchange": "2013-09-28T22:40:50.0000000Z",  
  "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
  "asks": [  
    {  
      "price": 456.35,  
      "size": 123  
    },  
    {  
      "price": 456.36,  
      "size": 23  
    },  
    ... cut ...  
  ],  
  "bids": [  
    {  
      "price": 456.10,  
      "size": 42  
    },  
    {  
      "price": 456.09,  
      "size": 5  
    },  
    ... cut ...  
  ]  
}
```

### Message variables[​](/market-data/websocket-ds/messages#message-variables-4 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `book20` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Exchange time of orderbook |
| time\_coinapi | CoinAPI time when orderbook received from exchange |
| asks | Best 20 ask levels in order from best to worst. |
| bids | Best 20 bid levels in order from best to worst. |
| price | Price of bid/ask |
| size | Volume resting on bid/ask level in base amount |

Orderbook L2 (max 2x50)  IN[​](/market-data/websocket-ds/messages#orderbook-l2-max-2x50---in "Direct link to orderbook-l2-max-2x50---in")
-----------------------------------------------------------------------------------------------------------------------------------------

A Book50 message contain first 50 best bid or ask levels.

info

Updates in this data type are sent every 1 second if orderbook changed (outside or inside levels covered by the snapshot visibility). To reduce amount of updates please use the `subscribe_update_limit_ms_book_snapshot` parameter.

```
{  
  "type": "book50",  
  "symbol_id": "BITSTAMP_SPOT_BTC_USD",  
  "sequence": 2323346,  
  "time_exchange": "2013-09-28T22:40:50.0000000Z",  
  "time_coinapi": "2017-03-18T22:42:21.3763342Z",  
  "asks": [  
    {  
      "price": 456.35,  
      "size": 123  
    },  
    {  
      "price": 456.36,  
      "size": 23  
    },  
    ... cut ...  
  ],  
  "bids": [  
    {  
      "price": 456.10,  
      "size": 42  
    },  
    {  
      "price": 456.09,  
      "size": 5  
    },  
    ... cut ...  
  ]  
}
```

### Message variables[​](/market-data/websocket-ds/messages#message-variables-5 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `book50` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Exchange time of orderbook |
| time\_coinapi | CoinAPI time when orderbook received from exchange |
| asks | Best 50 ask levels in order from best to worst. |
| bids | Best 50 bid levels in order from best to worst. |
| price | Price of bid/ask |
| size | Volume resting on bid/ask level in base amount |

Orderbook L3 (Full)  IN[​](/market-data/websocket-ds/messages#orderbook-l3-full---in "Direct link to orderbook-l3-full---in")
-----------------------------------------------------------------------------------------------------------------------------

A `book_l3` message is sent for each snapshot or update of the order book in the level 3 format (order-by-order).
After subscription to this data type is initialized, we immediately start delivering updates to the order book and at least one snapshot will be provided as soon as possible with the nearest update of the book.
Book L3 does not aggregate any data. Every ask and bid corresponds to passive order with information on the price and size of that order. The id can identify any order.

info

If the data source is providing the maximum resoluiont of the order book on level 2 then this data type will fallback to the Level 2, in that case the Order ID's will be null or not provided. You should treat Order without Id as Level 2 aggregated entry in the price queue.

```
{  
  "type": "book_l3"  
  "symbol_id": "COINBASE_SPOT_BCH_USD",  
  "sequence": 2323346,  
  "time_exchange": "2020-08-26T12:36:04.3464706Z",  
  "time_coinapi": "2020-08-26T12:36:04.2807750Z",  
  "is_snapshot": false,  
  "asks": [  
	{  
	  "id": "520269d4-c085-47ed-8825-6d787af90800",  
	  "price": 273.01,  
	  "size": 1.81940502,  
	  "update_type":"ADD"  
	},  
	{  
	  "id": "0ac891c7-8360-462c-8d9a-d8b217d3fca2",  
	  "price": 273.02,  
	  "size": 1.0,  
	  "update_type":"DELETE"  
	},  
	... cut ...  
  ],  
  "bids": [  
	{  
	  "id": "6340ec1e-8be8-404e-b9a4-a14120ec179e",  
	  "price": 272.94,  
	  "size": 1.81940502,  
	  "update_type":"UPDATE"  
	},  
	{  
	  "id": "7eaaa899-089f-4308-9fa2-e33737ae36ee",  
	  "price": 272.96,  
	  "size": 1.85989855,  
	  "update_type":"DELETE"  
	},  
	... cut ...  
  ]  
}
```

### Message variables[​](/market-data/websocket-ds/messages#message-variables-6 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `book_l3` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| time\_exchange | Exchange time of orderbook |
| time\_coinapi | CoinAPI time when orderbook received from exchange |
| is\_snapshot | Is message a snapshot? If `true` then all bid and ask levels are listed, otherwise only changed since the last message |
| asks | All ask levels for snapshot message, otherwise only changed ask levels since the last message. Data will be in order from the best to the worst price. |
| bids | All bid levels for snapshot message, otherwise only changed bid levels since the last message. Data will be in order from the best to the worst price. |
| id | Order identifier |
| price | Price of bid/ask |
| size | Bid/ask base asset amount |
| update\_type | Type of update message |

### Possible `update_type` values[​](/market-data/websocket-ds/messages#possible-update_type-values "Direct link to possible-update_type-values")

The snapshot message represents the initial collection of the orders in the order book. Further updates are modifying this collection.
`update_type` determines the type of update for the order.
Please note that the snapshot message has no defined `update_type`.

| `update_type` | Description |
| --- | --- |
| `ADD` | Add order to the price queue. |
| `UPDATE` | Update the order size in the price queue. |
| `SUBTRACT` | Subtract the order size in the price queue. |
| `DELETE` | Delete the order from the price queue. |
| `MATCH` | Subtract the order size in the price queue (same as `SUBTRACT` but caused by the match). |

Reconnect IN[​](/market-data/websocket-ds/messages#reconnect-in "Direct link to reconnect-in")
----------------------------------------------------------------------------------------------

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
  "type": "reconnect"  
  "within_seconds": 10,  
  "before_time": "2020-08-06T19:19:09.7035429Z",  
}
```

### Message variables[​](/market-data/websocket-ds/messages#message-variables-7 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `reconnect` |
| within\_seconds | Seconds within which reconnection should be performed. |
| before\_time | Time before which reconnection should be performed. |

Heartbeat IN[​](/market-data/websocket-ds/messages#heartbeat-in "Direct link to heartbeat-in")
----------------------------------------------------------------------------------------------

> Heartbeat message JSON is structured like this:

```
{  
  "type": "hearbeat"  
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

General](/market-data/websocket-ds/general)[Next

JSON RPC](/market-data/jsonrpc-api)

* [Trades  IN](/market-data/websocket-ds/messages#trades--in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables)
  + [Possible `taker_side` values](/market-data/websocket-ds/messages#possible-taker_side-values)
* [Quotes  IN](/market-data/websocket-ds/messages#quotes--in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-1)
* [Orderbook L2 (Full)  IN](/market-data/websocket-ds/messages#orderbook-l2-full--in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-2)
* [Orderbook L2 (max 2x5)  IN](/market-data/websocket-ds/messages#orderbook-l2-max-2x5---in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-3)
* [Orderbook L2 (max 2x20)  IN](/market-data/websocket-ds/messages#orderbook-l2-max-2x20---in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-4)
* [Orderbook L2 (max 2x50)  IN](/market-data/websocket-ds/messages#orderbook-l2-max-2x50---in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-5)
* [Orderbook L3 (Full)  IN](/market-data/websocket-ds/messages#orderbook-l3-full---in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-6)
  + [Possible `update_type` values](/market-data/websocket-ds/messages#possible-update_type-values)
* [Reconnect IN](/market-data/websocket-ds/messages#reconnect-in)
  + [Message variables](/market-data/websocket-ds/messages#message-variables-7)
* [Heartbeat IN](/market-data/websocket-ds/messages#heartbeat-in)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.