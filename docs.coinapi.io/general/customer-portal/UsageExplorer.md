Usage Explorer | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/customer-portal/UsageExplorer)

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

  + [Home](/general/customer-portal/home)
  + [Billing](/general/customer-portal/billing)
  + [Subscriptions](/general/customer-portal/subscriptions)
  + [API Keys](/general/customer-portal/APIKeys)
  + [Traces](/general/customer-portal/Traces)
  + [Usage Explorer](/general/customer-portal/UsageExplorer)
  + [Metered Usage](/general/customer-portal/MeteredUsage)
  + [Support Tickets](/general/customer-portal/SupportTickets)
  + [Quotas and Limits](/general/customer-portal/QuotasLimits)
  + [Notifications](/general/customer-portal/Notifications)
  + [Account](/general/customer-portal/Account)
* [MCP Servers](/general/mcp-servers)
* [FAQ](/general/faq/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [Customer Portal](/general/customer-portal/)
* Usage Explorer

Usage Explorer
==============

This is your **Usage Explorer page**, a dashboard that helps you visualize and analyze various operational data points. The system uses parameters to identify where usage occurred, allowing you to break down metrics effectively.

On the left side, you'll find a panel with several filters to customize the data you see. Each metric can contain a single value. Parameters are used to identify where the usage occurred.

* **Metric Selection -** this dropdown allows you to choose the primary data point for analysis:
  + "Data Messages Received (count)”
  + "Data Messages Received (sent)”
  + “Data Bytes Received (bytes)”
  + “Data Bytes Sent (bytes)”
  + “Connection Time (connection-seconds)”
  + “API Calls (count)”
  + “API Calls Received (count)”
  + “API Calls Sent (count)”
  + “Market Data API REST Credits (credits)”
* **Group By -** this dropdown lets you categorize or group the selected metric for:
  + "DataCenter" - Location where the usage metric was created (e.g. `AWS-EU-EAST-1` etc)
  + "ProtocolName" - he name of the protocol that was used to generate the metric (e.g. `REST`, `WebSocket`, `FIX`, `S3`)
  + "ServiceName" - The name of the product (e.g. `MarketData`)
* **API Keys -** helps separate usage by the specific API Key that initiated the activity.
  + You can filter by "All API keys," or select specific keys
* **Data Center -** filters metrics by the location where the usage occurred (e.g., a specific server facility). Includes "All data centers" or specific locations like "HQ-5" and "DP-AP-NORTHEAST-TY." A search and "Select All" are also available.
* **Data Source -** isolates usage related to a particular data source (e.g., a specific exchange or blockchain).
* **Operation Name -** filters by the specific ID that identifies operations within a Service and Protocol (this is often a Data Type or a specific method call). Search and "Select All" functionalities are present.
* **Protocol Name -** allows you to select metrics based on the communication protocol used:
  + "REST"
  + "WebSocket"
  + "FIX”
* **Service Name -** Filters metrics by the specific product.
  + “Market Data”
  + “ExchangeRates”
  + “FinFeedStockAPI”
  + “NAAS”
  + “Indexes”
  + “EMS”

**The main area on the right displays the selected metrics:**

* **Time Range Selection**:
  + You can quickly select a time frame using buttons like **1H, 6H, 1D, 3D, 1W, 2W, 1M**.
  + A **"Select range"** field is also available for choosing a custom date and time period.
* **Metrics Chart**:
  + A bar chart visually represents the selected metric over the chosen time.
* **Summary Table**:
  + Below the chart, a table summarizes the data.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Traces](/general/customer-portal/Traces)[Next

Metered Usage](/general/customer-portal/MeteredUsage)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.