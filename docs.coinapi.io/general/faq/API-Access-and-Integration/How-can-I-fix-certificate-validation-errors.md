How can I fix certificate validation errors when connecting to CoinAPI? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/API-Access-and-Integration/How-can-I-fix-certificate-validation-errors)

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
* How can I fix certificate validation errors when connecting to CoinAPI?

How can I fix certificate validation errors when connecting to CoinAPI?
=======================================================================

Certificate validation errors typically occur when your system lacks updated CA (Certificate Authority) certificates. Here’s how to resolve it based on your operating system:

On Windows:

* Ensure your Windows Updates are fully installed, as CA certificates are updated through the standard update process.

On Ubuntu/Debian Linux:

* Run the following command to refresh your certificate store:

  ```
  sudo update-ca-certificates
  ```

Alternative Option:

If updating certificates isn't feasible, you may connect via an unencrypted HTTP endpoint—though this is not recommended for production due to security concerns.

For production environments, we recommend using HTTPS with properly updated CA bundles.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Can using a VPN affect my connection to CoinAPI?](/general/faq/API-Access-and-Integration/Can-using-a-VPN-affect-my-connection-to-CoinAPI)[Next

How can I troubleshoot FIX API logon issues with CoinAPI?](/general/faq/API-Access-and-Integration/How-can-I-troubleshoot-FIX-API-logon-issues-with-CoinAPI)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.