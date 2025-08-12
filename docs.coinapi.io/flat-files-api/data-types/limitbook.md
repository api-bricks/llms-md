Full Limit Order Book | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/data-types/limitbook)

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

* [Flat Files](/flat-files-api/)
* [Data & Structure](/flat-files-api/data-types/)

  + [Data Types and File Structure Overview](/flat-files-api/data-types/)
  + [Quotes](/flat-files-api/data-types/quotes)
  + [Trades](/flat-files-api/data-types/trades)
  + [Full Limit Order Book](/flat-files-api/data-types/limitbook)
* [Snowflake Access](/flat-files-api/snowflake/)
* [S3 API](/flat-files-api/s3-api/)
* [Push API](/flat-files-api/rest-api/push-api)

* [Data & Structure](/flat-files-api/data-types/)
* Full Limit Order Book

On this page

Full Limit Order Book
=====================

Overview[​](/flat-files-api/data-types/limitbook#overview "Direct link to Overview")
------------------------------------------------------------------------------------

The Full Limit Order Book (LOB) data type provides a comprehensive view of the order book for a specific trading pair on an exchange. It captures all changes to the order book, allowing for a detailed reconstruction of the market state at any given moment.

File Organization[​](/flat-files-api/data-types/limitbook#file-organization "Direct link to File Organization")
---------------------------------------------------------------------------------------------------------------

Full Limit Order Book data is organized in the S3 bucket as follows:

```
T-LIMITBOOK_FULL/  
└── D-YYYYMMDD/  
    └── E-[EXCHANGE]/  
        └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz
```

Example: `T-LIMITBOOK/D-20230701/E-BINANCE/IDDI-1234+SC-BINANCE_SPOT_ETH_USDT+S-ETH-USDT.csv.gz`

Where:

* `T-QUOTES`: Indicates the data type (Quotes)
* `D-YYYYMMDD`: Date of the data
* `E-[EXCHANGE]`: Exchange name
* `IDDI-[IDENTIFIER]`: CoinAPI's internal identifier
* `SC-[COINAPI_SYMBOL_ID]`: CoinAPI's symbol identifier
* `S-[EXCHANGE_SYMBOL]`: The symbol as identified by the exchange

File Format[​](/flat-files-api/data-types/limitbook#file-format "Direct link to File Format")
---------------------------------------------------------------------------------------------

Files are in CSV format, compressed with gzip. Each row represents a single update to the order book.

Data Fields[​](/flat-files-api/data-types/limitbook#data-fields "Direct link to Data Fields")
---------------------------------------------------------------------------------------------

| Column Name | Type | Description |
| --- | --- | --- |
| time\_exchange | datetime | UTC timestamp of the update provided by the exchange or estimated using the exchange API delay. |
| time\_coinapi | datetime | UTC timestamp when CoinAPI first received the update. |
| is\_buy | boolean | Indicates if the update is related to the bid side of the book. 0 for ask (sell), 1 for bid (buy). |
| update\_type | string | Type of the update. Possible values: ADD, SUB, MATCH, SET, DELETE, SNAPSHOT. |
| entry\_px | decimal | Price identifying the book level. |
| entry\_sx | decimal | Volume associated with the specific update item. |
| order\_id | string | ID of the order if the format is Level 3 (order-by-order), empty if the format is Level 2. |

Example Data[​](/flat-files-api/data-types/limitbook#example-data "Direct link to Example Data")
------------------------------------------------------------------------------------------------

```
time_exchange,time_coinapi,is_buy,update_type,entry_px,entry_sx,order_id  
2023-07-01T12:00:00.123456Z,2023-07-01T12:00:00.234567Z,1,ADD,30000.00,1.5,ord123  
2023-07-01T12:00:01.123456Z,2023-07-01T12:00:01.234567Z,0,DELETE,30005.00,0.5,ord124  
2023-07-01T12:00:02.123456Z,2023-07-01T12:00:02.234567Z,1,SUB,30000.00,0.5,ord123
```

Data Collection Process[​](/flat-files-api/data-types/limitbook#data-collection-process "Direct link to Data Collection Process")
---------------------------------------------------------------------------------------------------------------------------------

1. We maintain a real-time connection to each supported exchange.
2. Every change to the order book is captured and recorded.
3. The data is processed, normalized, and stored in our system.
4. At the end of each day (UTC), the data is aggregated into daily files and uploaded to the S3 bucket.

Update Types Explained[​](/flat-files-api/data-types/limitbook#update-types-explained "Direct link to Update Types Explained")
------------------------------------------------------------------------------------------------------------------------------

* ADD: Adds a new order to the book.
* SUB: Subtracts volume from an existing order.
* MATCH: Similar to SUB, but indicates the subtraction was due to a trade execution.
* SET: Sets a new volume for an existing order.
* DELETE: Removes an order from the book.
* SNAPSHOT: Provides a full snapshot of the order book. All previous data should be discarded before processing a SNAPSHOT.

Corner Cases and Special Considerations[​](/flat-files-api/data-types/limitbook#corner-cases-and-special-considerations "Direct link to Corner Cases and Special Considerations")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Order ID Usage**: Some exchanges provide order IDs (Level 3 data), while others don't (Level 2 data). When order IDs are not available, the `order_id` field will be empty.
2. **Snapshots**: Snapshots are typically provided at the start of each day or after a disconnection. Always process SNAPSHOT updates by clearing the existing book first.
3. **High Frequency Updates**: During periods of high volatility, you may observe a very high frequency of updates.

Usage Tips[​](/flat-files-api/data-types/limitbook#usage-tips "Direct link to Usage Tips")
------------------------------------------------------------------------------------------

1. To reconstruct the full order book, process updates sequentially, maintaining the state of the book in memory.
2. Use the `time_exchange` field for accurate sequencing of updates.
3. Pay attention to the `update_type` field to correctly apply changes to your local order book representation.

For any questions or issues with the Full Limit Order Book data, please contact our support team.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Trades](/flat-files-api/data-types/trades)[Next

Introduction](/flat-files-api/snowflake/)

* [Overview](/flat-files-api/data-types/limitbook#overview)
* [File Organization](/flat-files-api/data-types/limitbook#file-organization)
* [File Format](/flat-files-api/data-types/limitbook#file-format)
* [Data Fields](/flat-files-api/data-types/limitbook#data-fields)
* [Example Data](/flat-files-api/data-types/limitbook#example-data)
* [Data Collection Process](/flat-files-api/data-types/limitbook#data-collection-process)
* [Update Types Explained](/flat-files-api/data-types/limitbook#update-types-explained)
* [Corner Cases and Special Considerations](/flat-files-api/data-types/limitbook#corner-cases-and-special-considerations)
* [Usage Tips](/flat-files-api/data-types/limitbook#usage-tips)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.