Product Changelog | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/changelog/)

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
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* Product Changelog

On this page

Product Changelog
=================

This section will cover the technical changes to the products or documentation. The Changelog section is not just a record of changes; it's a communication tool that bridges the gap between developers and users, ensuring that the latter has a clear understanding of the product's evolution and current state.

It's a log of: `BREAKING CHANGES`, `FEATURES`, `IMPROVEMENTS`, `BUG FIXES`, `INTEGRATIONS`, or other `NOTES` per public version.

2025 July 30[​](/general/changelog/#2025-july-30 "Direct link to 2025 July 30")
-------------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements "Direct link to IMPROVEMENTS")

* **Market Data API**: Significantly reduced latency and improved real-time accuracy of OHLCV aggregated data.
  + Closed candles are now finalized within approximately 10 seconds of the period ending (down from up to 3 minutes).
  + In-progress candles refresh every 1-3 seconds on highly-liquid markets, providing fresher data for trading bots and back-testing.
  + Enhancement applies to all periods (1SEC-1Y) and major exchanges, e.g., Binance, Coinbase.
* **Market Data API**: Added POWERTRADE integration.

2025 June 29[​](/general/changelog/#2025-june-29 "Direct link to 2025 June 29")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features "Direct link to FEATURES")

* **Market Data API**: Our OHLCV Market Data now can include midpoint from best prices on the both sides of the book `midpoint = ((ask + bid) / 2)` this mean that there will be elements with `trades_count = 0 and volume_traded = 0` when in period there was no transactions, but there are changes in the order book resting best prices.

2025 June 26[​](/general/changelog/#2025-june-26 "Direct link to 2025 June 26")
-------------------------------------------------------------------------------

##### BREAKING CHANGES[​](/general/changelog/#breaking-changes "Direct link to BREAKING CHANGES")

* **Market Data API REST API**: `/v1/symbols` now lists only active symbols for faster responses; all symbols, including inactive ones, are still accessible via `/v1/symbols/{exchange_id}/history`.

##### IMPROVEMENTS[​](/general/changelog/#improvements-1 "Direct link to IMPROVEMENTS")

* **Infrastructure**: Overall infrastructure stability and performance improvements.

2025 June 18[​](/general/changelog/#2025-june-18 "Direct link to 2025 June 18")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-1 "Direct link to FEATURES")

* **Market Data API**: Released version 2 API of the Metrics API. The V2 API contains all the metrics from the V1 API which is now in the deprecated state plus additional metrics like:
  + Minted stablecoins
  + Stablecoins circulating supply, unreleased supply, minted supply
  + Stablecoins bridged to other chains
  + Total Value Locked per protocol
  + Fees per protocol
  + Onchain trading volumes
* **Market Data API**: Extended our Market Data API by /v1/chains endpoint.

##### NOTES[​](/general/changelog/#notes "Direct link to NOTES")

* **Metrics API V1**: The V1 API is now in deprecated state. [Documentation for V2 API](https://docs.coinapi.io/market-data/rest-api/metricsv2/)

2025 June 17[​](/general/changelog/#2025-june-17 "Direct link to 2025 June 17")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-2 "Direct link to FEATURES")

* **Model Context Protocol (MCP)**: Officially launched MCP support across CoinAPI products:
  + Easy integration with AI chat models (LLMs) and autonomous agents
  + Single composite MCP endpoint at `https://mcp.api.apibricks.io/mcp` for all services
  + Machine-readable JSON-Schema format that describes API endpoints, parameters, and usage
  + Schema-level validation for more robust integrations
  + Auto-discovery of new API routes and services without requiring client-side updates
  + Unified authentication and consistent developer experience across all APIs
  + Future-proof architecture ensuring seamless integration with new services

2025 June 13[​](/general/changelog/#2025-june-13 "Direct link to 2025 June 13")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-3 "Direct link to FEATURES")

* **Console**: Added support for credits with expiration dates.

2025 May 30[​](/general/changelog/#2025-may-30 "Direct link to 2025 May 30")
----------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-2 "Direct link to IMPROVEMENTS")

* **Console**: Expanded notification types to include:
  + Credits Added (free, auto recharged, or manually added)
  + Credits Auto Recharge Failed
  + Credits Low Balance
  + API Key First Authorization Failure

2025 May 29[​](/general/changelog/#2025-may-29 "Direct link to 2025 May 29")
----------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-4 "Direct link to FEATURES")

* **Console**: Enhanced notification system:
  + Users can customize which notifications they want to receive
  + Support for additional email recipients for non-billing and action required notifications
  + Integration capabilities with PagerDuty and Slack channels
  + New notifications history view

2025 May 21[​](/general/changelog/#2025-may-21 "Direct link to 2025 May 21")
----------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations "Direct link to INTEGRATIONS")

* **Market Data API**: Added ASTERFINANCE integration.
* **Market Data API**: Added EXTENDED integration.

2025 May 14[​](/general/changelog/#2025-may-14 "Direct link to 2025 May 14")
----------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-3 "Direct link to IMPROVEMENTS")

* **Console**: Added Balance History view showing detailed historical balance changes and transactions.
* **SDK & OpenAPI**: Released new unified GitHub repository at [api-bricks/api-bricks-sdk](https://github.com/api-bricks/api-bricks-sdk) featuring:
  + Consolidated OpenAPI definitions for all product lines
  + Automated daily updates of OpenAPI definitions
  + Automatic SDK updates on OpenAPI changes
  + Automated package publishing to PyPI, NuGet, and other package managers
  + Legacy and manual SDK support maintained

2025 May 9[​](/general/changelog/#2025-may-9 "Direct link to 2025 May 9")
-------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-4 "Direct link to IMPROVEMENTS")

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

2025 April 01[​](/general/changelog/#2025-april-01 "Direct link to 2025 April 01")
----------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-5 "Direct link to FEATURES")

* **Console**: Migrated Traces for Requests, Traces for Connections, Usage metrics, Support tickets, and Quotas and Limits from the Customer Portal to the Console. The Console is now the default place for customers.

##### IMPROVEMENTS[​](/general/changelog/#improvements-5 "Direct link to IMPROVEMENTS")

* **Console**: Improved Request and Connection Traces to display information in a more user-friendly way.
* **Indexes API**: Shortened the number of PRIMKT indexes as they were too wide.
* **Market Data API**: Reduced latency for all exchanges.
* **Market Data API**: Made major improvements in historical data processing.
* **Market Data API**: Completed OHLCV and quotes backfill for multiple exchanges.
* **Exchange Rates API**: Stability improvements.

##### INTEGRATIONS[​](/general/changelog/#integrations-1 "Direct link to INTEGRATIONS")

* **Market Data API**: Added VERTEX integration (as of 2025-04-08).
* **Market Data API**: Added PARADEX integration (as of 2025-04-09).
* **Market Data API**: Added ORDERLYNETWORK integration (as of 2025-04-23).
* **Market Data API**: Added TOOBIT integration (as of 2025-04-23).
* **Market Data API**: Added WEEX integration (as of 2025-04-23).
* **Market Data API**: Added FAMEEX (SPOT) integration (as of 2025-04-25).
* **Market Data API**: Added FAMEEXFTS integration (as of 2025-04-25).
* **Market Data API**: Added TAPBIT integration (as of 2025-04-25).
* **Market Data API**: Added TAPBITFTS integration (as of 2025-04-25).

##### NOTES[​](/general/changelog/#notes-1 "Direct link to NOTES")

* **Console**: The old customer portal has been disabled. We are continuously working on improving the Console.

##### BUG FIXES[​](/general/changelog/#bug-fixes "Direct link to BUG FIXES")

* **Exchange Rates API**: Resolved various issues.

2025 March 01[​](/general/changelog/#2025-march-01 "Direct link to 2025 March 01")
----------------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-2 "Direct link to INTEGRATIONS")

* **Market Data API**: Added BINANCEOPT integration.
* **Market Data API**: Added DRIFT integration.
* **Market Data API**: Added DEEPCOINFTS integration.
* **Market Data API**: Added ORANGEX integration.
* **Market Data API**: Added ORANGEXFTS integration.
* **Market Data API**: Added COINCALL SPOT integration.
* **Market Data API**: Added COINCALLFTS integration.
* **Market Data API**: Added COINCALLOPT integration.
* **Market Data API**: Added HOTCOIN integration.
* **Market Data API**: Added HOTCOINFTS integration.
* **Market Data API**: Added GRVT integration.

##### IMPROVEMENTS[​](/general/changelog/#improvements-6 "Direct link to IMPROVEMENTS")

* **Market Data API**: Reduced latency standard deviation and implemented general network improvements for the `WebSocket API` and `FIX API`.
* **Exchange Rates API**: Expanded asset coverage to include more fiat FX pairs and commodities such as gold (XAU) and silver (XAG).
* **Exchange Rates API**: Extended the historical data availability for high-frequency (100ms interval) FX data back to 2012.

2025 February 01[​](/general/changelog/#2025-february-01 "Direct link to 2025 February 01")
-------------------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-6 "Direct link to FEATURES")

* **Indexes API**: Added possibility to preview changes to the Index Components.
* **Console**: We relesed new console that will in the future replace old customer portal.
* **Console**: In new Console there is possibility to generate API Keys that are not limited to single product.

##### INTEGRATIONS[​](/general/changelog/#integrations-3 "Direct link to INTEGRATIONS")

* **Market Data API** **Flat Files API**: Added LMAXDIGITAL Premium Data Source feed.
* **Market Data API**: DERIBIT integration improvements.
* **Market Data API**: DRIFT integrated using WebSocket API.
* **Market Data API**: BACKPACK integration PERPETUAL symbols covered.
* **Market Data API**: BITRUE rewrited on WebSocket API.
* **Market Data API**: UPBIT integration over WebSocket API.
* **Market Data API**: WHITEBIT integration over WebSocket API.
* **Market Data API**: BINANCE integration improvements.
* **Market Data API**: PHEMEX integration improvements.
* **Market Data API**: HUOBI related integrations improved.

##### IMPROVEMENTS[​](/general/changelog/#improvements-7 "Direct link to IMPROVEMENTS")

* **Indexes API** **Market Data API** **Exchange Rates API**: Data quality and coverage improvements.

##### BUG FIXES[​](/general/changelog/#bug-fixes-1 "Direct link to BUG FIXES")

* **Market Data WS DS API**: Some individual integrations were not available via the WS DS API.

2025 January 01[​](/general/changelog/#2025-january-01 "Direct link to 2025 January 01")
----------------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-7 "Direct link to FEATURES")

* **Exchange Rates API**: Released new Exchange Rates API as fork from the Market Data API. REST and WebSocket API protocols with real-time and historical data and assets.

##### INTEGRATIONS[​](/general/changelog/#integrations-4 "Direct link to INTEGRATIONS")

* **Market Data API** **Flat Files API**: Improved the BYBIT integrations. BYBITUSDC virtual exchange was discontinued, the symbols were moved to the BYBIT exchange to align the identifiers better with the exchange API.
* **Market Data API** **Flat Files API**: Resolved the issue with the KUCOIN integration.

##### IMPROVEMENTS[​](/general/changelog/#improvements-8 "Direct link to IMPROVEMENTS")

* **Market Data API**: Various documentation improvements.
* **Flat Files API**: Added cost estimation source code for reference.
* **Market Data API** **Indexes API**: Improved the performance and availability of the Exchange Rates and Indexes, deployed another location in the NCSA region for availability.
* **Documentation**: Migrated Metadata Explorer from the website to the documentation.
* **Market Data REST API**: Improved the response time performance of the Exchange Rate Historical endpoint for all assets at specific timestamp.
* **Market Data API** **Indexes API**: Improved the stability and performance of the data calculation.

##### BUG FIXES[​](/general/changelog/#bug-fixes-2 "Direct link to BUG FIXES")

* **Market Data API** **Flat Files API**: Limit parameter is correctly ignored when accesing historical quotes, trades and orderbooks while querying by the `date` parameter.
* **Market Data API**: Fixed the corner-case with the time value on the weekend and monday while querying for the real-time crosses using crypto and the fiat's for which markets are closed on the weekend.

##### BREAKING CHANGES[​](/general/changelog/#breaking-changes-1 "Direct link to BREAKING CHANGES")

* **Indexes API**: WebSocket API do not provide the `sequence` field in the messages as data is delivered only via the TCP which guarantees the order of the messages and provides the sequence number (on the deeper level).

2024 December 01[​](/general/changelog/#2024-december-01 "Direct link to 2024 December 01")
-------------------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-8 "Direct link to FEATURES")

* **Market Data API**: Options Market State endpoint providing now underlying\_price field.
* **Index API**: Released IDX\_VOL\_CAPIVIX index family, our first volatility indexes measuring 30-day implied volatility based on options markets. Currently available for two pairs:
  + IDX\_VOL\_CAPIVIX\_BTC\_USD
  + IDX\_VOL\_CAPIVIX\_ETH\_USD

##### IMPROVEMENTS[​](/general/changelog/#improvements-9 "Direct link to IMPROVEMENTS")

* **Market Data API** **Flat Files API**: Performance, lantecy and stability improvements.
* **Market Data API** **Flat Files API**: Updated the symbol mapping procedures to resolve various corner-cases, improved the CoinAPI symbol identifiers. We are now using scientific notation for the OPTION symbols in the Strike Price field.
* **Flat Files API**: Improved prefix handling in the ListObjects response.

##### BUG FIXES[​](/general/changelog/#bug-fixes-3 "Direct link to BUG FIXES")

* **Flat Files API**: Fixed issues related to 'Last-Modified' error or BAD\_REQUEST responses when using multipart downloads.

2024 November 01[​](/general/changelog/#2024-november-01 "Direct link to 2024 November 01")
-------------------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-9 "Direct link to FEATURES")

* **Market Data API**: Added new Options Market State endpoint providing comprehensive options data:
  + Displays current option prices grouped by underlying asset and expiration dates
  + Shows strike prices with associated bid/ask prices and volumes
  + Includes last trade details (price, size, and aggressor direction)
  + Provides both exchange and CoinAPI timestamps
  + Designed for easy integration with dashboards and analytics applications

##### IMPROVEMENTS[​](/general/changelog/#improvements-10 "Direct link to IMPROVEMENTS")

* **Market Data API**: Added regional endpoints and unencrypted options for all API types:
  + REST API: Added NCSA, EMEA, and APAC regional endpoints, each available via HTTP and HTTPS
  + WebSocket API: Added NCSA, EMEA, and APAC regional endpoints, each available via WS and WSS
  + FIX API: Added NCSA, EMEA, and APAC regional endpoints, each available on ports 3302 (unencrypted) and 3303 (encrypted)
  + All endpoints maintain GeoDNS auto-routing option through the default domains
* **WebSocket API**: Performance enhancements:
  + Better stability during high market activity
  + Improved long-term connection reliability
* **Market Data API**: Platform improvements:
  + Faster response times across all endpoints
  + More reliable real-time data delivery
* **Service Level Agreement (SLA)**: SLA Target changed from 99% to 99.9%

##### INTEGRATIONS[​](/general/changelog/#integrations-5 "Direct link to INTEGRATIONS")

* **Market Data API**: Integrated several new exchanges to expand our market coverage:
  + BACKPACK exchange integration completed
  + HYPERLIQUID exchange integration
  + COINW exchange integration
  + BITMARTFTS exchange integration

2024 October 01[​](/general/changelog/#2024-october-01 "Direct link to 2024 October 01")
----------------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-10 "Direct link to FEATURES")

* **Customer Portal**: Released a new Spend Management feature, giving users greater control over their credit usage:
  + Daily credit consumption tracking
  + Customizable daily credit usage budget
  + Email notifications for threshold alerts
  + Webhook integration for real-time usage updates
  + Automated enforcement of budget limits

##### IMPROVEMENTS[​](/general/changelog/#improvements-11 "Direct link to IMPROVEMENTS")

* **Market Data API**: Significant enhancements to our Exchange Rates service:
  + Increased frequency of exchange rate updates from 1 second to 100 milliseconds, providing more real-time data.
  + Extended coverage to include all FX rates, offering a comprehensive view of the forex market.
  + Improved quality of rates for corner-cases through algorithm adjustments, ensuring more accurate data in unusual market conditions.

##### INTEGRATIONS[​](/general/changelog/#integrations-6 "Direct link to INTEGRATIONS")

* **Market Data API**: Integrated the Hyperliquid exchange, expanding our coverage of decentralized perpetual futures trading platforms.

##### FEATURES[​](/general/changelog/#features-11 "Direct link to FEATURES")

* **Indexes API**: Introduced FX Reference Rates Index, published every 100 milliseconds, providing high-frequency benchmark data for forex markets.

##### BUG FIXES[​](/general/changelog/#bug-fixes-4 "Direct link to BUG FIXES")

* **Documentation**: Resolved an issue in the documentation UI where users occasionally couldn't set up an API key for requests.
* **Customer Portal**: Fixed a bug where users with free API keys were unable to use the "Manage Subscriptions" button.

2024 September 01[​](/general/changelog/#2024-september-01 "Direct link to 2024 September 01")
----------------------------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-12 "Direct link to IMPROVEMENTS")

* **Market Data API**: Improvements in the performance of the history endpoints OHLCV, Exchange Rates and Historical Metrics.
* **Documentation**: Added a new article explaining how usage credits work, providing clarity on our billing system.

##### FEATURES[​](/general/changelog/#features-12 "Direct link to FEATURES")

* **Indexes API**: We have added the Indexes API to our product portfolio, providing comprehensive market data aggregation from multiple sources for a broad overview of market conditions.

2024 August 01[​](/general/changelog/#2024-august-01 "Direct link to 2024 August 01")
-------------------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-13 "Direct link to IMPROVEMENTS")

* **Customer Portal**: We added the Traces for Connections in the customer portal. This will help us gather more information about the usage and enable identification of the possible issues faster. This is currently available for Market Data WS and FIX API in EMEA and APAC, and will be expanded.
* **Customer Portal**: We added an Audit Trial feature (you can find it in left-side menu) where any organization member can inspect what changes were applied by other user inside in the organization account.
* **Status Page**: We have a new status page released with many improvements and changes:
  + Updated with uptime percentages, full incident history, and new API
  + Added product-specific uptime displays
  + Enabled access to complete incident records
  + Launched API for automated status checks
* **Documentation**: We made a few important improvements and changes in our docs:
  + New welcome page added
  + Improved top navigation for better product accessibility
  + Enhanced mobile menu with a focus on product selection
  + Fixed all broken links for improved SEO
  + Added a new security section

##### NOTES[​](/general/changelog/#notes-2 "Direct link to NOTES")

* **Customer Portal**: We removed possibility to set Market Data API REST Request Limits per specific API Key. Keys that had that enabled and set will work the same. The new keys do not have possibility to have that set.

2024 July 01[​](/general/changelog/#2024-july-01 "Direct link to 2024 July 01")
-------------------------------------------------------------------------------

##### IMPROVEMENTS[​](/general/changelog/#improvements-14 "Direct link to IMPROVEMENTS")

* **Market Data API**: Effective immediately, we have increased the publishing frequency of our historical exchange rates from 1-second intervals to 100-millisecond intervals to enable more precise analysis and decision-making for our users who rely on historical exchange rate data.
  + Historical exchange rates are now updated every 100 milliseconds (previously every 1 second)
  + This change applies to all currency pairs in our historical data set
  + No action is required from customers to access this enhanced data
* **Customer Portal**: A new, more user-friendly way to log in. When you are logged in to the Customer or Support portal then you can switch between them without logging in again separately.

2024 June 01[​](/general/changelog/#2024-june-01 "Direct link to 2024 June 01")
-------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-13 "Direct link to FEATURES")

* **Customer Portal**: The release of an improved Usage Metrics view with new features.
  + **Extended Time Interval Querying:** Customers can now query usage metrics over a wider range of time intervals, including 1 hour, 6 hours, 1 day, 3 days, 1 week, 2 weeks, and 1 month. This enables better trend analysis and long-term tracking of data usage patterns.
  + **Advanced Filtering Options:** The updated view allows fine-grained filtering by several parameters: Data Center, API Key, Data Source, Operation Name, Protocol Name, and Service Name.
  + **More Metrics Available for Tracking:** Customers can track a variety of metrics using the new view, including Data Messages Received, Data Messages Sent, Data Bytes Received, Data Bytes Sent, Connection Time, API Calls, API Calls Received, API Calls Sent, Market Data API REST Credits
* **WebSocket DS API**:
  + **Exchange-Specific Connections:** The new setup ensures that issues with one exchange do not affect other data streams.
  + **Direct Routing with Optimized DNS:** Connections are routed directly to the infrastructure closest to the exchange, reducing latency by eliminating unnecessary hops and aggregation points.
  + **Enhanced Authorization:** Authorization now supports query-string, URL path, header, or JWT (JSON Web Token), removing the need for the API key field in the hello message.
  + **Precise Symbol Filtering:** Requires exact symbol identifiers, with error messaging for invalid symbols while keeping the connection active. Supports both our format and the exchange format for symbol identifiers.
  + **Supported Data Types:** Includes quote, trade, and book data types for comprehensive data access.

##### INTEGRATIONS[​](/general/changelog/#integrations-7 "Direct link to INTEGRATIONS")

* **Market Data API**: We have integrated our Market Data API with the BITRUE exchange.
* **EMS Trading API**: Integrated the Institutional API using FIX.
* **EMS Trading API**: Refreshed our integration with Poloniex to utilize their newest API

##### IMPROVEMENTS[​](/general/changelog/#improvements-15 "Direct link to IMPROVEMENTS")

* **API Limits:** `X-CoinAPI-Limits: ForceInclude` header is no longer interpreted on our side and information about the Limits is provided in each API Call response header.
* **Support:** We have added support for the Coinbase Advanced API (WebSocket) to our EMS API.
* **EMS Trading API**: We have also conducted various tests on our existing integrations and made a few improvements.
* **WebSocket DS API**:
  + **Better Latency:** By routing connections directly to the nearest infrastructure to the exchange, one hop in the data transmission path is eliminated, resulting in faster data delivery.
  + **Optimized for High Volume:** Designed to handle high data volumes efficiently, addressing the limitations of the original WebSocket API under high traffic conditions.

##### ONGOING SUPPORT[​](/general/changelog/#ongoing-support "Direct link to ONGOING SUPPORT")

* **WebSocket API V1:** Continued support with no plans for deprecation. Users can continue using the V1 API as usual while benefiting from the new features of the WebSocket DS API.

2024 May 01[​](/general/changelog/#2024-may-01 "Direct link to 2024 May 01")
----------------------------------------------------------------------------

##### INTEGRATIONS[​](/general/changelog/#integrations-8 "Direct link to INTEGRATIONS")

* **Market Data API**: Integration of BitMEX Options - Users can now trade options for BTC, ETH, DOGE, SOL, BNB, and XRP with multiple expiration dates. The new multi-coin margining system supports BTC, USDT, and USDC.
* **Market Data API**: Reintegration with LMAX Digital exchange

##### FEATURES[​](/general/changelog/#features-14 "Direct link to FEATURES")

* **Market Data API**: New feature to access on-chain addresses for each asset, including details such as chain ID, network ID, and specific addresses for networks like ARBITRUM and ETHEREUM.
* **Customer Portal**: Introduced Traces View to provide detailed logs of all API calls, including filtering options for time ranges and HTTP status. This feature enhances transparency and allows real-time monitoring of API interactions.

2024 April 01[​](/general/changelog/#2024-april-01 "Direct link to 2024 April 01")
----------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-15 "Direct link to FEATURES")

* **Index API**: We've released the Alpha version of the feature with the IDX\_REFRATE\_VWAP indexes family. Values have been filled backward for almost 15 years. Current values are also available. Index endpoints have been refreshed to reflect available operations and fit usage scenarios. The documentation is updated.
* **Index API**: The feature is designed to give a comprehensive view of the market by aggregating data from many sources. This can be particularly useful for traders and investors who want to get a broad overview of the market conditions. More information about the Index API can be found at <https://docs.coinapi.io/market-data/rest-api/indexes>
* **CoinAPI SDK**: .NET console application for SDK exchange data throughput/latency tests
* **Market Data WebSocket API**: We added the possibility to subscribe to any asset pair in exchange rates (previously only USD or stablecoins were allowed on the quote).
* **Market Data REST API**: In the metadata of assets, for each asset, we now provide the on-chain addresses per network chain.

##### IMPROVEMENTS[​](/general/changelog/#improvements-16 "Direct link to IMPROVEMENTS")

* **Status Page**: We are now collecting new Prometheus metrics from the integrations that will be charted in Grafana. In the next step, we will provide dashboards with performance metrics for our API, so that customers have more insight into our statistics.
* **Customer Portal**: A new, more transparent view of subscriptions is introduced: <https://customerportal.coinapi.io/subscriptions>
* **Market Data API**: Exchange Rates API – Historical Exchange Rates using now the same data source as Index API.
* **Market Data API**: Multiple unrelated stability and latency improvements executed.

##### INTEGRATIONS[​](/general/changelog/#integrations-9 "Direct link to INTEGRATIONS")

* **Market Data API**: General stability and performance improvements for DERIBIT, POLONIEXFTS, CRYPTOCOM

##### NOTES[​](/general/changelog/#notes-3 "Direct link to NOTES")

* **Websocket API**: Changed book data type to require a defined filter in the hello or subscribe message

2024 March 01[​](/general/changelog/#2024-march-01 "Direct link to 2024 March 01")
----------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-16 "Direct link to FEATURES")

* **Market Data WebSocket API**: Added 2 new messages (subscribe and unsubscribe) to allow control of the state of the connection without repeating the complete state using a hello message at every change.

##### IMPROVEMENTS[​](/general/changelog/#improvements-17 "Direct link to IMPROVEMENTS")

* **Market Data REST API**: Added example responses in the REST API in OpenAPI and the documentation.
* **Market Data API**: Several improvements exeucted for the BEQUANT CRYPTOCOM HUOBIFTS~ BITKUB data sources.
* **Market Data REST API**: OHLCV by Exchange endpoint can now be called while time\_start and time\_end crossing midnight UTC.
* **Market Data API**: Multiple unrelated stability and latency improvements executed.
* **Documentation**: Added the API limits and billing metrics page.
* **Documentation**: Added the performance testing guide page.

##### BUG FIXES[​](/general/changelog/#bug-fixes-5 "Direct link to BUG FIXES")

* **Market Data REST API**: Resolved issue causing the REST API Credits to be counted incorrectly while having multiple API Keys for some customers.

2024 February 01[​](/general/changelog/#2024-february-01 "Direct link to 2024 February 01")
-------------------------------------------------------------------------------------------

##### FEATURES[​](/general/changelog/#features-17 "Direct link to FEATURES")

* **Market Data REST API**: Added Index API feature for the testing and early feedback in the alpha version.
* **Market Data REST API**: Added OHLCV historical data by exchange.

##### IMPROVEMENTS[​](/general/changelog/#improvements-18 "Direct link to IMPROVEMENTS")

* **Documentation**: Added the EMS Trading API QuickStart How-to Guide.
* **Website**: Released Metadata Explorer covering the exchanges and symbols that we support.

2024 January 01[​](/general/changelog/#2024-january-01 "Direct link to 2024 January 01")
----------------------------------------------------------------------------------------

##### BREAKING CHANGES[​](/general/changelog/#breaking-changes-2 "Direct link to BREAKING CHANGES")

* **EMS API**: Public release of the product, promotion from the beta phase.

##### IMPROVEMENTS[​](/general/changelog/#improvements-19 "Direct link to IMPROVEMENTS")

* **Market Data API**: Increased stability and reduced latency by 50% for the Exchange Rates and OHLCV endpoints.
* **Support:** Intoduced AI Bot that has the information about the product and answering questions on the support.
* **Market Data API**: Increased the frequency and stability of the data feeds reducing the latencies and variance of latencies.
* **Documentation**: Migrating the FAQ section to the documentation.
* **Website**: Improved free plan subscription flow.

##### INTEGRATIONS[​](/general/changelog/#integrations-10 "Direct link to INTEGRATIONS")

* **Market Data API**: Added new integration `DYDX` to the DYDX v3.
* **EMS API**: Added new integration `DYDX` to the DYDX v3.

##### FEATURES[​](/general/changelog/#features-18 "Direct link to FEATURES")

* **Market Data FIX API**: Improved feed L2 feed to make sure each L2 update is trackable to specific L3 updates if the data source distributing data in L3 format.

##### BUG FIXES[​](/general/changelog/#bug-fixes-6 "Direct link to BUG FIXES")

* **EMS API**: Resolved issue related to the fact that we reported errors on invalid orders received from the customer side in non descriptive manner.

##### NOTES[​](/general/changelog/#notes-4 "Direct link to NOTES")

* We focused mostly on the stability of the platform and improvements that we can execute on multiple fronts.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Enterprise Plan](/general/faq/Enterprise-Plan/)[Next

Product Roadmap](/general/roadmap)

* [2025 July 30](/general/changelog/#2025-july-30)
* [2025 June 29](/general/changelog/#2025-june-29)
* [2025 June 26](/general/changelog/#2025-june-26)
* [2025 June 18](/general/changelog/#2025-june-18)
* [2025 June 17](/general/changelog/#2025-june-17)
* [2025 June 13](/general/changelog/#2025-june-13)
* [2025 May 30](/general/changelog/#2025-may-30)
* [2025 May 29](/general/changelog/#2025-may-29)
* [2025 May 21](/general/changelog/#2025-may-21)
* [2025 May 14](/general/changelog/#2025-may-14)
* [2025 May 9](/general/changelog/#2025-may-9)
* [2025 April 01](/general/changelog/#2025-april-01)
* [2025 March 01](/general/changelog/#2025-march-01)
* [2025 February 01](/general/changelog/#2025-february-01)
* [2025 January 01](/general/changelog/#2025-january-01)
* [2024 December 01](/general/changelog/#2024-december-01)
* [2024 November 01](/general/changelog/#2024-november-01)
* [2024 October 01](/general/changelog/#2024-october-01)
* [2024 September 01](/general/changelog/#2024-september-01)
* [2024 August 01](/general/changelog/#2024-august-01)
* [2024 July 01](/general/changelog/#2024-july-01)
* [2024 June 01](/general/changelog/#2024-june-01)
* [2024 May 01](/general/changelog/#2024-may-01)
* [2024 April 01](/general/changelog/#2024-april-01)
* [2024 March 01](/general/changelog/#2024-march-01)
* [2024 February 01](/general/changelog/#2024-february-01)
* [2024 January 01](/general/changelog/#2024-january-01)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.