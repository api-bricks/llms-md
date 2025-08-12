Order Books Dataset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/snowflake/orderbooks)

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
* Order Books Dataset

On this page

Order Books Dataset
===================

Overview[​](/flat-files-api/snowflake/orderbooks#overview "Direct link to Overview")
------------------------------------------------------------------------------------

The "ORDERBOOKS" dataset provides comprehensive information about market depth and liquidity across trading venues. It includes detailed data about bid-ask spreads, order sizes, price levels, and real-time order flow.

This dataset helps users:

* Track market depth and available liquidity at different price levels
* Access real-time order book snapshots across multiple venues
* Monitor bid-ask spread dynamics and market making activity
* Analyze order flow patterns and market microstructure
* Evaluate trading costs and market impact across different order sizes

Table Details[​](/flat-files-api/snowflake/orderbooks#table-details "Direct link to Table Details")
---------------------------------------------------------------------------------------------------

**Name**: `LISTINGS.PUBLIC.ORDERBOOKS`

Schema[​](/flat-files-api/snowflake/orderbooks#schema "Direct link to Schema")
------------------------------------------------------------------------------

```
CREATE OR REPLACE TABLE LISTINGS.PUBLIC.ORDERBOOK_DEPTH (  
    symbol_id             VARCHAR(100),  
    time_exchange         TIMESTAMP_NTZ(9),  
    time_coinapi          TIMESTAMP_NTZ(9),  
  
    Level 0  
    ask_price_0           NUMBER(38,8),  
    ask_size_0            NUMBER(38,8),  
    bid_price_0           NUMBER(38,8),  
    bid_size_0            NUMBER(38,8),  
  
    Level 1  
    ask_price_1           NUMBER(38,8),  
    ask_size_1            NUMBER(38,8),  
    bid_price_1           NUMBER(38,8),  
    bid_size_1            NUMBER(38,8),  
  
    Level n  
    ask_price_n           NUMBER(38,8),  
    ask_size_n            NUMBER(38,8),  
    bid_price_n           NUMBER(38,8),  
    bid_size_n            NUMBER(38,8),,  
);
```

Example Query[​](/flat-files-api/snowflake/orderbooks#example-query "Direct link to Example Query")
---------------------------------------------------------------------------------------------------

```
SELECT   
    symbol_id,  
    time_exchange,  
    time_coinapi  
FROM ORDERBOOKS  
LIMIT 5;
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Index Dataset](/flat-files-api/snowflake/index-data)[Next

Quotes Dataset](/flat-files-api/snowflake/quotes)

* [Overview](/flat-files-api/snowflake/orderbooks#overview)
* [Table Details](/flat-files-api/snowflake/orderbooks#table-details)
* [Schema](/flat-files-api/snowflake/orderbooks#schema)
* [Example Query](/flat-files-api/snowflake/orderbooks#example-query)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.