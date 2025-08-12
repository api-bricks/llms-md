How do I calculate the number of requests I’ll be making for a specific query? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/API-Usage-and-Limits/How-do-I-calculate-the-number-of-requests)

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

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [FAQ](/general/faq/)

  + [General](/general/faq/general/)
  + [API Usage and Limits](/general/faq/API-Usage-and-Limits/)

    - [API Usage Limits](/general/faq/API-Usage-and-Limits/API-Usage-Limits)
    - [How can I check my historical API usage with CoinAPI?](/general/faq/API-Usage-and-Limits/How-can-I-check-my-historical-API-usage-with-CoinAPI)
    - [How can I retrieve more than 100 items in a single API response?](/general/faq/API-Usage-and-Limits/How-can-I-retrieve-more-than-100-items)
    - [How do I calculate the number of requests I’ll be making for a specific query?](/general/faq/API-Usage-and-Limits/How-do-I-calculate-the-number-of-requests)
    - [How do I enable overage?](/general/faq/API-Usage-and-Limits/How-do-I-enable-overage)
    - [How does CoinAPI’s credit system work? Do I need to preload credits, and how fast are charges reflected?](/general/faq/API-Usage-and-Limits/How-does-CoinAPI-credit-system-work)
    - [What happens if I exceed my daily REST API request limit on my CoinAPI plan?](/general/faq/API-Usage-and-Limits/What-happens-if-I-exceed-my-daily-REST-API-request-limit)
    - [Why do some CoinAPI responses not include rate limit headers?](/general/faq/API-Usage-and-Limits/Why-do-some-CoinAPI-responses-not-include-rate-limit-headers)
    - [Why does using limit=1 still count as 1 full request in my API usage? Isn't pricing based on 100 data points?](/general/faq/API-Usage-and-Limits/Why-does-using-limit-1-still-count-as-1-full-request)
    - [I barely use the REST API. Why is my usage still so high?](/general/faq/API-Usage-and-Limits/Why-is-my-usage-so-high)
  + [Billing, Payment, and Subscriptions](/general/faq/Billing-Payment-and-Subscriptions/)
  + [Account Management](/general/faq/Account-Management/)
  + [Security and Privacy](/general/faq/Security-and-Privacy/)
  + [API Access & Integration](/general/faq/API-Access-and-Integration/)
  + [Market Data API](/general/faq/Market-Data-API/)
  + [EMS Trading API](/general/faq/EMS-Trading-API/)
  + [Indexes API](/general/faq/Indexes-API/)
  + [Flat Files API](/general/faq/Flat-Files-API/)
  + [Exchange Rates API](/general/faq/Exchange-Rates-API/)
  + [Node as a Service](/general/faq/Node-as-a-Service/)
  + [Enterprise Plan](/general/faq/Enterprise-Plan/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [FAQ](/general/faq/)
* [API Usage and Limits](/general/faq/API-Usage-and-Limits/)
* How do I calculate the number of requests I’ll be making for a specific query?

How do I calculate the number of requests I’ll be making for a specific query?
==============================================================================

CoinAPI uses a credit-based system for REST API requests. The number of request credits consumed depends on how many data items you retrieve in a single call.

How it works:

* If you do not use the `limit` parameter, the default is `limit=100`, which counts as 1 request
* If you do use the `limit` parameter, every 100 data items returned counts as 1 request

Example:

```
GET /v1/ohlcv/BINANCE_SPOT_BTC_USDT/history?limit=1500
```

This call returns 1,500 items, which counts as:

```
1500 ÷ 100 = 15 requests
```

Additional tips:

* `limit` minimum: 1
* `limit` maximum: 100,000

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

How can I retrieve more than 100 items in a single API response?](/general/faq/API-Usage-and-Limits/How-can-I-retrieve-more-than-100-items)[Next

How do I enable overage?](/general/faq/API-Usage-and-Limits/How-do-I-enable-overage)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.