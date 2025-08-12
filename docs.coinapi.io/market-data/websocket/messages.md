Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/websocket/messages)

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
* Messages

On this page

Messages
========

Trades  IN[​](/market-data/websocket/messages#trades--in "Direct link to trades--in")
-------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables "Direct link to Message variables")

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

### Possible `taker_side` values[​](/market-data/websocket/messages#possible-taker_side-values "Direct link to possible-taker_side-values")

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

Quotes  IN[​](/market-data/websocket/messages#quotes--in "Direct link to quotes--in")
-------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-1 "Direct link to Message variables")

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

Orderbook L2 (Full)  IN[​](/market-data/websocket/messages#orderbook-l2-full--in "Direct link to orderbook-l2-full--in")
------------------------------------------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-2 "Direct link to Message variables")

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

Orderbook L2 (max 2x5)  IN[​](/market-data/websocket/messages#orderbook-l2-max-2x5---in "Direct link to orderbook-l2-max-2x5---in")
-----------------------------------------------------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-3 "Direct link to Message variables")

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

Orderbook L2 (max 2x20)  IN[​](/market-data/websocket/messages#orderbook-l2-max-2x20---in "Direct link to orderbook-l2-max-2x20---in")
--------------------------------------------------------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-4 "Direct link to Message variables")

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

Orderbook L2 (max 2x50)  IN[​](/market-data/websocket/messages#orderbook-l2-max-2x50---in "Direct link to orderbook-l2-max-2x50---in")
--------------------------------------------------------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-5 "Direct link to Message variables")

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

Orderbook L3 (Full)  IN[​](/market-data/websocket/messages#orderbook-l3-full---in "Direct link to orderbook-l3-full---in")
--------------------------------------------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-6 "Direct link to Message variables")

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

### Possible `update_type` values[​](/market-data/websocket/messages#possible-update_type-values "Direct link to possible-update_type-values")

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

