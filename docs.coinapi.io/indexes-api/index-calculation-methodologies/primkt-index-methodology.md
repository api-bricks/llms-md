PRIMKT Index Methodology | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/index-calculation-methodologies/primkt-index-methodology)

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
* [Index Calculation Methodologies](/category/index-calculation-methodologies)

  + [PRIMKT Index Methodology](/indexes-api/index-calculation-methodologies/primkt-index-methodology)
  + [VWAP Index Methodology](/indexes-api/index-calculation-methodologies/vwap-index-methodology)
  + [CAPIVIX Index Methodology](/indexes-api/index-calculation-methodologies/capivix-index-methodology)
* [Eligibility Criteria](/category/eligibility-criteria)
* [Index Maintenance](/category/index-maintenance)
* [Index policies](/indexes-api/index-policies/)
* [Governance](/category/governance)
* [Conflict of Interest Policies](/indexes-api/conflict-of-interest-policies)
* [Use of Expert Judgment](/indexes-api/use-of-expert-judgment)
* [Limitations of the Indexes](/indexes-api/limitations-of-the-indexes)
* [Disclaimer](/indexes-api/disclaimer)
* [MCP API](/indexes-api/mcp)

* [Index Calculation Methodologies](/category/index-calculation-methodologies)
* PRIMKT Index Methodology

On this page

PRIMKT Index Methodology
========================

This article provides comprehensive information on the calculation methodology for our PRIMKT (Principal Market Price) indexes. It offers a detailed explanation of how CoinAPI PRIMKT Indexes are calculated, which can be valuable for understanding the process and verifying index value accuracy.

Data Inputs[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#data-inputs "Direct link to Data Inputs")
------------------------------------------------------------------------------------------------------------------------------

### Exchange Selection[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#exchange-selection "Direct link to Exchange Selection")

The index considers data from the following exchanges:

* Binance
* Bitstamp
* Bitfinex
* Bybit Spot
* Coinbase
* Deribit
* Gemini
* Kraken
* KuCoin
* OKEx
* Upbit

### Symbol Selection[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#symbol-selection "Direct link to Symbol Selection")

Only SPOT trading pairs from the selected exchanges are considered for index calculation.

### Time Periods[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#time-periods "Direct link to Time Periods")

Two key time periods are used in the calculation:

1. **Activity Period**: Ends at the index calculation time and spans the last 15 minutes.
2. **Lookup Period**: Ends at the index calculation time and spans the last 60 minutes.

Calculation Methodology[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#calculation-methodology "Direct link to Calculation Methodology")
------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Exchange Filtering**: Exchanges without any trades in the Activity Period are excluded.
2. **Data Collection**: For each eligible symbol, volume and last price data are collected from the remaining exchanges over the Lookup Period.
3. **Principal Market Determination**: For each symbol, the exchange with the highest trading volume is designated as the principal market.
4. **Index Value Calculation**: The index value for each symbol is set to the last traded price on its principal market during the Lookup Period.

Index Outputs[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#index-outputs "Direct link to Index Outputs")
------------------------------------------------------------------------------------------------------------------------------------

### Index Codes[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#index-codes "Direct link to Index Codes")

Index values are created with the following format:
`{IndexDefinitionCode}_{BaseAssetId}_{QuoteAssetId}`

### Components[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#components "Direct link to Components")

Each index includes the following component:

* `PRINCIPAL_MARKET_VOLUME_PERCENTAGE_{ExchangeIdBeingPrincipalMarket}`: Represents the percentage of total volume from the principal market.

Note: Component data is only available for index values calculated within the last 7 days.

Frequency[​](/indexes-api/index-calculation-methodologies/primkt-index-methodology#frequency "Direct link to Frequency")
------------------------------------------------------------------------------------------------------------------------

The index is calculated in real-time, providing up-to-date pricing information for supported digital assets.

Please note that for real-time scenarios, we highly encourage you to use our WebSocket Index API. This API provides continuous, low-latency updates, ensuring you receive the most up-to-date index values as they are calculated. For more information on how to connect and use the WebSocket API, please refer to our [WebSocket Index API documentation](/indexes-api/websocket-api).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Index Calculation Methodologies](/category/index-calculation-methodologies)[Next

VWAP Index Methodology](/indexes-api/index-calculation-methodologies/vwap-index-methodology)

* [Data Inputs](/indexes-api/index-calculation-methodologies/primkt-index-methodology#data-inputs)
  + [Exchange Selection](/indexes-api/index-calculation-methodologies/primkt-index-methodology#exchange-selection)
  + [Symbol Selection](/indexes-api/index-calculation-methodologies/primkt-index-methodology#symbol-selection)
  + [Time Periods](/indexes-api/index-calculation-methodologies/primkt-index-methodology#time-periods)
* [Calculation Methodology](/indexes-api/index-calculation-methodologies/primkt-index-methodology#calculation-methodology)
* [Index Outputs](/indexes-api/index-calculation-methodologies/primkt-index-methodology#index-outputs)
  + [Index Codes](/indexes-api/index-calculation-methodologies/primkt-index-methodology#index-codes)
  + [Components](/indexes-api/index-calculation-methodologies/primkt-index-methodology#components)
* [Frequency](/indexes-api/index-calculation-methodologies/primkt-index-methodology#frequency)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.