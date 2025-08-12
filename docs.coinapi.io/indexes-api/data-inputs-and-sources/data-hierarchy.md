Data Hierarchy | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/data-inputs-and-sources/data-hierarchy)

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

* [Indexes API](/indexes-api/)
* [Introduction](/indexes-api/introduction/)

  + [Purpose and Scope](/indexes-api/introduction/purpose-and-scope)
  + [Key Principles](/indexes-api/introduction/key-principles)
  + [Quickstart](/indexes-api/introduction/quickstart)
  + [Governance and Oversight](/indexes-api/introduction/governance-and-oversight)
* [Index offerings](/category/index-offerings)

  + [Principal Market Price](/indexes-api/index-offerings/primkt-index)
  + [Volume Weighted Average Price](/indexes-api/index-offerings/vwap-index)
  + [Volatility Index](/indexes-api/index-offerings/capivix-index)
* [Introduction](/indexes-api/rest-api/coinapi-indexes-rest-api)
* [WebSocket Index API](/indexes-api/websocket-api/)

  + [Endpoints](/indexes-api/websocket-api/endpoints)
  + [General](/indexes-api/websocket-api/general)
  + [Messages](/indexes-api/websocket-api/messages)
* [Data Inputs and Sources](/indexes-api/data-inputs-and-sources/)

  + [Exchange Selection Criteria](/indexes-api/data-inputs-and-sources/exchange-selection-criteria)
  + [Data Quality Controls](/indexes-api/data-inputs-and-sources/data-quality-controls)
  + [Data Hierarchy](/indexes-api/data-inputs-and-sources/data-hierarchy)
* [Index Calculation Methodologies](/category/index-calculation-methodologies)
* [Eligibility Criteria](/category/eligibility-criteria)
* [Index Maintenance](/category/index-maintenance)
* [Index policies](/indexes-api/index-policies/)
* [Governance](/category/governance)
* [Conflict of Interest Policies](/indexes-api/conflict-of-interest-policies)
* [Use of Expert Judgment](/indexes-api/use-of-expert-judgment)
* [Limitations of the Indexes](/indexes-api/limitations-of-the-indexes)
* [Disclaimer](/indexes-api/disclaimer)
* [MCP API](/indexes-api/mcp)

* [Data Inputs and Sources](/indexes-api/data-inputs-and-sources/)
* Data Hierarchy

Data Hierarchy
==============

In the event of data unavailability or quality issues from primary sources, CoinAPI employs a clear data hierarchy to ensure consistent and reliable index calculation:

1. Primary Data Sources: Data from exchanges meeting all our selection criteria form the primary inputs for index calculations.
2. Last Known Good Data: If current data is unavailable or unreliable across all sources, we may use the last known good data point.
3. Secondary Data Sources: A list of pre-approved backup exchanges is maintained. If primary sources experience long-term issues or failures, these sources can be replaced by backup exchanges. Such information is publicly announced.
4. Index Suspension: In extreme cases where no reliable data is available and using stale data would be misleading, index calculation may be temporarily suspended.

The exact hierarchy and failover processes are tailored to each specific index and are detailed in the respective index methodologies.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Data Quality Controls](/indexes-api/data-inputs-and-sources/data-quality-controls)[Next

Index Calculation Methodologies](/category/index-calculation-methodologies)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.