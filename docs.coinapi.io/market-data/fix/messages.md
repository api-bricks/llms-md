Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/fix/messages)

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
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)

  + [FIX API](/market-data/fix/)
  + [Messages](/market-data/fix/messages)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [FIX API](/market-data/fix/)
* Messages

On this page

Messages
========

All FIX messages are equipped with Standard Header and Trailer, below we will describe what is required in them in accordance with FIX 4.4, the standard that we use.

Standard Header[​](/market-data/fix/messages#standard-header "Direct link to Standard Header")
----------------------------------------------------------------------------------------------

| Tag | Name | Description |
| --- | --- | --- |
| 8 | BeginString | `FIX.4.4` |
| 9 | BodyLength | Message length, in bytes, forward to the CheckSum `<10>` field |
| 35 | MsgType | Defines message type |
| 49 | SenderCompID | Assigned value used to identify message sender |
| 56 | TargetCompID | Assigned value used to identify message receiver |
| 34 | MsgSeqNum | Integer message sequence number. Reset on Logon, Logout and Disconnect. |
| 52 | SendingTime | Time of message transmission always expressed in UTC (Universal Time Coordinated, also known as "GMT") |

Standard Trailer[​](/market-data/fix/messages#standard-trailer "Direct link to Standard Trailer")
-------------------------------------------------------------------------------------------------

| Tag | Name | Description |
| --- | --- | --- |
| 10 | CheckSum | Three byte, simple checksum. Always the last field in a message, i.e. serves, with the trailing, as the end-of-message delimiter. Always defined as three characters |

Logon 35=A[​](/market-data/fix/messages#logon-35a "Direct link to logon-35a")
-----------------------------------------------------------------------------

```
8=FIX.4.4|9=97|35=A|34=1|49=COINAPI|52=20170503-22:00:56.743|56=73034021-THIS-IS-SAMPLE-KEY|98=0|108=1|10=245|
```

First message sent by the client to CoinAPI FIX Gateway after connection to initiate a FIX session.
After successful authorization, server will respond with same message type and start delivering market data messages to you.

| Tag | Name | Description |
| --- | --- | --- |
| 49 | SenderCompID | Your API key |
| 56 | TargetCompID | `COINAPI_V2` |
| 108 | HeartBtInt | `1` *(seconds)* |
| 98 | EncryptMethod | `0` |

Logout 35x5[​](/market-data/fix/messages#logout-35x5 "Direct link to logout-35x5")
----------------------------------------------------------------------------------

Message sent by any side to close established session.
If received, should be sent back unchanged to confirm session termination.

Security List Request  35=x[​](/market-data/fix/messages#security-list-request--35x "Direct link to security-list-request--35x")
--------------------------------------------------------------------------------------------------------------------------------

Security List Request message is used to request full symbol list or narrowed to specific criteria.

Message to request all symbols:

| Tag | Name | Description |
| --- | --- | --- |
| 320 | SecurityReqID | Unique ID of your request, used to link Security List (y) message to the request. |
| 559 | SecurityListRequestType | `4` = Request all symbols. |

Message to request all symbols where our symbol identifier starts with specific string eg. all securities from BITSTAMP exchange to USD.

| Tag | Name | Description |
| --- | --- | --- |
| 320 | SecurityReqID | Unique ID of your request, used to link Security List (y) message to the request. |
| 559 | SecurityListRequestType | `0` = Filter symbols by Symbol (55) or SecurityExchange (207) fields. |
| 55 | Symbol | Exact match or regex for the symbol identifier filtering, eg. `^BITSTAMP_(.*)_USD$` or `BITSTAMP_SPOT_BTC_USD`, have in mind that regex is enabled only if value string starts with `^` or/and ends with `$`. |

Message to request all symbols from specific exchange eg. GEMINI.

| Tag | Name | Description |
| --- | --- | --- |
| 320 | SecurityReqID | Unique ID of your request, used to link Security List (y) message to the request. |
| 559 | SecurityListRequestType | `0` = Filter symbols by Symbol (55) or SecurityExchange (207) fields. |
| 207 | SecurityExchange | Exchange identifier used to filter the symbols |

Security List  35=y[​](/market-data/fix/messages#security-list--35y "Direct link to security-list--35y")
--------------------------------------------------------------------------------------------------------

Response to the Security List Request (x) message.

| Tag | Name | Description |
| --- | --- | --- |
| 320 | SecurityReqID | SecurityReqID (320) from Security List Request (x) message. |
| 322 | SecurityResponseID | Unique ID of the response message. |
| 560 | SecurityRequestResult | Result of the Security List Request.   Valid values:  * `0` = Valid request. * `1` = Response is empty. We couldn't find any symbols matching selection criteria. * `4` = Data temportantly unavailable. Reserved for unlikely event of issue beyond the client control. |
| 393 | TotNoRelatedSym | Total number of symbols in the response. |
| 898 | LastFragment | Indicates if this is a last message |
| 146 | NoRelatedSym | Specifies the number of repeating symbols (instruments) specified. |
| => 55 | Symbol | Our Symbol identifier *(full list available [here](/market-data/rest-api/metadata/#list-all-symbols-get))* |
| => 207 | SecurityExchange | Our exchange identifier, eg. `BITSTAMP`. *(full list available [here](/market-data/rest-api/metadata/#list-all-exchanges-get))* |

Market Data Request  35=V[​](/market-data/fix/messages#market-data-request--35v "Direct link to market-data-request--35v")
--------------------------------------------------------------------------------------------------------------------------

Market Data Request (V) message is used to request market data.

| Tag | Name | Description |
| --- | --- | --- |
| 262 | MDReqId | Must be unique, or the ID of previous Market Data Request (V) to disable if SubscriptionRequestType (263) = Disable previous Snapshot + Updates Request. |
| 263 | SubscriptionRequestType | SubcriptionRequestType indicates what type of response is expected. A snapshot request only asks for current information. A subscribe request asks for updates as the status changes. Unsubscribe will cancel any future update messages.   Valid values:  * `0` = Snapshot. We will deliver only one order book snapshot per symbol requested. * `1` = Snapshot + Updates (Subscribe). We will deliver the initial snapshot per order book requested and then updates for the order book and trades. * `2` = Disable previous Snapshot + Update Request (Unsubscribe). |
| 264 | MarketDepth | Depth of market for Book Snapshot, value ignored for trades.   Valid values:  * `0` = Full book * `1` = Quotes * Other value indicating snapshot limited to provided number of best levels. Use the `0` for the trades as value is required. |
| 265 | MDUpdateType | Required if SubscriptionRequestType (263) = Snapshot + Updates (1) and apply only for the orderbook data.  Valid values:  * `0` = Full refresh (Instead of the updates for the order book, each time the snapshot will be delivered. MDMarketDepth need to be in range of `<1;20>`) * `1` = Incremental Refresh (MDMarketDepth must be `0` as incremential refresh is possible only for the full order book, for other use-cases you should set MDUpdateType to `0` (Full Refresh)) |
| 267 | NoMDEntryTypes | Number of MDEntryType (269) fields requested. |
| => 269 | MDEntryType | This is a list of all the types of Market Data Type requested.   Valid values:  * `0` = Orderbook bids * `1` = Orderbook asks * `2` = Trades  Only possible combinations here are `012 (Orderbook and Trades), 01 (Orderbook) and 2 (Trades)`, the client is not allowed to ask only for the one-side of the book. |
| 146 | NoRelatedSym | Number of symbols (instruments) requested. |
| => 55 | Symbol | Exact match or regex for the symbol identifier filtering, eg. `^BITSTAMP_(.*)_USD$` or `BITSTAMP_SPOT_BTC_USD`, have in mind that regex is enabled only if value string starts with `^` or/and ends with `$`. |

Market Data Request Reject  35=Y[​](/market-data/fix/messages#market-data-request-reject--35y "Direct link to market-data-request-reject--35y")
-----------------------------------------------------------------------------------------------------------------------------------------------

Market Data Request Reject (Y) message is used to reject the request for the market data.

| Tag | Name | Description |
| --- | --- | --- |
| 262 | MDReqId | MDReqId (262) from Market Data Request (V) message. |
| 281 | MDReqRejReason | Reason for the rejection of a Market Data request.   Valid values:  * `0` = Unknown symbol. * `4` = Unsupported SubscriptionRequestType (263) * `5` = Unsupported MarketDepth (264) * `8` = Unsupported MDEntryType (269) |
| 58 | Text | Error message |

Market Data Incremental  35=X[​](/market-data/fix/messages#market-data-incremental--35x "Direct link to market-data-incremental--35x")
--------------------------------------------------------------------------------------------------------------------------------------

Market Data - Incremental Refresh (X) message, representing new executed transaction or orderbook update.

| Tag | Name | Description |
| --- | --- | --- |
| 262 | MDReqId | MDReqId (262) from Market Data Request (V) message. Used to link request to the Market Data, eg. with your internal identifier. |
| 268 | NoMdEntries | Number of trades in the message |
| => 279 | MDUpdateAction | Type of Market Data update action.   Valid values:  * `0` = New. Used for the trades. * `1` = Change. Used for all changes of the order book. |
| => 269 | MDEntryType | Type of Market Data entry.   Valid values:  * `0` = Bids * `1` = Ask/Offer * `2` = Trades |
| => 278 | MDEntryID | Our unique trade identifier in the form of UUIDv4 |
| => 55 | Symbol | Our Symbol identifier *(full list available [here](/market-data/rest-api/metadata/#list-all-symbols-get))* |
| => 270 | MDEntryPx | Entry price |
| => 271 | MDEntrySize | Entry size in base amount |
| => 272 | MDEntryDate | Date of the entry reported by the exchange |
| => 273 | MDEntryTime | Time of the entry reported by the exchange with milliseconds |
| => 282 | MDEntryOriginator | Used only when MDEntryType (269) is Trade. Aggressor side of the transaction. *(BUY/SELL/BUY\_ESTIMATED/SELL\_ESTIMATED/UNKNOWN)* |

### Possible `MDEntryOriginator` values[​](/market-data/fix/messages#possible-mdentryoriginator-values "Direct link to possible-mdentryoriginator-values")

If exchange has not reported who the aggressor side of the transaction was, we will classNameify who it most probably was based on current market view.

| `taker_side` | Description |
| --- | --- |
| `BUY` | Exchange has reported that transaction aggressor was buying |
| `SELL` | Exchange has reported that transaction aggressor was selling |
| `BUY_ESTIMATED` | Exchange has not reported transaction aggressor, we estimated that more likely it was buying |
| `SELL_ESTIMATED` | Exchange has not reported transaction aggressor, we estimated that more likely it was selling |
| `UNKNOWN` | Exchange has not reported transaction aggressor and we have not estimated who it was |

tip

To classNameify who the aggressor of the transaction was, we using a proprietary algorithm that extends the method described in the paper "Inferring trade direction from intraday data (1991) by Lee and Ready"

Market Data Snapshot  35=W[​](/market-data/fix/messages#market-data-snapshot--35w "Direct link to market-data-snapshot--35w")
-----------------------------------------------------------------------------------------------------------------------------

Market Data - Snapshot/Full Refresh (W) message, representing orderbook snapshot.

```
8=FIX.4.4|9=2814|35=W|34=7|49=COINAPI|52=20170503-22:35:18.590|56=73034021-THIS-IS-SAMPLE-KEY|55=COINBASE_SPOT_BTC_EUR|268=40|269=1|270=1397.84000000|271=0.25620000|272=20170503|273=22:35:18.408|269=1|270=1397.85000000|271=0.24000000|272=20170503|273=22:35:18.408|269=1|270=1397.86000000|271=0.50000000|272=20170503|273=22:35:18.408|269=1|270=1399.96000000|271=0.08000000|272=20170503|273=22:35:18.408|269=1|270=1399.98000000|271=0.11000000|272=20170503|273=22:35:18.408|269=1|270=1399.99000000|271=0.93340628|272=20170503|273=22:35:18.408|269=1|270=1400.0|271=4.37155883|272=20170503|273=22:35:18.408|269=1|270=1401.22000000|271=0.11000000|272=20170503|273=22:35:18.408|269=1|270=1401.23|271=0.01|272=20170503|273=22:35:18.408|269=1|270=1402.12|271=0.10000000|272=20170503|273=22:35:18.408|269=1|270=1402.60000000|271=5.30086000|272=20170503|273=22:35:18.408|269=1|270=1402.68000000|271=0.11000000|272=20170503|273=22:35:18.408|269=1|270=1402.69|271=0.02000000|272=20170503|273=22:35:18.408|269=1|270=1404.0|271=1.0|272=20170503|273=22:35:18.408|269=1|270=1404.01000000|271=0.47000000|272=20170503|273=22:35:18.408|269=1|270=1405.0|271=0.24577401|272=20170503|273=22:35:18.408|269=1|270=1405.07|271=0.01264284|272=20170503|273=22:35:18.408|269=1|270=1405.11|271=0.01943044|272=20170503|273=22:35:18.408|269=1|270=1405.61000000|271=1.68316924|272=20170503|273=22:35:18.408|269=1|270=1405.67000000|271=4.13101588|272=20170503|273=22:35:18.408|269=0|270=1396.00000000|271=0.73076211|272=20170503|273=22:35:18.408|269=0|270=1395.82000000|271=0.31000000|272=20170503|273=22:35:18.408|269=0|270=1395.81000000|271=4.07759372|272=20170503|273=22:35:18.408|269=0|270=1395.47000000|271=0.40000000|272=20170503|273=22:35:18.408|269=0|270=1395.01000000|271=0.56000000|272=20170503|273=22:35:18.408|269=0|270=1395.00000000|271=0.05000000|272=20170503|273=22:35:18.408|269=0|270=1394.34000000|271=0.50000000|272=20170503|273=22:35:18.408|269=0|270=1393.79000000|271=0.02000000|272=20170503|273=22:35:18.408|269=0|270=1393.78000000|271=0.10000000|272=20170503|273=22:35:18.408|269=0|270=1393.50000000|271=0.10000000|272=20170503|273=22:35:18.408|269=0|270=1393.23000000|271=0.13000000|272=20170503|273=22:35:18.408|269=0|270=1393.11000000|271=1.00000000|272=20170503|273=22:35:18.408|269=0|270=1393.02000000|271=0.33524135|272=20170503|273=22:35:18.408|269=0|270=1393.00000000|271=0.50000000|272=20170503|273=22:35:18.408|269=0|270=1392.52000000|271=0.02000000|272=20170503|273=22:35:18.408|269=0|270=1392.51000000|271=0.11000000|272=20170503|273=22:35:18.408|269=0|270=1392.50000000|271=0.10000000|272=20170503|273=22:35:18.408|269=0|270=1392.36000000|271=2.62000000|272=20170503|273=22:35:18.408|269=0|270=1392.31000000|271=0.02000000|272=20170503|273=22:35:18.408|269=0|270=1392.01000000|271=0.41000000|272=20170503|273=22:35:18.408|10=075|
```

```
public void OnMessage(QuickFix.FIX44.MarketDataSnapshotFullRefresh msg, SessionID s)  
{  
    for (int idx = 0; idx < msg.NoMDEntries.getValue(); idx++)  
    {  
        var level = new QuickFix.FIX44.MarketDataSnapshotFullRefresh.NoMDEntriesGroup();  
        msg.GetGroup(idx + 1, level);  
  
        Console.WriteLine($"Orderbook {level.MDEntryType} @ {msg.Symbol}:");  
        Console.WriteLine($" Date: {level.MDEntryDate}");  
        Console.WriteLine($" Time: {level.MDEntryTime}");  
        Console.WriteLine($" Px: {level.MDEntryPx}");  
        Console.WriteLine($" Size: {level.MDEntrySize}");  
    }  
}
```

| Tag | Name | Description |
| --- | --- | --- |
| 55 | Symbol | Our Symbol identifier *(full list available [here](/market-data/rest-api/metadata/#list-all-symbols-get))* |
| 262 | MDReqId | MDReqId (262) from Market Data Request (V) message. Used to link request to the Market Data, eg. with your internal identifier. |
| 268 | NoMdEntries | Number of levels in the orderbook. |
| => 269 | MDEntryType | Type Market Data entry.   Valid values:  * `0` = Bid * `1` = Ask/Offer |
| => 270 | MDEntryPx | Price level of the orderbook level |
| => 271 | MDEntrySize | Volume resting on this orderbook level |
| => 272 | MDEntryDate | Date of the orderbook reported by the exchange |
| => 273 | MDEntryTime | Time of the orderbook reported by the exchange with milliseconds |

Heartbeat 35=0[​](/market-data/fix/messages#heartbeat-350 "Direct link to heartbeat-350")
-----------------------------------------------------------------------------------------

```
8=FIX.4.4|9=87|35=0|34=13|49=COINAPI|52=20170503-22:21:27.545|56=73034021-THIS-IS-SAMPLE-KEY|10=048|
```

Message sent by any side after defined amount of seconds in communication silence.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

FIX API](/market-data/fix/)[Next

Introduction](/market-data/latency-faq/)

* [Standard Header](/market-data/fix/messages#standard-header)
* [Standard Trailer](/market-data/fix/messages#standard-trailer)
* [Logon 35=A](/market-data/fix/messages#logon-35a)
* [Logout 35x5](/market-data/fix/messages#logout-35x5)
* [Security List Request  35=x](/market-data/fix/messages#security-list-request--35x)
* [Security List  35=y](/market-data/fix/messages#security-list--35y)
* [Market Data Request  35=V](/market-data/fix/messages#market-data-request--35v)
* [Market Data Request Reject  35=Y](/market-data/fix/messages#market-data-request-reject--35y)
* [Market Data Incremental  35=X](/market-data/fix/messages#market-data-incremental--35x)
  + [Possible `MDEntryOriginator` values](/market-data/fix/messages#possible-mdentryoriginator-values)
* [Market Data Snapshot  35=W](/market-data/fix/messages#market-data-snapshot--35w)
* [Heartbeat 35=0](/market-data/fix/messages#heartbeat-350)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.