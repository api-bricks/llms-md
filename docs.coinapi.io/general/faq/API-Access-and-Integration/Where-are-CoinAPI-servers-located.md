Where are CoinAPI’s servers located, and how does latency vary by region? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/API-Access-and-Integration/Where-are-CoinAPI-servers-located)

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
  + [Billing, Payment, and Subscriptions](/general/faq/Billing-Payment-and-Subscriptions/)
  + [Account Management](/general/faq/Account-Management/)
  + [Security and Privacy](/general/faq/Security-and-Privacy/)
  + [API Access & Integration](/general/faq/API-Access-and-Integration/)

    - [Can using a VPN affect my connection to CoinAPI?](/general/faq/API-Access-and-Integration/Can-using-a-VPN-affect-my-connection-to-CoinAPI)
    - [How can I fix certificate validation errors when connecting to CoinAPI?](/general/faq/API-Access-and-Integration/How-can-I-fix-certificate-validation-errors)
    - [How can I troubleshoot FIX API logon issues with CoinAPI?](/general/faq/API-Access-and-Integration/How-can-I-troubleshoot-FIX-API-logon-issues-with-CoinAPI)
    - [How can I use CoinAPI from MATLAB?](/general/faq/API-Access-and-Integration/How-can-I-use-CoinAPI-from-MATLAB)
    - [How do I generate an API key for FIX API access?](/general/faq/API-Access-and-Integration/How-do-I-generate-an-API-key-for-FIX-API)
    - [How do I troubleshoot API errors?](/general/faq/API-Access-and-Integration/How-do-I-troubleshoot-API-errors)
    - [How does CoinAPI calculate cryptocurrency exchange rates?](/general/faq/API-Access-and-Integration/How-does-CoinAPI-calculate-cryptocurrency-exchange-rates)
    - [How should I document and troubleshoot CoinAPI connectivity issues?](/general/faq/API-Access-and-Integration/How-should-I-document-and-troubleshoot-CoinAPI-connectivity-issues)
    - [What programming languages are supported by CoinAPI?](/general/faq/API-Access-and-Integration/What-programming-languages-are-supported-by-CoinAPI)
    - [What timezone does CoinAPI use for date and time values?](/general/faq/API-Access-and-Integration/What-timezone-does-CoinAPI-use-for-date-and-time)
    - [Where are CoinAPI’s servers located, and how does latency vary by region?](/general/faq/API-Access-and-Integration/Where-are-CoinAPI-servers-located)
    - [Where can I find API examples and SDK source code for CoinAPI?](/general/faq/API-Access-and-Integration/Where-can-I-find-API-examples-and-SDK-source-code)
    - [Why am I getting an "Invalid API Key" error after generating a new key?](/general/faq/API-Access-and-Integration/Why-am-I-getting-an-invalid-API-Key-error-after-generating-a-new-key)
    - [Why does my WebSocket connection keep disconnecting with code 1006 and no reason?](/general/faq/API-Access-and-Integration/Why-does-my-WebSocket-connection-keep-disconnecting-with-code-1006-and-no-reason)
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
* [API Access & Integration](/general/faq/API-Access-and-Integration/)
* Where are CoinAPI’s servers located, and how does latency vary by region?

Where are CoinAPI’s servers located, and how does latency vary by region?
=========================================================================

CoinAPI operates a globally distributed infrastructure with low-latency data centers in the following locations:

* AWS Regions: `us-east-1`, `eu-central-1`, `eu-west-1`
* Colocated Sites:
  + USA: Chicago, New York
  + UK: London
  + Poland: Warsaw
  + Asia: Tokyo

Latency Behavior:

* Real-time data (via REST `/current`, WebSocket, FIX) is delivered from the site you’re connected to, routed using GeoDNS to the closest available server.
* Average latency for public endpoints is ~20ms.
* On Enterprise Plans, customers can achieve sub-1ms latency using direct connections or AWS VPC Peering.

Historical data (via REST `/history` and Flat Files) is consolidated across all regions to produce a single, globally consistent dataset. This reduces geographic discrepancies but can be impacted by replay process constraints.

Learn more about optimizing connectivity or request direct site access by contacting our [Support Team](https://support.coinapi.io/hc/en-us/requests/new).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

What timezone does CoinAPI use for date and time values?](/general/faq/API-Access-and-Integration/What-timezone-does-CoinAPI-use-for-date-and-time)[Next

Where can I find API examples and SDK source code for CoinAPI?](/general/faq/API-Access-and-Integration/Where-can-I-find-API-examples-and-SDK-source-code)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.