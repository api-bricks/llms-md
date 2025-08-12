CoinAPI.io Blog - Crypto Exchange Rates API - The Ultimate Guide

**🚀 Metrics API V2 Live:**

Complete Market Intelligence - CEX + DeFi Data in One API

[Learn More](https://www.coinapi.io/blog/metrics-api-v2-trading-volume-analysis-and-on-chain-metrics)

[![background](https://cdn.sanity.io/images/o65xz72l/production/268144c90959611dea3e360f81e4549c3cd03fd0-142x34.svg)![background](https://cdn.sanity.io/images/o65xz72l/production/e0ca0c29b08cb53631d77de4a84246da316d55d2-142x34.svg)](/)

* Products
* Use Cases
* Pricing
* Developers
* Resources
* Contact us
* [Log in](https://console.coinapi.io/)

February 13, 2025

Crypto Exchange Rates API - The Ultimate Guide
==============================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F7ad2be1d531748a39c4c089f6e82e1eb05c81804-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

***In the wild wild world of crypto, keeping up to date with accurate exchange rates is crucial. No matter whether you are a trader, developer, a crypto business owner - it's important. When to buy Bitcoin? When to sell ETH? It's not investment advice, but Exchanger Rates might help you so much! Let’s dive into what crypto exchange rates are, why they matter, and how CoinAPI’s new [Exchange Rates API](https://docs.coinapi.io/market-data/rest-api/exchange-rates/) can help you get access to this vital information.***

What Are Cryptocurrency Exchange Rates?
---------------------------------------

Crypto exchange rates are the relative value of one cryptocurrency compared to another cryptocurrency or fiat currency (like USD or EUR). These rates are shaped by the interplay of market supply and demand, trading volumes and liquidity, current market sentiment, technical developments, regulatory news and macroeconomic conditions.

For example, when you see BTC/USD at 100,000, it means one Bitcoin is worth 100,000 US dollars. Common [trading pairs](https://www.coinapi.io/learn/glossary/trading-pair) include BTC/USD (Bitcoin to US Dollar), ETH/BTC (Ethereum to Bitcoin), and ETH/USD (Ethereum to US Dollar). Of course, there are other cryptocurrencies too.

![An illustration representing various cryptocurrency exchange rates.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F9b5c487e4288441dbe06ed1e549db7c354ec8d40-1344x768.png&w=1920&q=75)

Why Do Exchange Rates Differ Between Platforms?
-----------------------------------------------

You might notice that cryptocurrency prices can vary across different exchanges (not even mentioning differences between CEXs and DEXs). This is because of the unique characteristics of each platform’s trading environment. Trading volumes and liquidity depths, as well as geographic restrictions and regulations, play a big role in this.

Each platform has its own fee structure that affects pricing. Local market conditions and unbalanced arbitrage opportunities further contribute to these variations, creating a complex web of price differences across the cryptocurrency space.

Real-World Use Cases for Crypto Asset Exchange Rates
----------------------------------------------------

Exchange rate data has many practical applications across various industries. In the trading and investment space, it powers [algorithmic and high frequency trading](https://www.coinapi.io/blog/high-frequency-treading-strategies-in-crypto) systems and enables accurate portfolio valuation and management. Risk assessment and market trend analysis also rely heavily on exchange rate information.

Financial services benefit greatly from exchange rate data. Payment processors use it for currency conversion, while DeFi applications and [liquidity pool](https://www.coinapi.io/learn/glossary/liquidity-pool) managers depend on it for their core operations. The business and analytics sector uses it for financial reporting, tax compliance, market research and educational tools and simulations.

![An illustration representing various cryptocurrency exchange rates.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fa9b5374c6382b207263ad346a8c0bb7f09525d12-1344x768.png&w=1920&q=75)

CoinAPI's Cryptocurrency Exchange Rates API
-------------------------------------------

As [CoinAPI](https://www.coinapi.io/blog/what-is-coinapi-the-evolution-of-free-cyrpto-api) we have recently launched a new product - Exchange Rates API. It's a tool that provides full access to [cryptocurrency exchange rate](https://www.coinapi.io/blog/cryptocurrency-exchange-rates) data with many features. The service updates in real-time every 100ms and covers more than 2,252 assets. With over 20 terabytes of historical data spanning more than 14 years, you can get current and historical exchange rates through multiple delivery methods including [REST](https://docs.coinapi.io/exchange-rates-api/rest-api-historical/rest-api), [WebSocket](https://docs.coinapi.io/exchange-rates-api/websocket/), and [JSON-RPC](https://docs.coinapi.io/exchange-rates-api/jsonrpc-api) (more about it below👇).

### The Crypto Exchange Rates API Features

The API has multiple integrations to suit your needs. REST API is for basic use cases, WebSocket is for real-time data streaming and JSON-RPC is for more complex implementations.

We have coverage of over 350 exchanges and thousands of trading pairs for both cryptocurrency and fiat currencies. We have 99.9% SLA, [low latency](https://www.coinapi.io/blog/importance-of-low-latency-in-cryptocurrency-trading) data, and robust global infrastructure.

Your developers will love the extensive documentation, multiple SDKs, and support for multiple programming languages so implementation is easy no matter what your tech stack is.

Best Practices
--------------

When using exchange rate data in your app, couple of things to keep in mind. Data freshness is key, always verify the timestamp of the rate data to make sure it meets your requirements. Robust error handling for API responses and connection issues should be built in from the start.

[API rate limits](https://www.coinapi.io/learn/glossary/api-rate-limit) and proper throttling should be taken care of. And thorough validation of exchange rate data before using it in critical operations to prevent issues down the line.

### API Response - Examples

Enough talking! Let us show you how it actually works. Below is a list of example API responses for different requests - it gives a great picture of data clarity and quality we provide. If you want to learn more about the way we calculate the rates go to our [docs](https://docs.coinapi.io/exchange-rates-api)!

Check the Examples Out!

#### Specific Exchange Rate

This request gets the exchange rate for a specific base and quote asset at a given time or the current rate.

```
1{
2  "time": "2025-02-13T10:07:38.2687211Z",
3  "asset_id_base": "BTC",
4  "asset_id_quote": "USD",
5  "rate": 10000
6}
```

#### Explanation of Each Field:

* **`"time": "2025-02-13T10:07:38.2687211Z"`**   
  This is the timestamp the rate was recorded at. In this case 13th of February 2025. It's in ISO 8601 format and in Coordinated Universal Time (UTC) with the Z at the end. Useful for tracking when the rate was last updated so you can use the most recent data
* **`"asset_id_base": "BTC"`**   
  The base asset in the currency pair. In this case, Bitcoin (BTC) is the asset being compared. This is the cryptocurrency you are converting from.
* **`"asset_id_quote": "USD"`**  
  The quote asset in the currency pair. Here, the US Dollar (USD) is the asset being compared against. This is the currency you are converting to.
* **`"rate": 10000`**  
  The rate value. 1 BTC = 10,000 USD at this time. Use to convert BTC to USD. For example to convert bitcoin to US dollar multiply by this rate.

#### All Current Exchange Rate

This requests gets the current exchange rate between requested asset and all other assets.

```
1{
2  "asset_id_base": "BTC",
3  "rates": [
4    {
5      "time": "2017-08-09T14:31:37.0520000Z",
6      "asset_id_quote": "USD",
7      "rate": 3258.887541779804
8    },
9    {
10      "time": "2017-08-09T14:31:36.7570000Z",
11      "asset_id_quote": "EUR",
12      "rate": 2782.5255080599272
13    },
14    {
15      "time": "2017-08-09T14:31:36.7570000Z",
16      "asset_id_quote": "CNY",
17      "rate": 21756.295595926054
18    },
19    {
20      "time": "2017-08-09T14:31:36.7570000Z",
21      "asset_id_quote": "GBP",
22      "rate": 2509.602420379958
23    }
24  ]
25}
```

#### Explanation of Each Field:

* `"asset_id_base": "BTC"`   
  This is the base asset for which the rates are being provided. In this case, it’s Bitcoin (BTC). All rates are relative to Bitcoin. For example, the BTC/USD rate shows how much one Bitcoin is worth in US Dollars.
* `"rates":`   
  An array of rate objects. Each object in the array is a rate of the base asset (BTC) against a different quote asset.
* **`"time": "2017-08-09T14:31:37.0520000Z"`**   
  Timestamp when the USD rate was recorded. ISO 8601 in UTC.
* `"asset_id_quote": "USD"`   
  The quote asset against which BTC is being compared, which is the US Dollar.
* `"rate": 3258.887541779804`   
  The rate that 1 BTC is equal to approximately 3,258.89 USD at the time.

#### Timeseries Period

You can also get historical exchange rates of any asset pair, grouped into time periods.

**A full list of supported time periods that are available for requesting:**

* **Seconds**: 1SEC, 2SEC, 3SEC, 4SEC, 5SEC, 6SEC, 10SEC, 15SEC, 20SEC, 30SEC
* **Minutes**: 1MIN, 2MIN, 3MIN, 4MIN, 5MIN, 6MIN, 10MIN, 15MIN, 20MIN, 30MIN
* **Hours**: 1HRS, 2HRS, 3HRS, 4HRS, 6HRS, 8HRS, 12HRS
* **Days:** 1DAY, 2DAY, 3DAY, 5DAY, 7DAY, 10DAY

```
1[
2  {
3    "period_id": "1SEC",
4    "length_seconds": 1,
5    "length_months": 0,
6    "unit_count": 1,
7    "unit_name": "second",
8    "display_name": "1 Second"
9  },
10  {
11    "period_id": "30MIN",
12    "length_seconds": 1800,
13    "length_months": 0,
14    "unit_count": 30,
15    "unit_name": "minute",
16    "display_name": "30 Minutes"
17  },
18  {
19    "period_id": "10DAY",
20    "length_seconds": 864000,
21    "length_months": 0,
22    "unit_count": 10,
23    "unit_name": "day",
24    "display_name": "10 Days"
25  }
26]
27
```

#### Explanation of Each Field:

* **`"period_id": "1SEC"`**  
  This is a unique identifier for the time period. In this case "1SEC" means 1 second. Used as a parameter when requesting historical rate data to specify the granularity of the [data points](https://www.coinapi.io/learn/glossary/data-points). For example "1SEC" means [data should be aggregated](https://www.coinapi.io/learn/glossary/aggregated-data) every second.
* `"length_seconds": 1`   
  The length of the period in seconds. Useful for calculations or when programmatically handling different time intervals. In this case it means the period is 1 second.
* `"length_months": 0`   
  The length of the period in months. This period doesn't span months but this field is helpful for periods that do. For example a "6MON" period would have length\_months set to 6.
* `"unit_count": 1`   
  The count of the time unit specified in unit\_name. How many units make up the period. In this example it's 1 unit of the unit\_name.
* `"unit_name": "second"`   
  The name of the time unit for the period. So unit\_count refers to this. Here it's seconds.
* `"display_name": "1 Second"`   
  A human readable name for the period. Used in user interfaces, reports or documentation to display the period in a human friendly way. Helpful for users interacting with the data.

#### Timeseries Data

It gets the timeseries of the exchange rates between two assets.

```
1[
2  {
3    "time_period_start": "2016-01-01T00:00:00.0000000Z",
4    "time_period_end": "2016-01-01T00:01:00.0000000Z",
5    "time_open": "2016-01-01T00:00:00.0000000Z",
6    "time_close": "2016-01-01T00:00:00.0000000Z",
7    "rate_open": 430.586617904731,
8    "rate_high": 430.586617904731,
9    "rate_low": 430.586617904731,
10    "rate_close": 430.586617904731
11  },
12  {
13    "time_period_start": "2016-01-01T00:01:00.0000000Z",
14    "time_period_end": "2016-01-01T00:02:00.0000000Z",
15    "time_open": "2016-01-01T00:01:00.0000000Z",
16    "time_close": "2016-01-01T00:01:00.0000000Z",
17    "rate_open": 430.38999999999993,
18    "rate_high": 430.38999999999993,
19    "rate_low": 430.38999999999993,
20    "rate_close": 430.38999999999993
21  },
22  {
23    "time_period_start": "2016-01-01T00:02:00.0000000Z",
24    "time_period_end": "2016-01-01T00:03:00.0000000Z",
25    "time_open": "2016-01-01T00:02:00.0000000Z",
26    "time_close": "2016-01-01T00:02:00.0000000Z",
27    "rate_open": 430.6522189770523,
28    "rate_high": 430.6522189770523,
29    "rate_low": 430.6522189770523,
30    "rate_close": 430.6522189770523
31  }
32]
```

#### Explanation of Each Field:

* **`"time_period_start": "2016-01-01T00:00:00.0000000Z"`**   
  Start of the time period. ISO 8601 in UTC, Z at the end. The start of the range for which the rate data is aggregated.
* **`"time_period_end": "2016-01-01T00:01:00.0000000Z"`**  
  End of the time period. ISO 8601 in UTC. The end of the range, 1 minute in this case.
* **`"time_open": "2016-01-01T00:00:00.0000000Z"`**  
  First observed rate of the period. ISO 8601 in UTC. The opening rate of the asset for the period.
* **`"time_close": "2016-01-01T00:00:00.0000000Z"`**  
  Last observed rate of the period.
* **`"rate_open": 430.586617904731`**  
  Rate at time\_open. The initial rate for the period, for tracking the start value.
* **`"rate_high": 430.586617904731`**  
  Highest rate of the period. The peak rate for the period.
* **`"rate_low": 430.586617904731`**  
  Lowest rate of the period. The trough rate for the period.
* **`"rate_close": 430.586617904731`**  
  Rate at time\_close. The final rate for the period is for tracking the end value.

Get Exchange Rates API Now!
---------------------------

Crypto exchange rates are the backbone of the cryptocurrency ecosystem, from simple trades to complex financial applications. With CoinAPI’s Exchange Rates API, getting this data is easy and reliable so you can focus on building instead of managing data infrastructure. Whatever you’re building, a trading platform, portfolio management, or DeFi application, you need exchange rate data.

[CoinAPI](https://docs.coinapi.io/) has got you covered with all the crypto tools and infrastructure to get you that. Choose how you want to integrate.

#### [Let's Get in Touch!](https://www.coinapi.io/contact-us)

#### [Book a Call Now!](https://calendly.com/anyacoinapi/intro-call?month=2025-02)

![background](https://cdn.sanity.io/images/o65xz72l/production/e8a6b2e74f8d4106aca6ea9739a663190aadf694-40x40.svg)

Stay up-to-date with the latest CoinApi News.

Send

By subscribing to our newsletter, you accept our website terms and privacy policy.

### Recent Articles

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F1c608fa1f94b18e18e30a04e3006c5455b4dfeca-1000x500.png&w=3840&q=75)

Product Features

How to Get Accurate Historical Token Price Data for Financial Reporting

Retrieve complete, audit-ready historical token price data with CoinAPI. Perfect for finance managers, controllers, and ops teams handling Web3 assets.](/blog/historical-token-price-data-financial-reporting)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fabe93ecc9d8dfb15701c7ab459b916701aaf13e1-1000x500.png&w=3840&q=75)

Crypto Knowledge

Spot Trading in Crypto: What It Is, How It Works, and How to Master It

Learn spot trading in crypto from basics to pro strategies. Understand bids, asks, order books & use CoinAPI’s real-time and historical data.](/blog/spot-trading-in-crypto-guide)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ffee6e77e8c599cbdc3e536317ac7adcbbbb59f5e-1000x500.png&w=3840&q=75)

Crypto Knowledge

Understanding Crypto Market Data: From Tick Trades to OHLCV and Order Books

Choose the right crypto market data type - tick trades, quotes, order books, or OHLCV—for trading success. Complete guide with examples and use cases. Focus keyphrase: crypto market data](/blog/understanding-crypto-market-data-tick-trades-ohlcv-order-books)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F8c92ab519a2ec5af8b7edc3ba2371d9243750cc7-1000x500.png&w=3840&q=75)

Product Features

Crypto Tax Made Simple: How CoinAPI Exchange Rates Power Accurate Accounting

Solve crypto tax compliance with professional exchange rates API. Get audit-ready historical pricing, eliminate capital gains errors, and standardize crypto pricing across exchanges.](/blog/crypto-tax-coinapi-exchange-rates)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fa7ddd03200081ffce3dfdd9d9bc805c4cbac5801-1000x500.png&w=3840&q=75)

Crypto Knowledge

What Everyone Gets Wrong About L3 Data in Crypto

L3 data in crypto gives you full visibility into every individual order — but most traders use it wrong. Learn how to read L3 correctly, avoid common pitfalls, and scale smarter with CoinAPI.](/blog/what-everyone-gets-wrong-about-l3-data-in-crypto)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fab2a315d6528b49cda3fd200b418af97ce48894f-1000x500.png&w=3840&q=75)

Crypto Knowledge

How Level 3 Market Data Transforms Trading Performance

What if you could see every individual order placement, modification, and cancellation happening in real-time across crypto exchanges? Most traders operate blindfolded with basic price feeds, while sophisticated institutions access Level 3 market data—granular, order-by-order intelligence that reveals market microstructure 99% of traders never see.](/blog/how-level-3-market-data-transforms-trading-performance)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F47694398be69f125e8bc4fcd68c23cba8ad4f7e2-1000x500.png&w=3840&q=75)

Product Features

Pros and Cons of JSON-RPC and REST APIs Protocols

Choose the right API protocol for crypto trading. Compare JSON-RPC vs REST for market data, trading bots, and DeFi applications with real performance benchmarks.](/blog/pros-and-cons-of-json-rpc-and-rest-apis-protocols)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ff4583e287f8949afaddc3a4aaf89091f834a8bd6-1000x500.png&w=3840&q=75)

