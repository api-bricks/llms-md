Ohlcv | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/ohlcv/)

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

* [Market Data API](/market-data/)
* [Authentication](/market-data/authentication)
* [API limits and billing](/market-data/api-limits-and-billing-metrics)
* [Metadata Tables](/market-data/metadata-tables/introduction)
* [REST API](/market-data/rest-api/)

  + [Introduction](/market-data/rest-api/)
  + [Exchange Rates](/market-data/rest-api/exchange-rates/)
  + [Metadata](/market-data/rest-api/metadata/)
  + [MetricsV1](/market-data/rest-api/metricsv1/)
  + [MetricsV2](/market-data/rest-api/metricsv2/)
  + [Ohlcv](/market-data/rest-api/ohlcv/)

    - [Introduction](/market-data/rest-api/ohlcv/coinapi-market-data-rest-api)
    - [Historical data by exchange](/market-data/rest-api/ohlcv/historical-data-by-exchange)
    - [Historical data](/market-data/rest-api/ohlcv/historical-data)
    - [Latest data](/market-data/rest-api/ohlcv/latest-data)
    - [List all periods](/market-data/rest-api/ohlcv/list-all-periods)
  + [Options](/market-data/rest-api/options/)
  + [Order Book](/market-data/rest-api/order-book/)
  + [Order Book L3](/market-data/rest-api/order-book-l3/)
  + [Quotes](/market-data/rest-api/quotes/)
  + [Trades](/market-data/rest-api/trades/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* REST API
* Ohlcv

Ohlcv
=====

API calls described in this section are related to downloading OHLCV *(Open, High, Low, Close, Volume)* timeseries data.
Each data point of this timeseries represents several indicators calculated from transactions activity inside a time range (period).

info

OHLCV data primary purpose is to present an overview of the market in human readable form.
It's often used to visualize market data on charts, websites, and various kinds of reports.

tip

CoinAPI expanded the standard OHLCV timeseries by including time of first and last trade and amount of trades executed inside period.

[📄️ Introduction
---------------](/market-data/rest-api/ohlcv/coinapi-market-data-rest-api)

[📄️ Historical data by exchange
------------------------------

Get OHLCV timeseries data returned in time ascending order. Data can be requested by the period and for the specific exchange eg `BITSTAMP`](/market-data/rest-api/ohlcv/historical-data-by-exchange)

[📄️ Historical data
------------------

Get OHLCV timeseries data returned in time ascending order. Data can be requested by the period and for the specific symbol eg `BITSTAMP\_SPOT\_BTC\_USD`, if you need to query timeseries by asset pairs eg. `BTC/USD`, then please reffer to the Exchange Rates Timeseries data](/market-data/rest-api/ohlcv/historical-data)

[📄️ Latest data
--------------

Get OHLCV latest timeseries data returned in time descending order. Data can be requested by the period and for the specific symbol eg `BITSTAMP\_SPOT\_BTC\_USD`, if you need to query timeseries by asset pairs eg. `BTC/USD`, then please reffer to the Exchange Rates Timeseries data](/market-data/rest-api/ohlcv/latest-data)

[📄️ List all periods
-------------------

Get full list of supported time periods available for requesting OHLCV timeseries data.](/market-data/rest-api/ohlcv/list-all-periods)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Listing of metrics available for specific exchange](/market-data/rest-api/metricsv2/listing-of-metrics-available-for-specific-exchange)[Next

Introduction](/market-data/rest-api/ohlcv/coinapi-market-data-rest-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.