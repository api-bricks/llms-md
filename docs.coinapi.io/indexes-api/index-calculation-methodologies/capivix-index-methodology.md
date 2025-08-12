CAPIVIX Index Methodology | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/index-calculation-methodologies/capivix-index-methodology)

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
* CAPIVIX Index Methodology

On this page

CAPIVIX Index Methodology
=========================

This article provides comprehensive information on the calculation methodology for our CAPIVIX (CoinAPI Volatility Index) indexes. These indexes measure the market's expectation of 30-day volatility for major cryptocurrencies, similar to the VIX methodology for traditional markets. Currently, we calculate CAPIVIX for BTC/USD and ETH/USD pairs.

Data Inputs[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#data-inputs "Direct link to Data Inputs")
-------------------------------------------------------------------------------------------------------------------------------

### Exchange Selection[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#exchange-selection "Direct link to Exchange Selection")

The index considers options data from various selected derivatives exchanges.

### Instrument Selection[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#instrument-selection "Direct link to Instrument Selection")

For each underlying asset (BTC, ETH):

* Near-term and next-term put and call options
* Only options with more than zero volume in the last 24 hours
* Strike prices that straddle the current spot price
* Minimum of 8 strike prices per expiration

### Time Periods[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#time-periods "Direct link to Time Periods")

The calculation uses two expiration time periods:

1. **Near-term**: Options with < 30 days to expiration
2. **Next-term**: Options with ≥ 30 days to expiration

Calculation Methodology[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#calculation-methodology "Direct link to Calculation Methodology")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Data Collection**:

   * Select eligible options for both near-term and next-term expirations
   * Collect bid-ask quotes for each selected option
   * Record the risk-free interest rate for each expiration period
2. **Forward Level Calculation**:

   * Determine the forward index level (F) using put-call parity
   * Identify the strike price (K₀) at which the absolute difference between call and put prices is smallest
3. **Variance Calculation** for each expiration:

   ```
   σ² = (2/T) * Σ[ΔK/K² * e^(RT) * Q(K)]
   ```

   Where:

   * T is time to expiration
   * ΔK is the interval between strike prices
   * R is the risk-free interest rate
   * Q(K) is the midpoint of the bid-ask spread for each option
4. **30-day Volatility Interpolation**:

   ```
   CAPIVIX = 100 * √[{T₁σ₁²(N₂-N₃₀)/(N₂-N₁) + T₂σ₂²(N₃₀-N₁)/(N₂-N₁)} * N₃₆₅/N₃₀]
   ```

   Where:

   * N₁ and N₂ are near and next-term days to expiration
   * N₃₀ is 30 days
   * N₃₆₅ is 365 days

Index Outputs[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#index-outputs "Direct link to Index Outputs")
-------------------------------------------------------------------------------------------------------------------------------------

### Index Codes[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#index-codes "Direct link to Index Codes")

Index values are created with the following format:
`IDX_VOL_CAPIVIX_{AssetId}_USD`

For example:

* `IDX_VOL_CAPIVIX_BTC_USD`: Bitcoin Volatility Index
* `IDX_VOL_CAPIVIX_ETH_USD`: Ethereum Volatility Index

Frequency[​](/indexes-api/index-calculation-methodologies/capivix-index-methodology#frequency "Direct link to Frequency")
-------------------------------------------------------------------------------------------------------------------------

The index is calculated every 100 milliseconds, providing near-real-time volatility expectations.

For real-time index updates, we recommend using our WebSocket Index API. This API provides continuous, low-latency updates, ensuring you receive the most up-to-date index values as they are calculated. For more information on how to connect and use the WebSocket API, please refer to our [WebSocket Index API documentation](/indexes-api/websocket-api).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

VWAP Index Methodology](/indexes-api/index-calculation-methodologies/vwap-index-methodology)[Next

Eligibility Criteria](/category/eligibility-criteria)

* [Data Inputs](/indexes-api/index-calculation-methodologies/capivix-index-methodology#data-inputs)
  + [Exchange Selection](/indexes-api/index-calculation-methodologies/capivix-index-methodology#exchange-selection)
  + [Instrument Selection](/indexes-api/index-calculation-methodologies/capivix-index-methodology#instrument-selection)
  + [Time Periods](/indexes-api/index-calculation-methodologies/capivix-index-methodology#time-periods)
* [Calculation Methodology](/indexes-api/index-calculation-methodologies/capivix-index-methodology#calculation-methodology)
* [Index Outputs](/indexes-api/index-calculation-methodologies/capivix-index-methodology#index-outputs)
  + [Index Codes](/indexes-api/index-calculation-methodologies/capivix-index-methodology#index-codes)
* [Frequency](/indexes-api/index-calculation-methodologies/capivix-index-methodology#frequency)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.