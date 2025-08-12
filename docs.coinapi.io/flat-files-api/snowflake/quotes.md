Quotes Dataset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/snowflake/quotes)

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
* [Snowflake Access](/flat-files-api/snowflake/)

  + [Introduction](/flat-files-api/snowflake/)
  + [Assets Dataset](/flat-files-api/snowflake/assets)
  + [Exchange Rates Dataset](/flat-files-api/snowflake/exchange-rates)
  + [Index Dataset](/flat-files-api/snowflake/index-data)
  + [Order Books Dataset](/flat-files-api/snowflake/orderbooks)
  + [Quotes Dataset](/flat-files-api/snowflake/quotes)
  + [OHLCV Dataset](/flat-files-api/snowflake/ohlcv)
  + [Trades Dataset](/flat-files-api/snowflake/trades)
* [S3 API](/flat-files-api/s3-api/)
* [Push API](/flat-files-api/rest-api/push-api)

* [Snowflake Access](/flat-files-api/snowflake/)
* Quotes Dataset

On this page

Quotes Dataset
==============

Overview[​](/flat-files-api/snowflake/quotes#overview "Direct link to Overview")
--------------------------------------------------------------------------------

The "QUOTES" dataset provides comprehensive information about real-time price quotes across trading venues. It includes detailed data about bid-ask prices, quote sizes and market maker activity across different timeframes.

This dataset helps users:

* Track best bid and ask prices in real-time
* Access quote sizes and market depth at the top of book
* Monitor quote update frequency and market activity
* Analyze market maker behavior and pricing patterns
* Evaluate market quality and trading conditions across venues

Table Details[​](/flat-files-api/snowflake/quotes#table-details "Direct link to Table Details")
-----------------------------------------------------------------------------------------------

**Name**: `LISTINGS.PUBLIC.QUOTESFUTURES`

**Name**: `LISTINGS.PUBLIC.QUOTESOPTIONS`

**Name**: `LISTINGS.PUBLIC.QUOTESPERPETUAL`

Schema[​](/flat-files-api/snowflake/quotes#schema "Direct link to Schema")
--------------------------------------------------------------------------

```
CREATE OR REPLACE TABLE LISTINGS.PUBLIC.QUOTESFUTURES (  
    symbol_id             VARCHAR(100),  
    time_exchange         TIMESTAMP_NTZ(9),  
    time_coinapi          TIMESTAMP_NTZ(9),  
    ask_price             NUMBER(38,8),  
    ask_size              NUMBER(38,8),  
    bid_price             NUMBER(38,8),  
    bid_size              NUMBER(38,8),  
);
```

Example Query[​](/flat-files-api/snowflake/quotes#example-query "Direct link to Example Query")
-----------------------------------------------------------------------------------------------

```
SELECT   
    symbol_id,  
    time_exchange,  
    time_coinapi,  
    ask_price,  
    ask_size,  
    bid_price,  
    bid_size,  
FROM QUOTESFUTURES  
WHERE symbol_id IS NOT NULL  
    AND ask_price > 0  
    AND bid_price > 0  
ORDER BY time_coinapi DESC  -- Most recent quotes first  
LIMIT 50;
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Order Books Dataset](/flat-files-api/snowflake/orderbooks)[Next

OHLCV Dataset](/flat-files-api/snowflake/ohlcv)

* [Overview](/flat-files-api/snowflake/quotes#overview)
* [Table Details](/flat-files-api/snowflake/quotes#table-details)
* [Schema](/flat-files-api/snowflake/quotes#schema)
* [Example Query](/flat-files-api/snowflake/quotes#example-query)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.