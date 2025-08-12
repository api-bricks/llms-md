Traces | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/customer-portal/Traces)

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
* Traces

On this page

Traces
======

Traces Requests[​](/general/customer-portal/Traces#traces-requests "Direct link to Traces Requests")
----------------------------------------------------------------------------------------------------

This is your **Traces Requests page**, located within the "Traces" section. It is a tool for monitoring, analyzing, and debugging your API calls. It provides a detailed overview of your API request and response activity.

On the left side of the page, you have filtering options to narrow down the traces.

You can filter by **Time**, with choices:

* "Last 5 minutes"
* "Last 15 minutes"
* "Last 1 hour"
* "Last 4 hours"
* "Last 24 hours"

You can filter by **HTTP Status**, including:

* "All"
* "Success"
* "Client Error"
* "Server Error"

The main area on the right, titled "Traces Requests," displays the list of API call traces. Here, you'll find an "**Export data**" button to download the trace information and a field to "Filter Method..." if you're looking for specific API methods.

The table itself shows key details for each API call: the **Timestamp (UTC)** when the call was made, the **Method** used, the **Product** accessed, the **HTTP** status code, and the **Response time**.

You can click on a specific trace entry to see a detailed JSON view with more granular information so so-called “**Request Trace”.** It's the kind of in-depth view you'd access when investigating a particular trace from the main list.

### Request Trace[​](/general/customer-portal/Traces#request-trace "Direct link to Request Trace")

At the top, under "Connection Details," you get a quick summary with cards showing the **HTTP Route** (e.g., `v1/ohlcv/symbol_id/history`), the **HTTP Method** (e.g., `GET`), and the **HTTP Status Code** (e.g., `200`).

Below this summary, the page lists numerous specific details about the trace. This includes the **Timestamp** of the request, a unique **Trace ID**, the **Span Name**, and the **Service Name** like "MarketDataAPI/REST." A significant field is **Span Attributes**, which displays a JSON block containing many raw request and response parameters, including the API key used and target details. Further down, you'll find more parsed information such as the request **Duration**, the specific **HTTP Target** and full **HTTP URL**, the **HTTP Flavor**, the **API Key** involved, the **NET Host Name**, the **HTTPScheme**, and the **ID Organization**. Some details like the HTTP method, route, and status code are repeated here from the summary cards for comprehensive reference.

### Traces Connections[​](/general/customer-portal/Traces#traces-connections "Direct link to Traces Connections")

This is your **Traces Connections page**, located within the "Traces" section. This page provides an overview of service connections, detailing their activity and status.

At the top, you have a field to "Filter Service Name..." if you need to find connections related to a specific service.

The main part of the page displays a table listing these connections. Each entry in the table shows a unique **Connection ID**, the **Service Name** (e.g., "MarketData"), the **Protocol Name** (e.g., "WebSocket"), the **Start Time** and **End Time** of the connection, and the current **Status**. The status is clearly indicated, showing whether a connection is "Connected" or "Disconnected," highlighted with a badge.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

API Keys](/general/customer-portal/APIKeys)[Next

Usage Explorer](/general/customer-portal/UsageExplorer)

* [Traces Requests](/general/customer-portal/Traces#traces-requests)
  + [Request Trace](/general/customer-portal/Traces#request-trace)
  + [Traces Connections](/general/customer-portal/Traces#traces-connections)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.