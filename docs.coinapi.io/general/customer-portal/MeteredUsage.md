Metered Usage | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/customer-portal/MeteredUsage)

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
* Metered Usage

On this page

Metered Usage
=============

This is your Metered Usage page, accessible through your console. It's designed to provide a transparent way for you to track and understand your detailed service consumption, which is particularly important as invoices offer a more summarized view due to fractional billing. This page also helps you monitor usage that, under the new billing rules, might not be invoiced immediately.

The page is organized into three main views:

* **Daily History:** This view is set up to provide a day-by-day breakdown of your service usage. Here, you can review your consumption patterns on a daily basis.
* **Monthly Statement:** This view offers a more detailed summary of your usage over an entire month, supplementing the summarized information on your main invoice. It provides a comprehensive record of your monthly consumption.
* **Uninvoiced Currently:** This section is designed to display any service usage that has accumulated but has not yet been formally invoiced. This is especially relevant as invoices are issued only after an actual payment (excluding free or promotional credits) is made. In this view, you can see all usage that is awaiting future invoicing, particularly if you are a new customer yet to make an initial payment.

Daily History[​](/general/customer-portal/MeteredUsage#daily-history "Direct link to Daily History")
----------------------------------------------------------------------------------------------------

**Daily History page is** located within the "Metered Usage" section. It provides a detailed breakdown of your daily usage for various services and any associated pay-as-you-go costs.

Here's what you'll find on this page:

* **Controls at the Top**:
  + **"Select range"**: A dropdown or button that allows you to choose the specific date for which you want to view the history.
  + **"Filter Product Name..."**: An input field where you can type to search for specific product names within the history list.
* **Usage Details Table**:
  + This table lists your metered usage with the following columns:
    - **Name**: The name of the service or product (e.g., "CoinAPI Market Data API").
    - **SKU Name**: The specific stock-keeping unit or item name (e.g., "Connections," "API Credits," "Data Transfer - Tier 1").
    - **Description**: Details about the item, often including the pricing structure (e.g., "$0.02 per Connection-Hour," "$5.26 / 1k for first 1,000 credits / day," or tiered pricing for credits).
    - **Total usage**: The total amount of the service used (e.g., "60.79 Hours," "1000 Credits," "32 GB").
    - **Included usage**: The portion of the total usage that is covered by your plan's included allowances.
    - **PAYG usage**: The portion of the total usage that exceeds included allowances and falls under pay-as-you-go.
    - **PAYG Cost**: The cost associated with any pay-as-you-go usage
  + The table displays various entries, such as usage for API connections, different tiers of API credits, and data transfer.
* **Summary and Page Controls at the Bottom**:
  + **"Total pre-tax cost"**: Shows the sum of all pay-as-you-go costs for the selected period (e.g., "USD 0.00").

Monthly Statement[​](/general/customer-portal/MeteredUsage#monthly-statement "Direct link to Monthly Statement")
----------------------------------------------------------------------------------------------------------------

**Monthly Statement page** is located within the "Metered Usage" section. This page provides a summary of your metered usage and any associated pay-as-you-go costs for a selected month.

Here's a breakdown of what you'll find on this page:

* **Controls at the Top**:
  + **"Year" dropdown**: Allows you to select the year for the statement.
  + **"Month" dropdown**: Allows you to select the month for the statement.
  + **"Filter Product Name..."**: An input field where you can type to search for specific product names within the statement.
* **Usage Details Table**:
  + This table lists your metered usage for the selected month with the following columns:
    - **Name**: The name of the service or product (e.g., "CoinAPI Market Data API").
    - **SKU Name**: The specific stock-keeping unit or item name (e.g., "Connections," "API Credits").
    - **Description**: Details about the item, often including the pricing structure (e.g., "$0.02 per Connection-Hour," or tiered rates like "$5.26 / 1k for first 1,000 credits / day").
    - **Total usage**: The total amount of the service used during the selected month (e.g., "3157.843 Hours," "27000 Credits").
    - **Included usage**: The portion of the monthly total usage covered by your plan's included allowances.
    - **PAYG usage**: The portion of the monthly total usage that exceeds the included allowances.
    - **PAYG Cost**: The cost associated with any pay-as-you-go usage for the month.
  + The table displays various entries, reflecting accumulated monthly usage for items like API connections and different tiers of API credits.
* **Summary and Page Controls at the Bottom**:
  + **"Total pre-tax cost"**: Shows the sum of all pay-as-you-go costs for the selected month.

Uninvoiced Currently[​](/general/customer-portal/MeteredUsage#uninvoiced-currently "Direct link to Uninvoiced Currently")
-------------------------------------------------------------------------------------------------------------------------

**Uninvoiced Currently page** is located within the "Metered Usage" section. This page shows you a real-time or very recent overview of your metered usage that has accumulated since your last invoice and has not yet been billed.

Here's what you'll find on this page:

* **Controls at the Top**:
  + **"Filter Product Name..."**: An input field where you can type to search for specific product names within the list of uninvoiced items.
* **Usage Details Table**:
  + This table lists your current uninvoiced usage with the following columns:
    - **Name**: The name of the service or product (e.g., "CoinAPI Market Data API").
    - **SKU Name**: The specific stock-keeping unit or item name (e.g., "Connections," "API Credits").
    - **Description**: Details about the item, often including the pricing structure (e.g., "$0.02 per Connection-Hour," or tiered rates like "$5.26 / 1k for first 1,000 credits / day").
    - **Total usage**: The total amount of the service used so far in the current uninvoiced period (e.g., "29748.429 Hours," "250000 Credits").
    - **Included usage**: The portion of this current usage that is covered by your plan's included allowances.
    - **PAYG usage**: The portion of the current usage that exceeds included allowances and would be billable on a pay-as-you-go basis.
    - **PAYG Cost**: The potential cost associated with any current pay-as-you-go usage.
  + The table displays various entries, reflecting your accumulated usage for items like API connections and different tiers of API credits up to the current point in your billing cycle.
* **Summary and Page Controls at the Bottom**:
  + **"Total pre-tax cost"**: Shows the sum of all potential pay-as-you-go costs for the current uninvoiced period (e.g., "USD 0.00").

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Usage Explorer](/general/customer-portal/UsageExplorer)[Next

Support Tickets](/general/customer-portal/SupportTickets)

* [Daily History](/general/customer-portal/MeteredUsage#daily-history)
* [Monthly Statement](/general/customer-portal/MeteredUsage#monthly-statement)
* [Uninvoiced Currently](/general/customer-portal/MeteredUsage#uninvoiced-currently)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.