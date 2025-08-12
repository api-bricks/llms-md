Exchange Rates API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/Exchange-Rates-API/)

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

  + [General](/general/faq/general/)
  + [API Usage and Limits](/general/faq/API-Usage-and-Limits/)
  + [Billing, Payment, and Subscriptions](/general/faq/Billing-Payment-and-Subscriptions/)
  + [Account Management](/general/faq/Account-Management/)
  + [Security and Privacy](/general/faq/Security-and-Privacy/)
  + [API Access & Integration](/general/faq/API-Access-and-Integration/)
  + [Market Data API](/general/faq/Market-Data-API/)
  + [EMS Trading API](/general/faq/EMS-Trading-API/)
  + [Indexes API](/general/faq/Indexes-API/)
  + [Flat Files API](/general/faq/Flat-Files-API/)
  + [Exchange Rates API](/general/faq/Exchange-Rates-API/)
  + [Node as a Service](/general/faq/Node-as-a-Service/)
  + [Enterprise Plan](/general/faq/Enterprise-Plan/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [FAQ](/general/faq/)
* Exchange Rates API

On this page

Exchange Rates API
==================

Welcome to the CoinAPI FAQ. We've grouped the most common customer questions by product to help you find quick, clear answers.

Tips for Navigating This FAQ[​](/general/faq/Exchange-Rates-API/#tips-for-navigating-this-faq "Direct link to Tips for Navigating This FAQ")
--------------------------------------------------------------------------------------------------------------------------------------------

* Use CTRL+F to search for terms like "order book", "Flat Files", or "credits".
* Bookmark docs.coinapi.io for full technical documentation.

Frequently Asked Questions[​](/general/faq/Exchange-Rates-API/#frequently-asked-questions "Direct link to Frequently Asked Questions")
--------------------------------------------------------------------------------------------------------------------------------------

### 1. What is Exchange Rate API?[​](/general/faq/Exchange-Rates-API/#1-what-is-exchange-rate-api "Direct link to 1. What is Exchange Rate API?")

The Exchange Rate API is a service offered by CoinAPI that provides real-time and historical exchange rate data for a wide range of cryptocurrencies and fiat currencies. This API is essential for developers and businesses that require accurate and up-to-date pricing information to power their applications, trading platforms, financial analytics, and more.

### 2. What affects cryptocurrency exchange rates?[​](/general/faq/Exchange-Rates-API/#2-what-affects-cryptocurrency-exchange-rates "Direct link to 2. What affects cryptocurrency exchange rates?")

Cryptocurrency exchange rates are influenced by a variety of dynamic factors, including:

* **Market Supply and Demand**: The most fundamental driver — prices rise when demand exceeds supply and fall in the reverse scenario.
* **News and Regulatory Developments**: Announcements about regulation, bans, or institutional adoption can significantly impact market behavior.
* **Network Events**: Hard forks, protocol upgrades, or changes in tokenomics (e.g., halvings) can alter perceived value and price.
* **Market Sentiment**: Public perception, social media trends, and investor confidence play a key role, especially in volatile markets.
* **Trading Volume and Liquidity**: Assets with higher liquidity tend to have more stable rates, while low-volume markets are more prone to price swings.
* **Macroeconomic Trends**: Inflation rates, interest rates, and broader financial market shifts (e.g., stock market moves or fiat currency fluctuations) can also impact crypto valuations.

These factors often interact in real-time, which is why CoinAPI aggregates data from multiple exchanges to help users monitor and respond to these influences with precision.

### 3. What are some common use cases of exchange rate data?[​](/general/faq/Exchange-Rates-API/#3-what-are-some-common-use-cases-of-exchange-rate-data "Direct link to 3. What are some common use cases of exchange rate data?")

Exchange rate data provided by CoinAPI serves a multitude of applications across various industries and applications:

1. Algorithmic and High-Frequency Trading
   * Traders use real-time exchange rate data to develop and deploy algorithmic trading strategies
   * High-frequency traders leverage discrepancies for arbitrage strategies
2. Financial Analysis and Research
   * Analysts utilize historical and real-time data to identify and analyze market trends
3. Portfolio Management
   * Portfolio managers use exchange rate data to accurately value cryptocurrency holdings
4. Risk Management
   * Monitoring exchange rates assists in assessing and mitigating currency volatility risks
5. Payment Processing
   * Businesses rely on up-to-date exchange rates for accurate currency conversion
6. DeFi Apps
   * DeFi platforms integrate exchange rate data for smart contracts functionality
7. Liquidity Pools
   * Accurate exchange rates help in managing liquidity pools
8. Tax Reporting
   * Historical exchange rate data aids in tax reporting compliance
9. Education
   * Used to create simulations and learning tools
10. Market Analysis Projects
    * Employed for academic projects and market analyses

### 4. What are the data delivery methods?[​](/general/faq/Exchange-Rates-API/#4-what-are-the-data-delivery-methods "Direct link to 4. What are the data delivery methods?")

We offer two API connections:

* REST API: For operations that can tolerate latency, used for historical data and account management
* WebSocket: For real-time applications, offering lower latency and continuous data streams

### 5. What are the exchange rates in crypto?[​](/general/faq/Exchange-Rates-API/#5-what-are-the-exchange-rates-in-crypto "Direct link to 5. What are the exchange rates in crypto?")

Exchange rates in cryptocurrency refer to the relative value or price of one cryptocurrency compared to another cryptocurrency or to fiat currencies. These rates are determined by:

1. Market supply and demand
2. Market depth and liquidity
3. Trading pairs

Most common reference rates:

* BTC/USD (Bitcoin to US Dollar)
* ETH/BTC (Ethereum to Bitcoin)
* ETH/USD (Ethereum to US Dollar)

### 6. What are the time periods I can use for Exchange Rates and OHLCV?[​](/general/faq/Exchange-Rates-API/#6-what-are-the-time-periods-i-can-use-for-exchange-rates-and-ohlcv "Direct link to 6. What are the time periods I can use for Exchange Rates and OHLCV?")

For Exchange Rates historical timeseries data:

| Time unit | Period identifiers |
| --- | --- |
| Second | 1SEC, 2SEC, 3SEC, 4SEC, 5SEC, 6SEC, 10SEC, 15SEC, 20SEC, 30SEC |
| Minute | 1MIN, 2MIN, 3MIN, 4MIN, 5MIN, 6MIN, 10MIN, 15MIN, 20MIN, 30MIN |
| Hour | 1HRS, 2HRS, 3HRS, 4HRS, 6HRS, 8HRS, 12HRS |
| Day | 1DAY, 2DAY, 3DAY, 5DAY, 7DAY, 10DAY |

You can get a full list of supported time periods at: <https://docs.coinapi.io/exchange-rates-api/rest-api-historical/timeseries-periods>

### 7. Why are there no Exchange Rates data for some assets for a given period?[​](/general/faq/Exchange-Rates-API/#7-why-are-there-no-exchange-rates-data-for-some-assets-for-a-given-period "Direct link to 7. Why are there no Exchange Rates data for some assets for a given period?")

Some assets can be supported at a particular date but not have Exchange Rates data available for a given period. This is because Exchange Rates data is produced from Quotes, Trades, and Metadata datasets. Quotes and Trades data are symbol-based, and some assets may not have symbols available yet for the queried period.

### 8. Why do exchange rates differ between platforms?[​](/general/faq/Exchange-Rates-API/#8-why-do-exchange-rates-differ-between-platforms "Direct link to 8. Why do exchange rates differ between platforms?")

Rate differences between exchanges occur due to:

* Different trading volumes and liquidity depths
* Geographic restrictions and regulations
* Fees and spread policies
* Local market conditions
* Arbitrage opportunities not yet balanced out

### 9. Can you provide proof or documentation of the source for CoinAPI’s exchange rates?[​](/general/faq/Exchange-Rates-API/#9-can-you-provide-proof-or-documentation-of-the-source-for-coinapis-exchange-rates "Direct link to 9. Can you provide proof or documentation of the source for CoinAPI’s exchange rates?")

CoinAPI maintains confidentiality of its proprietary data aggregation sources for the Exchange Rates API to ensure both security and performance consistency. While we don’t disclose each contributing source publicly, we follow strict quality control standards to deliver accurate, reliable, and consistent exchange rate data.

Need verified source transparency?

We recommend using our Indexes API, which:

* Provides detailed breakdowns of contributing markets and exchanges
* Uses transparent methodologies such as PRIMKT and VWAP
* Offers full documentation and historical insight into source composition and weighting

[VWAP Index Methodology Documentation](https://docs.coinapi.io/indexes-api/index-calculation-methodologies/vwap-index-methodology)

### 10. Do you have any insight or documentation on how you handle aggregation, especially with DEX data?[​](/general/faq/Exchange-Rates-API/#10-do-you-have-any-insight-or-documentation-on-how-you-handle-aggregation-especially-with-dex-data "Direct link to 10. Do you have any insight or documentation on how you handle aggregation, especially with DEX data?")

Yes, CoinAPI provides detailed documentation on how we perform rate aggregation, including methodologies that account for data from both centralized and decentralized exchanges (DEXs).

You can explore our aggregation algorithm and methodology here:

[Exchange Rates Aggregation Documentation](https://docs.coinapi.io/market-data/rest-api/exchange-rates/)

This resource outlines how we derive exchange rates, including how contributing exchanges are weighted and how outliers are filtered to produce robust and reliable aggregated rates.

If you're specifically looking at DEX data handling, please note that the inclusion depends on symbol availability and market activity from supported DEXs like Uniswap.

### 11. Do you have any details on how prices are aggregated from multiple exchanges like Coinbase, OKX, Binance, Bybit, and Kraken?[​](/general/faq/Exchange-Rates-API/#11-do-you-have-any-details-on-how-prices-are-aggregated-from-multiple-exchanges-like-coinbase-okx-binance-bybit-and-kraken "Direct link to 11. Do you have any details on how prices are aggregated from multiple exchanges like Coinbase, OKX, Binance, Bybit, and Kraken?")

Yes, we aggregate exchange rates using a Volume-Weighted Average Price (VWAP) over a 24-hour rolling window. This VWAP is calculated across multiple high-quality data sources listed on our platform, including major exchanges like Coinbase, OKX, Binance, Bybit, and Kraken. We carefully select and manage these sources to ensure the highest data quality.

Please note that:

* The Exchange Rates API is not available via FIX API.
* To access exchange rate data, you can choose from two alternatives:
  1. Realtime REST API
  2. WebSocket API

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

How to get an estimation for Flat Files data](/general/faq/Flat-Files-API/estimation-for-flat-files)[Next

Node as a Service](/general/faq/Node-as-a-Service/)

* [Tips for Navigating This FAQ](/general/faq/Exchange-Rates-API/#tips-for-navigating-this-faq)
* [Frequently Asked Questions](/general/faq/Exchange-Rates-API/#frequently-asked-questions)
  + [1. What is Exchange Rate API?](/general/faq/Exchange-Rates-API/#1-what-is-exchange-rate-api)
  + [2. What affects cryptocurrency exchange rates?](/general/faq/Exchange-Rates-API/#2-what-affects-cryptocurrency-exchange-rates)
  + [3. What are some common use cases of exchange rate data?](/general/faq/Exchange-Rates-API/#3-what-are-some-common-use-cases-of-exchange-rate-data)
  + [4. What are the data delivery methods?](/general/faq/Exchange-Rates-API/#4-what-are-the-data-delivery-methods)
  + [5. What are the exchange rates in crypto?](/general/faq/Exchange-Rates-API/#5-what-are-the-exchange-rates-in-crypto)
  + [6. What are the time periods I can use for Exchange Rates and OHLCV?](/general/faq/Exchange-Rates-API/#6-what-are-the-time-periods-i-can-use-for-exchange-rates-and-ohlcv)
  + [7. Why are there no Exchange Rates data for some assets for a given period?](/general/faq/Exchange-Rates-API/#7-why-are-there-no-exchange-rates-data-for-some-assets-for-a-given-period)
  + [8. Why do exchange rates differ between platforms?](/general/faq/Exchange-Rates-API/#8-why-do-exchange-rates-differ-between-platforms)
  + [9. Can you provide proof or documentation of the source for CoinAPI’s exchange rates?](/general/faq/Exchange-Rates-API/#9-can-you-provide-proof-or-documentation-of-the-source-for-coinapis-exchange-rates)
  + [10. Do you have any insight or documentation on how you handle aggregation, especially with DEX data?](/general/faq/Exchange-Rates-API/#10-do-you-have-any-insight-or-documentation-on-how-you-handle-aggregation-especially-with-dex-data)
  + [11. Do you have any details on how prices are aggregated from multiple exchanges like Coinbase, OKX, Binance, Bybit, and Kraken?](/general/faq/Exchange-Rates-API/#11-do-you-have-any-details-on-how-prices-are-aggregated-from-multiple-exchanges-like-coinbase-okx-binance-bybit-and-kraken)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.