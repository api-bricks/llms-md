Trades | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/data-types/trades)

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
* Trades

On this page

Trades
======

Overview[​](/flat-files-api/data-types/trades#overview "Direct link to Overview")
---------------------------------------------------------------------------------

The Trades data type provides information about individual transactions that have occurred on an exchange for a specific trading pair. This data is crucial for understanding market activity, price movements, and trading volumes.

File Organization[​](/flat-files-api/data-types/trades#file-organization "Direct link to File Organization")
------------------------------------------------------------------------------------------------------------

Trade data is organized in the S3 bucket as follows:

```
T-TRADES/  
└── D-YYYYMMDD/  
    └── E-[EXCHANGE]/  
        └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz
```

Example: `T-TRADES/D-20230701/E-BINANCE/IDDI-1234+SC-BINANCE_SPOT_ETH_USDT+S-ETH-USDT.csv.gz`

Where:

* `T-QUOTES`: Indicates the data type (Quotes)
* `D-YYYYMMDD`: Date of the data
* `E-[EXCHANGE]`: Exchange name
* `IDDI-[IDENTIFIER]`: CoinAPI's internal identifier
* `SC-[COINAPI_SYMBOL_ID]`: CoinAPI's symbol identifier
* `S-[EXCHANGE_SYMBOL]`: The symbol as identified by the exchange

File Format[​](/flat-files-api/data-types/trades#file-format "Direct link to File Format")
------------------------------------------------------------------------------------------

Files are in CSV format, compressed with gzip. Each row represents a single trade.

Data Fields[​](/flat-files-api/data-types/trades#data-fields "Direct link to Data Fields")
------------------------------------------------------------------------------------------

| Column Name | Type | Description |
| --- | --- | --- |
| time\_exchange | datetime | UTC timestamp of the trade provided by the exchange or estimated using the exchange API delay. |
| time\_coinapi | datetime | UTC timestamp when CoinAPI first received the trade information. |
| guid | string | Unique identifier of the trade provided by CoinAPI. |
| price | decimal | Price at which the trade occurred. |
| base\_amount | decimal | Amount of base asset traded in the transaction. |
| taker\_side | string | Aggressor side of the transaction. Possible values: BUY, SELL, BUY\_ESTIMATED, SELL\_ESTIMATED, UNKNOWN. |
| id\_exch\_guid | string | Applicable if identifiers are not integers. |
| id\_exch\_int\_inc | integer | Exchange trade ID |
| order\_id\_maker | string | Unique identifier assigned to the maker's side of a trade (Only for L3). |
| order\_id\_taker | string | Unique identifier assigned to the taker's side of a trade (Only for L3). |

Example Data[​](/flat-files-api/data-types/trades#example-data "Direct link to Example Data")
---------------------------------------------------------------------------------------------

```
time_exchange;time_coinapi;guid;price;base_amount;taker_side;id_exch_guid;id_exch_int_inc;order_id_maker;order_id_taker  
2025-02-14T13:30:03.5851480;2025-02-14T13:30:48.4535346;723787cc-c2c2-42e0-9c17-47533847600f;0.00000732;180.35;BUY;;;;  
2025-02-14T12:50:00.6090960;2025-02-14T13:30:48.4535346;c6f313f5-cef6-4974-8397-f9a472b3a169;0.00000723;1410.59;SELL;;;;  
2025-02-14T12:35:53.4036209;2025-02-14T13:30:48.4535346;9c68a7ee-7b5a-4c81-82bb-dbb8976b917a;0.00000722;462.49;SELL;;;;  
2025-02-14T12:09:06.7816889;2025-02-14T13:30:48.4535346;0cf1ad21-9a43-459d-bede-d6fd9b7a4a14;0.00000728;963.14;BUY;;;;  
2025-02-14T12:02:12.9110560;2025-02-14T13:30:48.4535346;a568765e-2f67-4b38-9b70-d0a677653f52;0.00000729;676.59;SELL;;;;
```

Data Collection Process[​](/flat-files-api/data-types/trades#data-collection-process "Direct link to Data Collection Process")
------------------------------------------------------------------------------------------------------------------------------

1. We maintain real-time connections to supported exchanges.
2. As trades occur, we capture the trade information provided by the exchange.
3. The data is processed, normalized, and stored in our system.
4. At the end of each day (UTC), the data is aggregated into daily files and uploaded to the S3 bucket.

Taker Side Explanation[​](/flat-files-api/data-types/trades#taker-side-explanation "Direct link to Taker Side Explanation")
---------------------------------------------------------------------------------------------------------------------------

* BUY: The exchange reported that the trade aggressor was buying.
* SELL: The exchange reported that the trade aggressor was selling.
* BUY\_ESTIMATED: The exchange didn't report the aggressor; we estimated it was more likely a buy.
* SELL\_ESTIMATED: The exchange didn't report the aggressor; we estimated it was more likely a sell.
* UNKNOWN: The exchange didn't report the aggressor, and we couldn't confidently estimate it.

Corner Cases and Special Considerations[​](/flat-files-api/data-types/trades#corner-cases-and-special-considerations "Direct link to Corner Cases and Special Considerations")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Time Discrepancies**: There might be slight differences between `time_exchange` and `time_coinapi` due to network latency or exchange API delays.
2. **Estimated Taker Side**: When the exchange doesn't provide the taker side, we use our algorithms to estimate it. These estimations are based on order book data and may not always be 100% accurate.
3. **Trade Reversals**: In rare cases, exchanges might reverse or cancel trades. These are typically not reflected in our data, so be aware that very recent trade data might be subject to change on the exchange itself.

Usage Tips[​](/flat-files-api/data-types/trades#usage-tips "Direct link to Usage Tips")
---------------------------------------------------------------------------------------

1. Use the `guid` field to uniquely identify trades and avoid double-counting when processing multiple files.
2. The `base_amount` field represents the amount in the base currency of the trading pair (e.g., BTC in BTC/USDT).
3. To calculate the total value of a trade in the quote currency, multiply `price` by `base_amount`.
4. When analyzing trade direction, consider using only BUY and SELL categories for the most accurate data, or include estimated values if you need more comprehensive data.

For any questions or issues with the Trades data, please contact our support team.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Quotes](/flat-files-api/data-types/quotes)[Next

Full Limit Order Book](/flat-files-api/data-types/limitbook)

* [Overview](/flat-files-api/data-types/trades#overview)
* [File Organization](/flat-files-api/data-types/trades#file-organization)
* [File Format](/flat-files-api/data-types/trades#file-format)
* [Data Fields](/flat-files-api/data-types/trades#data-fields)
* [Example Data](/flat-files-api/data-types/trades#example-data)
* [Data Collection Process](/flat-files-api/data-types/trades#data-collection-process)
* [Taker Side Explanation](/flat-files-api/data-types/trades#taker-side-explanation)
* [Corner Cases and Special Considerations](/flat-files-api/data-types/trades#corner-cases-and-special-considerations)
* [Usage Tips](/flat-files-api/data-types/trades#usage-tips)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.