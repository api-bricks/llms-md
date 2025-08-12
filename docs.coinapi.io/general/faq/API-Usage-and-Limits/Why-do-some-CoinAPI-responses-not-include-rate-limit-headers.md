Why do some CoinAPI responses not include rate limit headers? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/API-Usage-and-Limits/Why-do-some-CoinAPI-responses-not-include-rate-limit-headers)

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
* Why do some CoinAPI responses not include rate limit headers?

Why do some CoinAPI responses not include rate limit headers?
=============================================================

The reason why response headers are not always present in the API responses is that, in some cases, we are unaware of their specific usage or requirements. To ensure that we promptly respond to your API calls and avoid unnecessary delays, we choose to provide a response without including the response headers. This decision is made with the intention of optimizing the operation of our API. By selectively excluding the inclusion of response headers in every request, we can enhance the overall performance and efficiency of the API.

It takes a while to verify the current usage as for the very first call for a given client we do not have a rate limit then yet.
Once the request is made, we start the rate limit verification process In the background. We may then in the meantime process many requests for this client and at some point we append the result of current usage to the header.
All requests that were made during that process are also included in the limit after some time.

For example (each bullet point representing a request made):

* Request (no info about clients usage)
* What's the usage? Starting the verification
* Request
* Request
* 5 requests used today (those 3 above are not counted yet), appended to the header
* Request (5 used)
* Request (5 used)
* Request (5 used)
* Request (5 used)
* Request (10 requests used today)

To provide clarity and transparency regarding the absence of response headers, we have documented this behavior on our official documentation page, which can be found at <https://docs.coinapi.io/market-data/rest-api#request-limit--apikey>

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

What happens if I exceed my daily REST API request limit on my CoinAPI plan?](/general/faq/API-Usage-and-Limits/What-happens-if-I-exceed-my-daily-REST-API-request-limit)[Next

Why does using limit=1 still count as 1 full request in my API usage? Isn't pricing based on 100 data points?](/general/faq/API-Usage-and-Limits/Why-does-using-limit-1-still-count-as-1-full-request)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.