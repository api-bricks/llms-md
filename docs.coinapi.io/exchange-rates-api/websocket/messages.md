Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/websocket/messages)

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
* Messages

On this page

Messages
========

Exchange Rate  IN[​](/exchange-rates-api/websocket/messages#exchange-rate--in "Direct link to exchange-rate--in")
-----------------------------------------------------------------------------------------------------------------

Exchange rate is defined as (VWAP-24H) last 24 hour (rolling window over time) Volume Weighted Average Price across multiple data sources listed on our platform. We are selecting and managing the data sources that are used in the calculation based on multiple factors to provide data of highest quality.

```
{  
  "type": "exrate",  
  "asset_id_base": "BTC",  
  "asset_id_quote": "USD",  
  "rate_type":"BASE_ALL_CROSSES_TO_REF",  
  "time": "2019-06-11T15:26:00.0000000Z",  
  "rate": 10065.0319541  
}
```

### Rate types[​](/exchange-rates-api/websocket/messages#rate-types "Direct link to Rate types")

Rate can be several types, we explain what this mean in the table below.

| Rate type | Description |
| --- | --- |
| `BASE_QUOTE_ISOLATED` | To produce rate value only assets in the `asset_id_base` or `asset_id_quote` quotes were used across multiple data sources. |
| `BASE_ALL_CROSSES_TO_REF` | To produce the value of the rate all crosses that included `asset_id_base` across data sources were used and the value was quoted in the reference asset `asset_id_quote`. This means for example that `BTC/USD` component of the rate could be composed of the `BTC/ETH * ETH/USDT * USDT/USD` crosses. In this rate type, we want to express the true value of the asset by seeking markets that have volume/activity and not blinding ourselves only to the direct crosses that in the crypto industry will often not represent the majority of the price discovery activity. This is the same type of rate that is available through other of our APIs. |
| `BASE_AND_QUOTE_TO_REF` | This is the same as `BASE_ALL_CROSSES_TO_REF`, but published only if your client subscribed to asset pair like `BTC/EUR` and the quote asset is not reference asset, then the rate is composed like this `BTC/USD * USD/EUR` in this example from the stream of `BASE_ALL_CROSSES_TO_REF` internally every 1 second. |

### Message variables[​](/exchange-rates-api/websocket/messages#message-variables "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `exrate` |
| asset\_id\_base | Base asset identifier. Full list available [here](/market-data/rest-api/metadata/#list-all-assets-get) |
| asset\_id\_quote | Quote asset identifier. Always `USD`. |
| rate\_type | Rate calculation type it could be `BASE_QUOTE_ISOLATED` or `BASE_ALL_CROSSES_TO_REF`. |
| time | Time of the exchange rate |
| rate | Exchange rate between pair of assets. |

info

There is too much assets to deliver all crosses between them (assets\_count^2), because of that if you need rate quoted in asset different than USD then you need to calculate it yourself on the client side eg. "BTC/USD \* 1 / (USDC/USD) = BTC/USD \* USD/USDC = BTC/USDC"

Reconnect IN[​](/exchange-rates-api/websocket/messages#reconnect-in "Direct link to reconnect-in")
--------------------------------------------------------------------------------------------------

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

### Message variables[​](/exchange-rates-api/websocket/messages#message-variables-1 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `reconnect` |
| within\_seconds | Seconds within which reconnection should be performed. |
| before\_time | Time before which reconnection should be performed. |

Heartbeat IN[​](/exchange-rates-api/websocket/messages#heartbeat-in "Direct link to heartbeat-in")
--------------------------------------------------------------------------------------------------

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

General](/exchange-rates-api/websocket/general)[Next

JSON RPC](/exchange-rates-api/jsonrpc-api)

* [Exchange Rate  IN](/exchange-rates-api/websocket/messages#exchange-rate--in)
  + [Rate types](/exchange-rates-api/websocket/messages#rate-types)
  + [Message variables](/exchange-rates-api/websocket/messages#message-variables)
* [Reconnect IN](/exchange-rates-api/websocket/messages#reconnect-in)
  + [Message variables](/exchange-rates-api/websocket/messages#message-variables-1)
* [Heartbeat IN](/exchange-rates-api/websocket/messages#heartbeat-in)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.