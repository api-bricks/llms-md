Data Quality Controls | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/data-inputs-and-sources/data-quality-controls)

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
* Data Quality Controls

Data Quality Controls
=====================

To maintain the highest standards of data integrity, CoinAPI algorithms of index calculation, implements a multi-layered approach to data quality control:

1. Real-time Validation: Continuous checks on incoming data are performed, flagging anomalies such as extreme price movements or abnormal trading patterns.
2. Cross-exchange Verification: data across multiple exchanges are compared to identify and investigate any significant discrepancies.
3. Volume Spike Analysis: Sudden, unusual spikes in trading volume are scrutinized to ensure they reflect genuine market activity.
4. Latency Monitoring: data feed latencies are monitored to ensure timely and accurate index calculations.
5. Outlier Detection: Advanced statistical methods are employed to detect and handle outliers in price and volume data.

Complementary, we also take manual actions to ensure the highest data quality:

1. Manual Oversight: Our data quality team provides human oversight, investigating issues and making informed decisions.
2. Historical Data Audits: when needed, historical data audits are conducted to identify and correct any retroactive data issues.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Exchange Selection Criteria](/indexes-api/data-inputs-and-sources/exchange-selection-criteria)[Next

Data Hierarchy](/indexes-api/data-inputs-and-sources/data-hierarchy)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.