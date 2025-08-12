Exchange Rates | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Currencies API](/currencies-api/)
* [Authentication](/currencies-api/authentication)
* [Metadata Tables](/currencies-api/metadata-tables/introduction)
* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)

  + [Introduction](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
  + [Exchange Rates](/currencies-api/rest-api-realtime/exchange-rates)

    - [Get specific rate](/currencies-api/rest-api-realtime/get-specific-rate)
    - [Get all current rates](/currencies-api/rest-api-realtime/get-all-current-rates)
  + [Metadata](/currencies-api/rest-api-realtime/metadata)
* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
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

[📄️ Get specific rate
--------------------

Retrieves the exchange rate for a specific base and quote asset at a given time or the current rate.](/currencies-api/rest-api-realtime/get-specific-rate)

[📄️ Get all current rates
------------------------

Get the current exchange rate between requested asset and all other assets.](/currencies-api/rest-api-realtime/get-all-current-rates)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/currencies-api/rest-api-realtime/fx-realtime-rest-api)[Next

Get specific rate](/currencies-api/rest-api-realtime/get-specific-rate)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.