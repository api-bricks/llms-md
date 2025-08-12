VWAP Index Methodology | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/index-calculation-methodologies/vwap-index-methodology)

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
* VWAP Index Methodology

On this page

VWAP Index Methodology
======================

This article provides comprehensive information on the calculation methodology for our VWAP (Volume-Weighted Average Price) indexes. It offers a detailed explanation of how CoinAPI VWAP Indexes are calculated, which can be valuable for understanding the process and verifying index value accuracy.

Data Inputs[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#data-inputs "Direct link to Data Inputs")
----------------------------------------------------------------------------------------------------------------------------

### Exchange Selection[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#exchange-selection "Direct link to Exchange Selection")

The index considers data from the following exchanges, with specific symbol considerations:

| Exchange | Symbols Considered |
| --- | --- |
| Binance | All available trading pairs |
| Bitstamp | All available trading pairs |
| Bitfinex | All available trading pairs |
| Bybit Spot | All available trading pairs |
| Coinbase | All available trading pairs |
| Deribit | All available trading pairs |
| Gemini | All available trading pairs |
| Kraken | All available trading pairs |
| KuCoin | All available trading pairs |
| OKEx | All available trading pairs |
| Upbit | All available trading pairs |
| GateIO | All available trading pairs |
| HitBTC | All available trading pairs |

### Symbol Selection[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#symbol-selection "Direct link to Symbol Selection")

From the trading pairs available on each exchange as indicated in the table above, only SPOT trading pairs are considered for index calculation.

### Time Period[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#time-period "Direct link to Time Period")

The index uses a 24-hour lookback period for price and volume data.

Calculation Methodology[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#calculation-methodology "Direct link to Calculation Methodology")
----------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Data Collection**: For each eligible symbol, query the average price and volume data from the proper exchanges over the last 24 hours.
2. **Symbol Grouping**: Group symbols according to their base and quote assets. Symbols with the same pairs of base and quote assets are grouped together, regardless of order.
3. **Group Calculations**: For each group:

   * Calculate the volume-weighted average price expressed in units of one asset from the pair.
   * Sum up the volumes of trades into a total volume.
4. **Price Conversion**: Convert prices calculated for each group to be expressed in reference asset units:

   * Construct a graph where vertices symbolize assets and edges symbolize cumulative trades between pairs of assets.
   * Launch a Breadth-First Search (BFS) algorithm from the reference asset vertex:
     + Set the depth of assets (reference and stable coin assets have depth 0).
     + For each vertex at depth "k", process edges to vertices at depth "k-1":
       - Filter edges to include only those with prices within 3 standard deviations of the average.
       - Convert prices to be expressed in reference asset.
       - Calculate the weighted average price for the vertex.

Index Outputs[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#index-outputs "Direct link to Index Outputs")
----------------------------------------------------------------------------------------------------------------------------------

### Index Codes[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#index-codes "Direct link to Index Codes")

Index values are created with the following format:
`{IndexDefinitionCode}_{AssetId}`

The value of such an index is the 24-hour volume-weighted average price of the asset expressed in reference asset units.

### Components[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#components "Direct link to Components")

Each index includes the following components:

* `VISITED_AT_DEPTH`: Shows the level (iteration) at which the algorithm calculated the average price for the current asset (for debugging purposes).
* `{IndexDefinitionCode}_{AnotherAssetId}`: Average price of another asset (in reference asset units) used to calculate the current asset's average price.
* `{BaseAssetId}_{QuoteAssetId}_24H_AVERAGE_PRICE_IN_REF_ASSET`: Volume-weighted average price of base asset calculated from all trades between base and quote assets in the last 24 hours, expressed in reference asset units.
* `{BaseAssetId}_{QuoteAssetId}_24H_TOTAL_VOLUME`: Total volume of all trades in the last 24 hours between base and quote assets.
* `{BaseAssetId}_{QuoteAssetId}_24H_AVERAGE_PRICE`: Volume-weighted average price of base asset calculated from all trades between base and quote assets in the last 24 hours.
* `SYMBOL_24H_PRICE_{SymbolId}`: Average price of symbol base asset traded in the last 24 hours, expressed in symbol quote asset units.
* `SYMBOL_24H_VOLUME_{SymbolId}`: Total volume of symbol base asset traded in the last 24 hours.

Frequency[​](/indexes-api/index-calculation-methodologies/vwap-index-methodology#frequency "Direct link to Frequency")
----------------------------------------------------------------------------------------------------------------------

The index is calculated periodically, providing up-to-date pricing information for supported digital assets.

For real-time index updates, we recommend using our WebSocket Index API. This API provides continuous, low-latency updates, ensuring you receive the most up-to-date index values as they are calculated. For more information on how to connect and use the WebSocket API, please refer to our [WebSocket Index API documentation](/indexes-api/websocket-api).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

PRIMKT Index Methodology](/indexes-api/index-calculation-methodologies/primkt-index-methodology)[Next

CAPIVIX Index Methodology](/indexes-api/index-calculation-methodologies/capivix-index-methodology)

* [Data Inputs](/indexes-api/index-calculation-methodologies/vwap-index-methodology#data-inputs)
  + [Exchange Selection](/indexes-api/index-calculation-methodologies/vwap-index-methodology#exchange-selection)
  + [Symbol Selection](/indexes-api/index-calculation-methodologies/vwap-index-methodology#symbol-selection)
  + [Time Period](/indexes-api/index-calculation-methodologies/vwap-index-methodology#time-period)
* [Calculation Methodology](/indexes-api/index-calculation-methodologies/vwap-index-methodology#calculation-methodology)
* [Index Outputs](/indexes-api/index-calculation-methodologies/vwap-index-methodology#index-outputs)
  + [Index Codes](/indexes-api/index-calculation-methodologies/vwap-index-methodology#index-codes)
  + [Components](/indexes-api/index-calculation-methodologies/vwap-index-methodology#components)
* [Frequency](/indexes-api/index-calculation-methodologies/vwap-index-methodology#frequency)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.