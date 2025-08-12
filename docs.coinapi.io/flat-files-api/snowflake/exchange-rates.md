Exchange Rates Dataset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/snowflake/exchange-rates)

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
* Exchange Rates Dataset

On this page

Exchange Rates Dataset
======================

Overview[​](/flat-files-api/snowflake/exchange-rates#overview "Direct link to Overview")
----------------------------------------------------------------------------------------

The "EXCHANGERATES" dataset provides comprehensive information about currency exchange rates across global financial markets. It includes detailed data about currency pairs, historical rate movements, and key trading information across different timeframes and market conditions.

This dataset helps users:

* Track currency pair relationships and their historical patterns
* Access reliable exchange rate data across multiple time periods
* Monitor market volatility and rate fluctuations
* Analyze currency performance and market trends
* Evaluate cross-currency relationships and correlations

Table Details[​](/flat-files-api/snowflake/exchange-rates#table-details "Direct link to Table Details")
-------------------------------------------------------------------------------------------------------

**Name**: `LISTINGS.PUBLIC.EXCHANGERATES`

Schema[​](/flat-files-api/snowflake/exchange-rates#schema "Direct link to Schema")
----------------------------------------------------------------------------------

```
CREATE OR REPLACE TABLE LISTINGS.PUBLIC.EXCHANGERATES (  
    time_period_start     TIMESTAMP_NTZ(9),  
    time_period_end       TIMESTAMP_NTZ(9),  
    time_open             TIMESTAMP_NTZ(9),  
    time_close            TIMESTAMP_NTZ(9),  
    rate_open             NUMBER(38,2),  
    rate_high             NUMBER(38,2),  
    rate_low              NUMBER(38,2),  
    rate_close            NUMBER(38,2)  
);
```

Example Query[​](/flat-files-api/snowflake/exchange-rates#example-query "Direct link to Example Query")
-------------------------------------------------------------------------------------------------------

```
SELECT   
    time_period_start,  
    time_period_end,  
    rate_open,  
    rate_high,  
    rate_low,  
    rate_close,  
ROUND(((rate_close - rate_open) / rate_open) * 100, 2) as price_change_percent  
FROM EXCHANGERATES  
LIMIT 100;
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Assets Dataset](/flat-files-api/snowflake/assets)[Next

Index Dataset](/flat-files-api/snowflake/index-data)

* [Overview](/flat-files-api/snowflake/exchange-rates#overview)
* [Table Details](/flat-files-api/snowflake/exchange-rates#table-details)
* [Schema](/flat-files-api/snowflake/exchange-rates#schema)
* [Example Query](/flat-files-api/snowflake/exchange-rates#example-query)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.