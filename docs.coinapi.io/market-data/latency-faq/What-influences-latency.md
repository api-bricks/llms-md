What influences latency between a client and an exchange/provider, and how can it be minimized? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/latency-faq/What-influences-latency)

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
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)

  + [Introduction](/market-data/latency-faq/)
  + [What influences latency between a client and an exchange/provider, and how can it be minimized?](/market-data/latency-faq/What-influences-latency)
  + [How to reduce latency for your Market Data API?](/market-data/latency-faq/how-to-reduce-market-data-apis-latency)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [Latency FAQ](/market-data/latency-faq/)
* What influences latency between a client and an exchange/provider, and how can it be minimized?

What influences latency between a client and an exchange/provider, and how can it be minimized?
===============================================================================================

Latency depends not only on the provider and exchange but also on the customer’s infrastructure. For example, achieving latency below 100ms between London and Binance may require additional data centers or optimized configurations. The direct path from London to Binance is approximately 250ms. To achieve sub-100ms latency end-to-end, additional infrastructure and strategic server placement on the customer’s side are essential. Additionally, some matching engines are inherently located more than 100ms away, which requires careful planning to address such challenges.

[How to reduce latency for your Market Data API?](https://docs.coinapi.io/market-data/latency-faq/how-to-reduce-market-data-apis-latency)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/market-data/latency-faq/)[Next

How to reduce latency for your Market Data API?](/market-data/latency-faq/how-to-reduce-market-data-apis-latency)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.