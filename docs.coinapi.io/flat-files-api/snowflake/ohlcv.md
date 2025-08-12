OHLCV Dataset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/snowflake/ohlcv)

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
* OHLCV Dataset

On this page

OHLCV Dataset
=============

Overview[​](/flat-files-api/snowflake/ohlcv#overview "Direct link to Overview")
-------------------------------------------------------------------------------

The "OHLCV" dataset provides comprehensive information about price movements and trading activity across markets. It includes detailed data about opening, high, low, and closing prices, along with trading volumes across different timeframes.

This dataset helps users:

* Track price movements and trading ranges
* Access standardized price data across multiple intervals
* Monitor trading volume and market activity patterns
* Analyze price trends and market momentum
* Evaluate market volatility and trading intensity across periods

Table Details[​](/flat-files-api/snowflake/ohlcv#table-details "Direct link to Table Details")
----------------------------------------------------------------------------------------------

**Name**: `LISTINGS.PUBLIC.OHLCV`

Schema[​](/flat-files-api/snowflake/ohlcv#schema "Direct link to Schema")
-------------------------------------------------------------------------

```
CREATE OR REPLACE TABLE LISTINGS.PUBLIC.OHLCV (  
    time_period_start     TIMESTAMP_NTZ(9),  
    time_period_end       TIMESTAMP_NTZ(9),  
    time_open             TIMESTAMP_NTZ(9),  
    time_close            TIMESTAMP_NTZ(9),  
    price_open            NUMBER(38,8),  
    price_high            NUMBER(38,8),  
    price_low             NUMBER(38,8),  
    price_close           NUMBER(38,8),  
    volume_traded         NUMBER(38,8),  
    trades_count          NUMBER(38,0)  
);
```

Example Query[​](/flat-files-api/snowflake/ohlcv#example-query "Direct link to Example Query")
----------------------------------------------------------------------------------------------

```
SELECT   
    time_period_start,  
    time_period_end,  
    time_open,  
    time_close,  
    price_open,  
    price_high,  
    price_low,  
    price_close,  
    volume_traded,  
    trades_count,  
FROM OHLCV  
WHERE time_period_start IS NOT NULL  
    AND price_open > 0  
    AND volume_traded > 0  
ORDER BY time_period_start DESC  -- Most recent periods first  
LIMIT 50;
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Quotes Dataset](/flat-files-api/snowflake/quotes)[Next

Trades Dataset](/flat-files-api/snowflake/trades)

* [Overview](/flat-files-api/snowflake/ohlcv#overview)
* [Table Details](/flat-files-api/snowflake/ohlcv#table-details)
* [Schema](/flat-files-api/snowflake/ohlcv#schema)
* [Example Query](/flat-files-api/snowflake/ohlcv#example-query)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.