OHLCV  IN[​](/market-data/websocket/messages#ohlcv--in "Direct link to ohlcv--in")
----------------------------------------------------------------------------------

A OHLCV message is sent on the between 1SEC and 1DAY. We are sending message when the ohlcv period is closed (we saw timestamp belonging to the new period) or every 5 seconds if ohlcv period was updated but not yet closed.

```
{  
  "type": "ohlcv",  
  "symbol_id": "BITSTAMP_SPOT_XRP_USD",  
  "sequence": 511,  
  "time_period_start": "2019-06-11T15:26:00.0000000Z",  
  "time_period_end": "2019-06-11T15:27:00.0000000Z",  
  "time_open": "2019-06-11T15:26:07.0000000Z",  
  "time_close": "2019-06-11T15:26:36.0000000Z",  
  "price_open": 0.3865,  
  "price_high": 0.38706,  
  "price_low": 0.3865,  
  "price_close": 0.38706,  
  "volume_traded": 1500.31419084,  
  "trades_count": 5  
}
```

### Message variables[​](/market-data/websocket/messages#message-variables-7 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `ohlcv` |
| symbol\_id | Our symbol identifier, format documented [here](/market-data/rest-api/metadata/#list-all-symbols-get). |
| sequence | Sequence number per pair (`type`, `symbol_id`) which is valid only for the lifespan of the connection. |
| period\_id | Identifier of timeseries period [full list here](/market-data/rest-api/ohlcv/#list-all-periods-get) |
| time\_period\_start | Period starting time *(range left inclusive)* |
| time\_period\_end | Period ending time *(range right exclusive)* |
| time\_open | Time of first trade inside period range |
| time\_close | Time of last trade inside period range |
| price\_open | First trade price inside period range |
| price\_high | Highest traded price inside period range |
| price\_low | Lowest traded price inside period range |
| price\_close | Last trade price inside period range |
| volume\_traded | Cumulative base amount traded inside period range |
| trades\_count | Amount of trades executed inside period range |

Asset  IN[​](/market-data/websocket/messages#asset---in "Direct link to asset---in")
------------------------------------------------------------------------------------

A asset message is sent periodically to update last volume and other information. Feed is useful to keep track of the current assets metadata.
Subscription to this message type triggers delivery of the snapshot.

```
{  
   "type":"asset",  
   "asset_id":"FAKT",  
   "name":"FAKT",  
   "type_is_crypto":1,  
   "data_quote_start":"2022-06-06T13:40:56.7147296Z",  
   "data_quote_end":"2022-11-09T00:00:00.0000000Z",  
   "data_orderbook_start":"2022-06-23T00:00:00.0000000Z",  
   "data_orderbook_end":"2022-11-09T00:00:00.0000000Z",  
   "data_trade_start":"2022-06-06T13:33:33.0000000Z",  
   "data_trade_end":"2022-11-09T00:00:00.0000000Z",  
   "data_symbols_count":6,  
   "volume_1hrs_usd":577.30,  
   "volume_1day_usd":23801.27,  
   "volume_1mth_usd":559053.26,  
   "price_usd":0.0189885151556305438646080756,  
}
```

### Message variables[​](/market-data/websocket/messages#message-variables-8 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `asset` |
| asset\_id | Identifier of asset *(full list available [here](/market-data/rest-api/metadata/#list-all-assets-get))* |
| ... | For other fields please reffer to the asset model documented [here](/market-data/rest-api/metadata/#list-all-assets-get) |

Exchange  IN[​](/market-data/websocket/messages#exchange---in "Direct link to exchange---in")
---------------------------------------------------------------------------------------------

A exchange message is sent periodically to update last volume and other information. Feed is useful to keep track of the current exchanges metadata.
Subscription to this message type triggers delivery of the snapshot.

```
{  
   "type":"exchange",  
   "exchange_id":"BITMEX",  
   "website":"https://www.bitmex.com/",  
   "name":"BitMEX",  
   "data_start":"2014-11-22",  
   "data_end":"2022-11-09",  
   "data_quote_start":"2014-11-22T16:58:47.8820780Z",  
   "data_quote_end":"2022-11-09T00:00:00.0000000Z",  
   "data_orderbook_start":"2014-11-22T16:58:47.8820780Z",  
   "data_orderbook_end":"2022-11-09T00:00:00.0000000Z",  
   "data_trade_start":"2014-11-22T17:51:38.9484710Z",  
   "data_trade_end":"2022-11-09T00:00:00.0000000Z",  
   "data_symbols_count":411  
}
```

### Message variables[​](/market-data/websocket/messages#message-variables-9 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `exchange` |
| exchange\_id | Identifier of exchange *(full list available [here](/market-data/rest-api/metadata/#list-all-exchanges-get))* |
| ... | For other fields please reffer to the exchange model documented [here](/market-data/rest-api/metadata/#list-all-exchanges-get) |

Symbol  IN[​](/market-data/websocket/messages#symbol---in "Direct link to symbol---in")
---------------------------------------------------------------------------------------

A symbol message is sent periodically to update last volume and other information. Feed is useful to keep track of the current symbols metadata.
Subscription to this message type triggers delivery of the snapshot.

```
{  
   "type": "symbol",  
   "symbol_id": "KRAKENFTS_PERP_BTC_USD",  
   "exchange_id": "KRAKENFTS",  
   "symbol_type": "PERPETUAL",  
   "asset_id_base": "BTC",  
   "asset_id_quote": "USD",  
   "asset_id_unit": "USD",  
   "future_contract_unit": 1.000000000,  
   "future_contract_unit_asset": "USD",  
   "data_start": "2019-10-30",  
   "data_end": "2021-03-03",  
   "data_quote_start": "2019-10-30T16:53:10.3262317Z",  
   "data_quote_end": "2021-03-03T13:51:45.6970000Z",  
   "data_orderbook_start": "2019-10-30T16:53:10.3262317Z",  
   "data_orderbook_end": "2020-08-05T14:37:32.0080000Z",  
   "data_trade_start": "2019-10-30T16:38:52.1620000Z",  
   "data_trade_end": "2021-03-03T13:46:25.7810000Z",  
   "volume_1hrs": 22897091.000000000,  
   "volume_1hrs_usd": 22897091.00,  
   "volume_1day": 459390289.000000000,  
   "volume_1day_usd": 459390289.00,  
   "volume_1mth": 12875674995.000000000,  
   "volume_1mth_usd": 12875674995.00,  
   "price": 51266,  
   "symbol_id_exchange": "pi_xbtusd",  
   "asset_id_base_exchange": "XBT",  
   "asset_id_quote_exchange": "USD",  
   "price_precision": 0.100000000,  
   "size_precision": 1.000000000  
}
```

### Message variables[​](/market-data/websocket/messages#message-variables-10 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `symbol` |
| symbol\_id | Identifier of symbol *(full list available [here](/market-data/rest-api/metadata/#list-all-symbols-get))* |
| ... | For other fields please reffer to the symbol model documented [here](/market-data/rest-api/metadata/#list-all-symbols-get) |

Exchange Rate  IN[​](/market-data/websocket/messages#exchange-rate--in "Direct link to exchange-rate--in")
----------------------------------------------------------------------------------------------------------

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

### Rate types[​](/market-data/websocket/messages#rate-types "Direct link to Rate types")

Rate can be several types, we explain what this mean in the table below.

| Rate type | Description |
| --- | --- |
| `BASE_QUOTE_ISOLATED` | To produce rate value only assets in the `asset_id_base` or `asset_id_quote` quotes were used across multiple data sources. |
| `BASE_ALL_CROSSES_TO_REF` | To produce the value of the rate all crosses that included `asset_id_base` across data sources were used and the value was quoted in the reference asset `asset_id_quote`. This means for example that `BTC/USD` component of the rate could be composed of the `BTC/ETH * ETH/USDT * USDT/USD` crosses. In this rate type, we want to express the true value of the asset by seeking markets that have volume/activity and not blinding ourselves only to the direct crosses that in the crypto industry will often not represent the majority of the price discovery activity. This is the same type of rate that is available through other of our APIs. |
| `BASE_AND_QUOTE_TO_REF` | This is the same as `BASE_ALL_CROSSES_TO_REF`, but published only if your client subscribed to asset pair like `BTC/EUR` and the quote asset is not reference asset, then the rate is composed like this `BTC/USD * USD/EUR` in this example from the stream of `BASE_ALL_CROSSES_TO_REF` internally every 1 second. |

### Message variables[​](/market-data/websocket/messages#message-variables-11 "Direct link to Message variables")

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

Reconnect IN[​](/market-data/websocket/messages#reconnect-in "Direct link to reconnect-in")
-------------------------------------------------------------------------------------------

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

### Message variables[​](/market-data/websocket/messages#message-variables-12 "Direct link to Message variables")

| Variable | Description |
| --- | --- |
| type | Message type, always `reconnect` |
| within\_seconds | Seconds within which reconnection should be performed. |
| before\_time | Time before which reconnection should be performed. |

Heartbeat IN[​](/market-data/websocket/messages#heartbeat-in "Direct link to heartbeat-in")
-------------------------------------------------------------------------------------------

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

General](/market-data/websocket/general)[Next

Introduction](/market-data/websocket-ds/)

* [Trades  IN](/market-data/websocket/messages#trades--in)
  + [Message variables](/market-data/websocket/messages#message-variables)
  + [Possible `taker_side` values](/market-data/websocket/messages#possible-taker_side-values)
* [Quotes  IN](/market-data/websocket/messages#quotes--in)
  + [Message variables](/market-data/websocket/messages#message-variables-1)
* [Orderbook L2 (Full)  IN](/market-data/websocket/messages#orderbook-l2-full--in)
  + [Message variables](/market-data/websocket/messages#message-variables-2)
* [Orderbook L2 (max 2x5)  IN](/market-data/websocket/messages#orderbook-l2-max-2x5---in)
  + [Message variables](/market-data/websocket/messages#message-variables-3)
* [Orderbook L2 (max 2x20)  IN](/market-data/websocket/messages#orderbook-l2-max-2x20---in)
  + [Message variables](/market-data/websocket/messages#message-variables-4)
* [Orderbook L2 (max 2x50)  IN](/market-data/websocket/messages#orderbook-l2-max-2x50---in)
  + [Message variables](/market-data/websocket/messages#message-variables-5)
* [Orderbook L3 (Full)  IN](/market-data/websocket/messages#orderbook-l3-full---in)
  + [Message variables](/market-data/websocket/messages#message-variables-6)
  + [Possible `update_type` values](/market-data/websocket/messages#possible-update_type-values)
* [OHLCV  IN](/market-data/websocket/messages#ohlcv--in)
  + [Message variables](/market-data/websocket/messages#message-variables-7)
* [Asset  IN](/market-data/websocket/messages#asset---in)
  + [Message variables](/market-data/websocket/messages#message-variables-8)
* [Exchange  IN](/market-data/websocket/messages#exchange---in)
  + [Message variables](/market-data/websocket/messages#message-variables-9)
* [Symbol  IN](/market-data/websocket/messages#symbol---in)
  + [Message variables](/market-data/websocket/messages#message-variables-10)
* [Exchange Rate  IN](/market-data/websocket/messages#exchange-rate--in)
  + [Rate types](/market-data/websocket/messages#rate-types)
  + [Message variables](/market-data/websocket/messages#message-variables-11)
* [Reconnect IN](/market-data/websocket/messages#reconnect-in)
  + [Message variables](/market-data/websocket/messages#message-variables-12)
* [Heartbeat IN](/market-data/websocket/messages#heartbeat-in)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.