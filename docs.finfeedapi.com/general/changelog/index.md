Product Changelog | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* Product Changelog

On this page

Product Changelog
=================

This section will cover the technical changes to the products or documentation. The Changelog section is not just a record of changes; it's a communication tool that bridges the gap between developers and users, ensuring that the latter has a clear understanding of the product's evolution and current state.

It's a log of: `BREAKING CHANGES`, `FEATURES`, `IMPROVEMENTS`, `BUG FIXES`, `INTEGRATIONS`, or other `NOTES` per public version.

2025 June 22[​](/general/changelog/#2025-june-22 "Direct link to 2025 June 22")
-------------------------------------------------------------------------------

* **Stock API**: Added amaican Stock Exchange (XJAM) with supported market data.

2025 June 18[​](/general/changelog/#2025-june-18 "Direct link to 2025 June 18")
-------------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations "Direct link to INTEGRATIONS")

* **Stock API**: Added MOSCOW EXCHANGE - ALL MARKETS (MISX) with supported market data.
* **Stock API**: Added SIX SWISS EXCHANGE AG (XSWX) with supported market data.
* **Stock API**: Added HONG KONG EXCHANGES AND CLEARING LTD (XHKG) with supported market data.
* **Stock API**: Added TAIPEI EXCHANGE (ROCO) with supported market data.

2025 June 17[​](/general/changelog/#2025-june-17 "Direct link to 2025 June 17")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features "Direct link to FEATURES")

* **MCP**: Launched Model Context Protocol (MCP) support across all FinFeedAPI products:
  + Provides machine-readable JSON-Schema manifest describing every endpoint, parameters, and usage.
  + Enables out-of-the-box integration with AI chat models (LLMs) and autonomous agents.
  + Offers a single composite endpoint: `https://mcp.api.apibricks.io/mcp` for accessing all services.
  + Delivers schema-level validation, catching user errors early and improving reliability.
  + Auto-discovers new API routes and services, removing the need for client-side updates.
  + Maintains the existing authentication mechanism, ensuring a consistent developer experience.

2025 June 13[​](/general/changelog/#2025-june-13 "Direct link to 2025 June 13")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-1 "Direct link to FEATURES")

* **Console**: Added support for credits with expiration dates.

2025 June 10[​](/general/changelog/#2025-june-10 "Direct link to 2025 June 10")
-------------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements "Direct link to IMPROVEMENTS")

* **SEC API**: Added new tutorial "Tesla SEC XBRL Filing Data Analysis and Visualization" demonstrating the XBRL to JSON converter functionality. Available in our [GitHub repository](https://github.com/api-bricks/api-bricks-sdk/blob/master/finfeedapi/sec-api-rest/tutorials/Tesla_SEC_XBRL_Filing_Data_Analysis_and_Visualization.ipynb).

2025 June 6[​](/general/changelog/#2025-june-6 "Direct link to 2025 June 6")
----------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-2 "Direct link to FEATURES")

* **SEC API**: Added WebSocket API with Real-time Fillings Feed
* **SEC API**: Completed XBRL to JSON converter endpoint

##### IMPROVEMENTS[​](/general/changelog/#improvements-1 "Direct link to IMPROVEMENTS")

* **Stock API**: Now interpreting CFI Codes of symbols in REST API
* **SEC API**: Renamed "Historical SEC REST API" to "SEC REST API" in documentation to reflect real-time filing updates

##### INTEGRATIONS[​](/general/changelog/#integrations-1 "Direct link to INTEGRATIONS")

* **Stock API**: Added TAIWAN STOCK EXCHANGE (XTAI) with EOD OHLCV data availability T+1 since 2004

2025 June 5[​](/general/changelog/#2025-june-5 "Direct link to 2025 June 5")
----------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-2 "Direct link to IMPROVEMENTS")

* **Console**: Added a new credits summary section in the billing overview for better financial tracking.

2025 May 30[​](/general/changelog/#2025-may-30 "Direct link to 2025 May 30")
----------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-3 "Direct link to IMPROVEMENTS")

* **Console**: Expanded notification types to include:
  + Credits Added (free, auto recharged, or manually added)
  + Credits Auto Recharge Failed
  + Credits Low Balance
  + API Key First Authorization Failure

2025 May 29[​](/general/changelog/#2025-may-29 "Direct link to 2025 May 29")
----------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-3 "Direct link to FEATURES")

* **Console**: Enhanced notification system:
  + Users can customize which notifications they want to receive
  + Support for additional email recipients for non-billing and action required notifications
  + Integration capabilities with PagerDuty and Slack channels
  + New notifications history view

2025 May 28[​](/general/changelog/#2025-may-28 "Direct link to 2025 May 28")
----------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-2 "Direct link to INTEGRATIONS")

* **Stock API**: Added SIX SWISS EXCHANGE AG (XSWX) with EOD OHLCV data availability T+1 since 1997.

2025 May 22[​](/general/changelog/#2025-may-22 "Direct link to 2025 May 22")
----------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-3 "Direct link to INTEGRATIONS")

* **Stock API**: Added HONG KONG EXCHANGES AND CLEARING LTD (XHKG) with EOD OHLCV data availability T+1 since 2015.

2025 May 20[​](/general/changelog/#2025-may-20 "Direct link to 2025 May 20")
----------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-4 "Direct link to INTEGRATIONS")

* **Stock API**: Added WARSAW STOCK EXCHANGE/EQUITIES/MAIN MARKET (XWAR) with EOD OHLCV data availability T+1 since 1991.

2025 May 19[​](/general/changelog/#2025-may-19 "Direct link to 2025 May 19")
----------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-4 "Direct link to FEATURES")

* **SEC API**: Launched new SEC API product with:
  + Initial set of basic tutorials demonstrating API functionality
  + Documentation available at [docs.finfeedapi.com/sec-api](https://docs.finfeedapi.com/sec-api/)
  + Example code and tutorials in [GitHub repository](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi/sec-api-rest/tutorials)
  + More features and tutorial content planned for future releases

2025 May 15[​](/general/changelog/#2025-may-15 "Direct link to 2025 May 15")
----------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-5 "Direct link to INTEGRATIONS")

* **Stock API**: Added TAIPEI EXCHANGE (TPEX/ROCO) with EOD OHLCV data availability T+1 since 2007.

2025 May 14[​](/general/changelog/#2025-may-14 "Direct link to 2025 May 14")
----------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-4 "Direct link to IMPROVEMENTS")

* **Console**: Added Balance History view showing detailed historical balance changes and transactions.
* **SDK & OpenAPI**: Released new unified GitHub repository at [api-bricks/api-bricks-sdk](https://github.com/api-bricks/api-bricks-sdk) featuring:
  + Consolidated OpenAPI definitions for all product lines
  + Automated daily updates of OpenAPI definitions
  + Automatic SDK updates on OpenAPI changes
  + Automated package publishing to PyPI, NuGet, and other package managers
  + Legacy and manual SDK support maintained

2025 May 9[​](/general/changelog/#2025-may-9 "Direct link to 2025 May 9")
-------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-6 "Direct link to INTEGRATIONS")

* **Stock API**: Added SHANGHAI STOCK EXCHANGE (XSHG) with EOD OHLCV data availability T+1 since 1990.
* **Stock API**: Added SHENZHEN STOCK EXCHANGE (XSHE) with EOD OHLCV data availability T+1 since 1999.

##### IMPROVEMENTS[​](/general/changelog/#improvements-5 "Direct link to IMPROVEMENTS")

* **Console & API**: Introduced Fractional Billing for Metered Usage.
* **Console & API**: Enhanced billing logic - customers are not invoiced until becoming Paying Customers after using free credits.
* **Console**: Added new Metered Usage views:
  + Daily History
  + Monthly Statement
  + Uninvoiced Currently
* **Console**: Replaced Tax Settings with Tax Registrations in the Invoice Address section.
* **Console**: Enhanced auto recharge feature:
  + Prioritizes last successful payment method
  + Added support for Direct Debits from bank accounts

2025 April 18[​](/general/changelog/#2025-april-18 "Direct link to 2025 April 18")
----------------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-7 "Direct link to INTEGRATIONS")

* **Stock API**: Expanded End-of-Day integrations by adding the following exchanges: EURONEXT BRUSSELS (ALXB, MLXB, VPXB, XBRU), EURONEXT LISBON – SOCIEDADE GESTORA DE MERCADOS REGULAMENTADOS S.A. (ALXL, ENXL, XLIS), EURONEXT GROUP (ALXP), BORSA ITALIANA S.P.A. (ATFX, BGEM, ETFP, ETLX, EXGM, MIVX, MTAA, MTAH), OSLO BØRS ASA (MERK, XOAS, XOSL), EURONEXT GROWTH DUBLIN (XESM), EURONEXT – EURONEXT AMSTERDAM (XAMS), EURONEXT DUBLIN (XMSM), and EURONEXT PARIS SA (XPAR, XMLI). Data is available for Stocks, Bonds, Funds, and ETFs via the Stock API using the `asset_class` and `symbol_category` fields.

##### FEATURES[​](/general/changelog/#features-5 "Direct link to FEATURES")

* **Stock API**: Added time-aggregated OHLCV endpoints for historical data. See [Historical data](https://docs.finfeedapi.com/stock-api/rest-api-historical/historical-data).

2025 March 28[​](/general/changelog/#2025-march-28 "Direct link to 2025 March 28")
----------------------------------------------------------------------------------

##### BREAKING CHANGES[​](/general/changelog/#breaking-changes "Direct link to BREAKING CHANGES")

* **Stock Histrical API**: Initial API product release. Endpoints: Metadata.
* **Stock Histrical API**: Added Native Exchange API for IEX Exchange covering Level 1 & 2 & 3, Trades, Admin and System Messages.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

MCP Servers](/general/mcp-servers)[Next

Product Roadmap](/general/roadmap)

* [2025 June 22](/general/changelog/#2025-june-22)
* [2025 June 18](/general/changelog/#2025-june-18)
* [2025 June 17](/general/changelog/#2025-june-17)
* [2025 June 13](/general/changelog/#2025-june-13)
* [2025 June 10](/general/changelog/#2025-june-10)
* [2025 June 6](/general/changelog/#2025-june-6)
* [2025 June 5](/general/changelog/#2025-june-5)
* [2025 May 30](/general/changelog/#2025-may-30)
* [2025 May 29](/general/changelog/#2025-may-29)
* [2025 May 28](/general/changelog/#2025-may-28)
* [2025 May 22](/general/changelog/#2025-may-22)
* [2025 May 20](/general/changelog/#2025-may-20)
* [2025 May 19](/general/changelog/#2025-may-19)
* [2025 May 15](/general/changelog/#2025-may-15)
* [2025 May 14](/general/changelog/#2025-may-14)
* [2025 May 9](/general/changelog/#2025-may-9)
* [2025 April 18](/general/changelog/#2025-april-18)
* [2025 March 28](/general/changelog/#2025-march-28)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.