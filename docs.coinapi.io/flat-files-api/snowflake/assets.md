Assets Dataset | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/snowflake/assets)

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
* Assets Dataset

On this page

Assets Dataset
==============

Overview[​](/flat-files-api/snowflake/assets#overview "Direct link to Overview")
--------------------------------------------------------------------------------

The "ASSETS" dataset provides a comprehensive listing of various assets in the crypto markets. It includes metadata such as asset identifiers, names, date ranges for quotes, trades, orderbook activity, and additional metrics related to trading volume, price, and coverage dates.

This dataset helps users:

* Quickly discover new assets
* Understand available historical date ranges for quotes, trades, and orderbook data
* Evaluate the scope of coverage and key activity metrics

Table Details[​](/flat-files-api/snowflake/assets#table-details "Direct link to Table Details")
-----------------------------------------------------------------------------------------------

**Name**: `LISTINGS.PUBLIC.ASSETS`

Schema[​](/flat-files-api/snowflake/assets#schema "Direct link to Schema")
--------------------------------------------------------------------------

```
CREATE OR REPLACE TABLE LISTINGS.PUBLIC.ASSETS (  
    ASSET_ID              VARCHAR(16777216),  
    NAME                  VARCHAR(16777216),  
    DATA_QUOTE_START      TIMESTAMP_NTZ(9),  
    DATA_QUOTE_END        TIMESTAMP_NTZ(9),  
    DATA_ORDERBOOK_START  TIMESTAMP_NTZ(9),  
    DATA_ORDERBOOK_END    TIMESTAMP_NTZ(9),  
    DATA_TRADE_START      TIMESTAMP_NTZ(9),  
    DATA_TRADE_END        TIMESTAMP_NTZ(9),  
    DATA_SYMBOLS_COUNT    NUMBER(38,0),  
    VOLUME_1HRS_USD       NUMBER(38,2),  
    VOLUME_1DAY_USD       VARCHAR(16777216),  
    VOLUME_1MTH_USD       VARCHAR(16777216),  
    PRICE_USD             VARCHAR(16777216),  
    ID_ICON               VARCHAR(16777216),  
    DATA_START            DATE,  
    DATA_END              DATE  
);
```

Example Query[​](/flat-files-api/snowflake/assets#example-query "Direct link to Example Query")
-----------------------------------------------------------------------------------------------

```
SELECT   
    asset_id,   
    name,   
    data_start,   
    data_end  
FROM ASSETS  
WHERE data_start IS NOT NULL  
    AND data_end IS NOT NULL  
ORDER BY data_end - data_start DESC  
LIMIT 50;
```

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/flat-files-api/snowflake/)[Next

Exchange Rates Dataset](/flat-files-api/snowflake/exchange-rates)

* [Overview](/flat-files-api/snowflake/assets#overview)
* [Table Details](/flat-files-api/snowflake/assets#table-details)
* [Schema](/flat-files-api/snowflake/assets#schema)
* [Example Query](/flat-files-api/snowflake/assets#example-query)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.