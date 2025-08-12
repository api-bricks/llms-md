Why does using limit=1 still count as 1 full request in my API usage? Isn't pricing based on 100 data points? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/API-Usage-and-Limits/Why-does-using-limit-1-still-count-as-1-full-request)

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
* Why does using limit=1 still count as 1 full request in my API usage? Isn't pricing based on 100 data points?

Why does using limit=1 still count as 1 full request in my API usage? Isn't pricing based on 100 data points?
=============================================================================================================

Yes, CoinAPI uses a credit-based model, but here's how the request-based billing works with the `limit` parameter:

How Credit Consumption Works:

* Each successful API request counts as at least 1 request.
* If your request includes the `limit` parameter:
  + Every 100 data points = 1 credit (rounded up).
  + Example: `limit=200` = 2 credits, `limit=1` = still 1 credit.

Even if you only request 1 data point (`limit=1`), it still triggers a full request and uses 1 credit, because that's the minimum unit for billing.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Why do some CoinAPI responses not include rate limit headers?](/general/faq/API-Usage-and-Limits/Why-do-some-CoinAPI-responses-not-include-rate-limit-headers)[Next

I barely use the REST API. Why is my usage still so high?](/general/faq/API-Usage-and-Limits/Why-is-my-usage-so-high)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.