Use case

Exchange Rates API for Fast Historical Token Prices

Exchange rates API for finance managers at Web3 companies. Get fast historical closing prices, multiple symbols per call, and ISO timestamps for compliance.](/blog/exchange-rates-api-for-fast-historical-token-prices)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fecfd635f082d4e6a312b9312725cf195c5d9dccd-1000x500.png&w=3840&q=75)

Crypto Knowledge

Why Crypto to Fiat APIs Are Revolutionizing Financial Operations

Discover how crypto-to-fiat APIs solve critical business challenges in portfolio management, tax compliance, and financial reporting. Learn why leading finance teams are standardizing on professional-grade solutions.](/blog/why-crypto-to-fiat-apis-are-revolutionizing-financial-operations)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fe7526651c2ce24101581e90a5982c62bb1b84f18-1000x500.png&w=3840&q=75)

Product Features

Metrics API V2: Trading Volume Analysis and On-Chain Metrics

Most crypto APIs show you prices on exchanges. But that’s only half the story. CoinAPI’s new Metrics API V2 gives you real-time visibility into DeFi protocols, stablecoin flows, and cross-chain activity — the $200B+ blind spot in traditional market data. With sub-30 second updates, standardized metrics, and multi-chain coverage, it's the fastest way to unlock on-chain trading signals, measure TVL, and track stablecoin health. If you’re still trading without it, you're flying blind.](/blog/metrics-api-v2-trading-volume-analysis-and-on-chain-metrics)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb5471406ca9cbf8f906574131747c4233f29e240-1000x500.png&w=3840&q=75)

