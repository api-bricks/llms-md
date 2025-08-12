Order Book | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/order-book/)

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
  + [Options](/market-data/rest-api/options/)
  + [Order Book](/market-data/rest-api/order-book/)

    - [Introduction](/market-data/rest-api/order-book/coinapi-market-data-rest-api)
    - [Current depth of the order book](/market-data/rest-api/order-book/current-depth-of-the-order-book)
    - [Get current order book](/market-data/rest-api/order-book/get-current-order-book)
    - [Historical data](/market-data/rest-api/order-book/historical-data)
    - [Latest data](/market-data/rest-api/order-book/latest-data)
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
* Order Book

Order Book
==========

This section describes calls related to order book data, also known as books or passive level 2 data.

info

When requesting current data for a specific symbol, output is not encapsulated into JSON array as only one item is returned.

info

GET `/v1/orderbooks/current` endpoint is charged one request per 100 data points returned after applying a filter defined by filter\_symbol\_id parameter. If filter symbols target more than one exchange, error is returned.

info

When requesting current order book data limited to a single level, then quotes are actually used. This information is important from the perspective that quotes data could be faster than order book data (behavior is dependent solely one the data source) and they can have the size equal to 0 when the size is unknown. Some data sources publish order books and separately quote data (without the sizes) at a higher frequency. In that case, we will merge the order book feed with quotes feed to make sure that our updates are as fast as possible. The quotes will have the size equal to 0 as the value is unknown and the customer can decide if these higher frequency updates without the sizes are valuable or if not then can discard them or ask for at least 2 order book levels (in case of a REST API call). For the data sources that publish order books only or order books and quotes with the sizes then this will not happen.

[📄️ Introduction
---------------](/market-data/rest-api/order-book/coinapi-market-data-rest-api)

[📄️ Current depth of the order book
----------------------------------

Retrieves the current depth of the order book for the specified symbol.](/market-data/rest-api/order-book/current-depth-of-the-order-book)

[📄️ Get current order book
-------------------------

Retrieves the current order book for the specified symbol.](/market-data/rest-api/order-book/get-current-order-book)

[📄️ Historical data
------------------

Get historical order book snapshots for a specific symbol within time range, returned in time ascending order.](/market-data/rest-api/order-book/historical-data)

[📄️ Latest data
--------------

Get latest order book snapshots for a specific symbol, returned in time descending order.](/market-data/rest-api/order-book/latest-data)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Current data by Exchange](/market-data/rest-api/options/current-data-by-exchange)[Next

Introduction](/market-data/rest-api/order-book/coinapi-market-data-rest-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.