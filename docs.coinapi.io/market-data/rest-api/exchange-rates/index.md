Exchange Rates | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/exchange-rates/)

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

    - [Introduction](/market-data/rest-api/exchange-rates/coinapi-market-data-rest-api)
    - [Get all current rates](/market-data/rest-api/exchange-rates/get-all-current-rates)
    - [Get specific rate](/market-data/rest-api/exchange-rates/get-specific-rate)
    - [Timeseries data](/market-data/rest-api/exchange-rates/timeseries-data)
    - [Timeseries periods](/market-data/rest-api/exchange-rates/timeseries-periods)
  + [Metadata](/market-data/rest-api/metadata/)
  + [MetricsV1](/market-data/rest-api/metricsv1/)
  + [MetricsV2](/market-data/rest-api/metricsv2/)
  + [Ohlcv](/market-data/rest-api/ohlcv/)
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
* Exchange Rates

Exchange Rates
==============

Exchange rate is defined as (VWAP-24H) last 24 hour (rolling window over time) Volume Weighted Average Price across multiple data sources listed on our platform. We are selecting and managing the data sources that are used in the calculation based on multiple factors to provide data of highest quality.

Algorithm is described below:

1. Exchange rates are produced from quotes, trades, and metadata datasets.
2. Symbols that are not data\_type = "SPOT" are excluded from the calculation.
3. Symbols from the data sources that were marked by us as not legitimate are excluded from the calculation.
4. Quotes data where the spread is outside the range of `<0$; 67%>` are discarded. `spreadPrc = (ask - bid) / ((ask + bid) / 2)`
5. The midpoint from the quote data is used as a pricing reference and it's weighted by the passive cumulative volume resting on the best prices.
6. Volume from the trades is used to weight the midpoint prices in the VWAP24 algorithm.
7. Midpoint data that has not been updated in the last 5 minutes and 1 second is discarded.
8. The last 24-hour volume for each symbol is updated every 4 hours when approximately 20% of the data in the sliding window changes (also, the list of eligible markets is updated at the same time).
9. Everywhere in the algorithm below, we are using asset pairs only from exchanges that have the highest legitimacy rank, and the rest of the exchanges are discarded. As we establish the highest-ranking exchanges that have this data for each asset pair, we ensure that the highest quality data is used for each of them. The rank used for asset pairing is carried over to the following steps.
10. Every 1 second, we update VWAP24 data for every asset pair across all data sources.
11. For each asset pair, we also discard data that is outside the 3 sigma range if there are at least 3 exchanges for this asset pair.
12. From the VWAP24 data, we are creating a tree structure where node/vertex = asset and edge = rate.
13. By traversing the tree structure using the BFS algorithm and our secret sauce, we are able to establish the final exchange rates.

[📄️ Introduction
---------------](/market-data/rest-api/exchange-rates/coinapi-market-data-rest-api)

[📄️ Get all current rates
------------------------

Get the current exchange rate between requested asset and all other assets.](/market-data/rest-api/exchange-rates/get-all-current-rates)

[📄️ Get specific rate
--------------------

Retrieves the exchange rate for a specific base and quote asset at a given time or the current rate.](/market-data/rest-api/exchange-rates/get-specific-rate)

[📄️ Timeseries data
------------------

Get the historical exchange rates between two assets in the form of the timeseries.](/market-data/rest-api/exchange-rates/timeseries-data)

[📄️ Timeseries periods
---------------------

You can also obtain historical exchange rates of any asset pair, grouped into time periods.](/market-data/rest-api/exchange-rates/timeseries-periods)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/market-data/rest-api/)[Next

Introduction](/market-data/rest-api/exchange-rates/coinapi-market-data-rest-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.