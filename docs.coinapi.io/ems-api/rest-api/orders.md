Orders | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/rest-api/orders)

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

* [EMS API](/ems-api/)
* [Authentication](/ems-api/authentication)
* [API limits and billing](/ems-api/api-limits-and-billing-metrics)
* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)

  + [Introduction](/ems-api/rest-api/rest-api)
  + [Orders](/ems-api/rest-api/orders)

    - [Get open orders](/ems-api/rest-api/get-open-orders)
    - [Send new order](/ems-api/rest-api/send-new-order)
    - [Get order execution report](/ems-api/rest-api/get-order-execution-report)
    - [Cancel order request](/ems-api/rest-api/cancel-order-request)
    - [Cancel all orders request](/ems-api/rest-api/cancel-all-orders-request)
    - [History of order changes](/ems-api/rest-api/history-of-order-changes)
  + [Balances](/ems-api/rest-api/balances)
  + [Positions](/ems-api/rest-api/positions)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* Orders

Orders
======

Order statuses and the lifecycle are documented in the separate section: [EMS / Starter Guide / Order Lifecycle](#ems-order-lifecycle)

[📄️ Get open orders
------------------

Get last execution reports for open orders across all or single exchange.](/ems-api/rest-api/get-open-orders)

[📄️ Send new order
-----------------

This request creating new order for the specific exchange.](/ems-api/rest-api/send-new-order)

[📄️ Get order execution report
-----------------------------

Get the last order execution report for the specified order. The requested order does not need to be active or opened.](/ems-api/rest-api/get-order-execution-report)

[📄️ Cancel order request
-----------------------

Request cancel for an existing order. The order can be canceled using the `client\_order\_id` or `exchange\_order\_id`.](/ems-api/rest-api/cancel-order-request)

[📄️ Cancel all orders request
----------------------------

This request cancels all open orders on single specified exchange.](/ems-api/rest-api/cancel-all-orders-request)

[📄️ History of order changes
---------------------------

Based on the date range, all changes registered in the orderbook.](/ems-api/rest-api/history-of-order-changes)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/ems-api/rest-api/rest-api)[Next

Get open orders](/ems-api/rest-api/get-open-orders)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.