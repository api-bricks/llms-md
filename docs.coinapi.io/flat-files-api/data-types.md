Data Types and File Structure Overview | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/data-types/)

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

* Data & Structure

On this page

Data Types and File Structure Overview
======================================

The Flat Files S3 API provides access to various types of cryptocurrency market data. This document provides an overview of the available data types and the general file structure used across the system.

Available Data Types[​](/flat-files-api/data-types/#available-data-types "Direct link to Available Data Types")
---------------------------------------------------------------------------------------------------------------

Our API offers the following types of market data:

1. Quotes
2. Trades
3. Limit Book Snapshots
4. Full Limit Order Book
5. OHLCV (Open, High, Low, Close, Volume) - Coming soon

Each data type is documented in detail in its respective article, including field descriptions, data formats, and usage examples. You will find the articles in left-side menu.

File Structure[​](/flat-files-api/data-types/#file-structure "Direct link to File Structure")
---------------------------------------------------------------------------------------------

Data in the S3 bucket is organized according to the following structure:

```
/  
├── T-TRADES/  
│   └── D-YYYYMMDD/  
│       └── E-[EXCHANGE]/  
│           └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz  
├── T-QUOTES/  
│   └── D-YYYYMMDD/  
│       └── E-[EXCHANGE]/  
│           └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz  
├── T-LIMITBOOK_FULL/  
│   └── D-YYYYMMDD/  
│       └── E-[EXCHANGE]/  
│           └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz  
└── T-OHLCV/  
    └── D-YYYYMMDD/  
        └── E-[EXCHANGE]/  
            └── IDDI-[IDENTIFIER]+SC-[COINAPI_SYMBOL_ID]+S-[EXCHANGE_SYMBOL].csv.gz
```

Where:

* `YYYYMMDD` represents the date of the data
* `[EXCHANGE]` is the identifier for the specific exchange
* `[IDENTIFIER]` is a unique identifier for the data file
* `[COINAPI_SYMBOL_ID]` is the CoinAPI symbol identifier
* `[EXCHANGE_SYMBOL]` is the symbol as used by the exchange

File Format[​](/flat-files-api/data-types/#file-format "Direct link to File Format")
------------------------------------------------------------------------------------

All data files are stored in CSV (Comma-Separated Values) format and compressed using gzip compression. This approach balances human readability with efficient storage and transfer sizes.

To use these files:

1. Download the `.csv.gz` file
2. Decompress the file using a tool that supports gzip (e.g., gzip, 7-zip)
3. Open the resulting CSV file in a spreadsheet application or process it with your preferred data analysis tool

Data Consistency and Synchronization[​](/flat-files-api/data-types/#data-consistency-and-synchronization "Direct link to Data Consistency and Synchronization")
---------------------------------------------------------------------------------------------------------------------------------------------------------------

All timestamp fields across different data types are synchronized to ensure consistency when analyzing data from multiple sources. We use high-precision time synchronization to maintain accuracy across our data collection infrastructure.

Best Practices for Data Retrieval[​](/flat-files-api/data-types/#best-practices-for-data-retrieval "Direct link to Best Practices for Data Retrieval")
------------------------------------------------------------------------------------------------------------------------------------------------------

1. Use date-based partitioning to efficiently retrieve data for specific time periods.
2. Leverage the prefix functionality in S3 listing operations to filter data by exchange, symbol, or date.
3. Implement parallel downloads for large datasets to improve retrieval speed.
4. Consider implementing local caching for frequently accessed data to reduce API calls and improve application performance.

For detailed information on each data type, please refer to the individual data type documentation.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Flat Files](/flat-files-api/)[Next

Data Types and File Structure Overview](/flat-files-api/data-types/)

* [Available Data Types](/flat-files-api/data-types/#available-data-types)
* [File Structure](/flat-files-api/data-types/#file-structure)
* [File Format](/flat-files-api/data-types/#file-format)
* [Data Consistency and Synchronization](/flat-files-api/data-types/#data-consistency-and-synchronization)
* [Best Practices for Data Retrieval](/flat-files-api/data-types/#best-practices-for-data-retrieval)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.