Product Features

Crypto Data Download: The Flat Files Advantage

Discover how to download crypto data for free and access premium bulk historical datasets. Compare APIs, learn S3 methods, and start backtesting with terabytes of clean cryptocurrency market data.](/blog/crypto-data-download-the-flat-files-advantage)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fca54fa639768f18864c62215de750ec797f31ddd-1000x500.png&w=3840&q=75)

Product Features

Why WebSocket Multiple Updates Beat REST APIs for Real-Time Crypto Trading

Learn why WebSocket multiple updates for crypto trading APIs provide faster signals than single response data. Discover real-time OHLCV implementation strategies for Bitcoin and cryptocurrency market data.](/blog/why-websocket-multiple-updates-beat-rest-apis-for-real-time-crypto-trading)

### Crypto API made simple: Try now or speak to our sales team

[Start for Free](/market-data-api/pricing)[Get in Touch](/contact-us)

[![background](https://cdn.sanity.io/images/o65xz72l/production/99475f0760777c30125556b2707e1e8f77f2fba0-179x42.svg)](/)

###### Join our newsletter

* [![X](https://cdn.sanity.io/images/o65xz72l/production/89a93ecdd3eaa62f0d2bad091ff6d92a31e9c372-28x28.svg)](https://twitter.com/realcoinapi "X")
* [![Linkedin](https://cdn.sanity.io/images/o65xz72l/production/be666e8656abe83e43c1db9a3ab76d44b9af5cb5-28x28.svg)](https://www.linkedin.com/company/coinapi "Linkedin")
* [![Github](https://cdn.sanity.io/images/o65xz72l/production/80703d2d9baaef7e7f5471a54a720b9383a63aab-28x28.svg)](https://github.com/coinapi/coinapi-sdk "Github")
* [![T.me](https://cdn.sanity.io/images/o65xz72l/production/39be23a1db383ad12c3e9d4bebae9bc77bf59b8b-28x28.svg)](https://t.me/coinapiofficial "T.me")
* [![Discord](https://cdn.sanity.io/images/o65xz72l/production/9862f060f9b89536f18d4e8770a11bfb00c3e3fd-30x28.svg)](https://discord.gg/vgJbjjsVaC "Discord")
* [![Reddit](https://cdn.sanity.io/images/o65xz72l/production/d02e41d1eab87d289f2bc6a390bcd0c7def1b7ac-30x28.svg)](https://www.reddit.com/r/CoinAPI/ "Reddit")
* [![YouTube](https://cdn.sanity.io/images/o65xz72l/production/535425f0f99df8b6173d663721f8941430d637b2-28x28.svg)](https://www.youtube.com/@CoinAPI_Official "YouTube")
* [![G2](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F4b1d455c2cab4bf625e7cc96a1b74695c0b3c4bc-28x28.png&w=64&q=75)](https://www.g2.com/products/coinapi/reviews "G2")

###### Products

###### Products

* [Market Data API](/products/market-data-api)
* [Indexes API](/products/indexes-api)
* [EMS Trading API](/products/ems-api)
* [Flat Files](/products/flat-files)
* [Exchange Rates API](/products/exchange-rates-api)
* [Exchange Link](https://www.coinapi.io/products/exchange-link)

###### CoinAPI.io

###### CoinAPI.io

* [Home](https://www.coinapi.io/)
* [API Docs](https://docs.coinapi.io/?_gl=1*jgom05*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Blog](https://www.coinapi.io/blog)

###### Help

###### Help

* [Contact sales](/contact-us)
* [Contact support](https://console.coinapi.io/?link=/support-tickets)
* [How-to Guides](https://docs.coinapi.io/market-data/how-to-guides/?_gl=1*16m3ndl*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [FAQ](https://docs.coinapi.io/general/faq/?_gl=1*dfjpiw*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Metadata Explorer](https://docs.coinapi.io/market-data/metadata-tables/introduction)

###### Developers

###### Developers

* [Helper Libraries](https://github.com/api-bricks/api-bricks-sdk/)
* [API Documentation](https://docs.coinapi.io/?_gl=1*iuavdb*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Status Page](https://status.coinapi.io/?_gl=1*1ww1bbe*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)

###### Legal

###### Legal

* [Terms of service](/legal#terms)
* [Acceptable Usage Policy](/legal#aup)
* [Privacy Policy](/legal#policy)

###### API Bricks brands

###### API Bricks brands

* [FinFeedAPI](https://finfeedapi.com/?utm_source=coinapi.io&utm_medium=referral&utm_campaign=footer)

![background](https://cdn.sanity.io/images/o65xz72l/production/5f005fa1cc9dc85c59ae054bb4a4838566b65c4e-25x26.svg)Copyright 2025 API BRICKS LTD F/K/A COINAPI LTD or its affiliates. All rights reserved.