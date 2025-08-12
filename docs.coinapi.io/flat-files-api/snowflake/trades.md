Trades Dataset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/snowflake/trades)

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
* Trades Dataset

On this page

Trades Dataset
==============

Overview[​](/flat-files-api/snowflake/trades#overview "Direct link to Overview")
--------------------------------------------------------------------------------

The "TRADES" dataset provides information about executed transactions across trading venues. It includes detailed data about trade prices, sizes, and execution timestamps.

This dataset helps users:

* Track individual transaction details and execution prices
* Access historical trade data across multiple venues
* Monitor trading activity and market liquidity
* Analyze price impact and trade size patterns
* Evaluate execution quality and market efficiency

Table Details[​](/flat-files-api/snowflake/trades#table-details "Direct link to Table Details")
-----------------------------------------------------------------------------------------------

**Name**: `LISTINGS.PUBLIC.TRADES`

**Name**: `LISTINGS.PUBLIC.TRADESUNISWAP`

Schema[​](/flat-files-api/snowflake/trades#schema "Direct link to Schema")
--------------------------------------------------------------------------

```
CREATE OR REPLACE TABLE LISTINGS.PUBLIC.TRADES (  
    symbol_id             VARCHAR(100),  
    time_exchange         TIMESTAMP_NTZ(9),  
    time_coinapi          TIMESTAMP_NTZ(9),  
    uuid                  VARCHAR(36),  
  
    Standard UUID length  
    price                 NUMBER(38,8),  
    size                  NUMBER(38,8),  
    taker_side            VARCHAR(4),  
  
    'BUY' or 'SELL'  
    id_trade              VARCHAR(100),  
      
    Exchange-specific trade ID  
    id_order_maker        VARCHAR(100),  
    id_order_taker        VARCHAR(100)  
);
```

Example Query[​](/flat-files-api/snowflake/trades#example-query "Direct link to Example Query")
-----------------------------------------------------------------------------------------------

```
SELECT   
    symbol_id,  
    time_exchange,  
    time_coinapi,  
    uuid,  
    price,  
    size,  
    taker_side,  
    id_trade,  
    id_order_maker,  
    id_order_taker,  
FROM TRADESUNISWAP  
WHERE symbol_id IS NOT NULL  
    AND price > 0  -- Ensure valid price  
    AND size > 0   -- Ensure valid size  
ORDER BY time_coinapi DESC  -- Most recent trades first  
LIMIT 50;
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

OHLCV Dataset](/flat-files-api/snowflake/ohlcv)[Next

Introduction](/flat-files-api/s3-api/)

* [Overview](/flat-files-api/snowflake/trades#overview)
* [Table Details](/flat-files-api/snowflake/trades#table-details)
* [Schema](/flat-files-api/snowflake/trades#schema)
* [Example Query](/flat-files-api/snowflake/trades#example-query)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.