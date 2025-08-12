Quotes | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/data-types/quotes)

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
* Quotes

On this page

Quotes
======

Overview[​](/flat-files-api/data-types/quotes#overview "Direct link to Overview")
---------------------------------------------------------------------------------

The Quotes data type provides information about the best bid and ask prices for a specific trading pair on an exchange. This data is crucial for understanding the current state of the market and the spread between buy and sell orders.

File Organization[​](/flat-files-api/data-types/quotes#file-organization "Direct link to File Organization")
------------------------------------------------------------------------------------------------------------

Quote data is organized in the S3 bucket as follows:

```
T-QUOTES/  
└── D-YYYYMMDD/  
    └── E-[EXCHANGE]/  
        └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz
```

Example: `T-QUOTES/D-20230701/E-BINANCE/IDDI-1234+SC-BINANCE_SPOT_ETH_USDT+S-ETH-USDT.csv.gz`

Where:

* `T-QUOTES`: Indicates the data type (Quotes)
* `D-YYYYMMDD`: Date of the data
* `E-[EXCHANGE]`: Exchange name
* `IDDI-[IDENTIFIER]`: CoinAPI's internal identifier
* `SC-[COINAPI_SYMBOL_ID]`: CoinAPI's symbol identifier
* `S-[EXCHANGE_SYMBOL]`: The symbol as identified by the exchange

File Format[​](/flat-files-api/data-types/quotes#file-format "Direct link to File Format")
------------------------------------------------------------------------------------------

Files are in CSV format, compressed with gzip. Each row represents a single quote update.

Data Fields[​](/flat-files-api/data-types/quotes#data-fields "Direct link to Data Fields")
------------------------------------------------------------------------------------------

| Column Name | Type | Description |
| --- | --- | --- |
| id\_site\_coinapi | string | UUID of the site which received the quote. Useful for replaying markets from the perspective of an algorithmic trading strategy. |
| time\_exchange | datetime | UTC timestamp of the quote provided by the exchange or estimated using the exchange API delay. |
| time\_coinapi | datetime | UTC timestamp when CoinAPI first received the quote. Useful for replaying markets from an algorithmic trading strategy perspective. |
| ask\_px | decimal | Best ask (sell) price |
| ask\_sx | decimal | Total amount of volume resting on the best ask level in the base asset of the symbol |
| bid\_px | decimal | Best bid (buy) price |
| bid\_sx | decimal | Total amount of volume resting on the best bid level in the base asset of the symbol |

Example Data[​](/flat-files-api/data-types/quotes#example-data "Direct link to Example Data")
---------------------------------------------------------------------------------------------

```
id_site_coinapi,time_exchange,time_coinapi,ask_px,ask_sx,bid_px,bid_sx  
550e8400-e29b-41d4-a716-446655440000,2023-07-01T12:00:00.123456Z,2023-07-01T12:00:00.234567Z,30000.50,1.5,30000.00,2.0  
550e8400-e29b-41d4-a716-446655440001,2023-07-01T12:00:01.123456Z,2023-07-01T12:00:01.234567Z,30001.00,1.2,30000.50,1.8
```

Data Collection Process[​](/flat-files-api/data-types/quotes#data-collection-process "Direct link to Data Collection Process")
------------------------------------------------------------------------------------------------------------------------------

1. We continuously monitor the order books of supported exchanges.
2. When a change in the best bid or ask is detected, a new quote entry is recorded.
3. The data is processed, normalized, and stored in our system.
4. At the end of each day (UTC), the data is aggregated into daily files and uploaded to the S3 bucket.

Corner Cases and Special Considerations[​](/flat-files-api/data-types/quotes#corner-cases-and-special-considerations "Direct link to Corner Cases and Special Considerations")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Missing Data**: If an exchange experiences downtime or connectivity issues, there may be gaps in the quote data.
2. **Extreme Values**: During periods of high volatility, you may observe unusually large spreads or extreme prices. These are typically valid market conditions rather than errors.
3. **time\_exchange vs time\_coinapi**: If these times are equal, it means the exchange did not provide a timestamp, and we're using our receipt time for both fields.

Usage Tips[​](/flat-files-api/data-types/quotes#usage-tips "Direct link to Usage Tips")
---------------------------------------------------------------------------------------

1. When analyzing spread, calculate it as `ask_px - bid_px`.
2. The `ask_sx` and `bid_sx` fields can be used to gauge market depth at the best prices.
3. Comparing `time_exchange` and `time_coinapi` can provide insights into latency between the exchange and our data collection points.

For any questions or issues with the Quotes data, please contact our support team.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Data Types and File Structure Overview](/flat-files-api/data-types/)[Next

Trades](/flat-files-api/data-types/trades)

* [Overview](/flat-files-api/data-types/quotes#overview)
* [File Organization](/flat-files-api/data-types/quotes#file-organization)
* [File Format](/flat-files-api/data-types/quotes#file-format)
* [Data Fields](/flat-files-api/data-types/quotes#data-fields)
* [Example Data](/flat-files-api/data-types/quotes#example-data)
* [Data Collection Process](/flat-files-api/data-types/quotes#data-collection-process)
* [Corner Cases and Special Considerations](/flat-files-api/data-types/quotes#corner-cases-and-special-considerations)
* [Usage Tips](/flat-files-api/data-types/quotes#usage-tips)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.