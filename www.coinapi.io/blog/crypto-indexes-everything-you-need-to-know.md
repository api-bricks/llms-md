CoinAPI.io Blog - Crypto Indexes - Everything You Need to Know

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

October 03, 2024

Crypto Indexes - Everything You Need to Know
============================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F854b8889649e06fb56507cf9ce7585203da22a02-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

***Crypto indexes provide a way to measure and compare the overall performance of the cryptocurrency market or specific segments. Whether you're a seasoned investor or just dipping your toes into the crypto waters, indexes are your secret weapon for understanding market trends and movements and making smarter investment decisions. Indexes also let users reduce risk by investing in a diversified portfolio of cryptocurrencies.***

What Are Cryptocurrency Indexes?
--------------------------------

Crypto indexes are financial instruments that track the performance of a bundle of cryptocurrencies, similar to stock market indexes like the S&P 500 or NASDAQ Composite. To put it even more simply, imagine a basket of fruit.

You don't need to choose between apples and grapes or know which fruit gives you a particular vitamin, you need to know that fruits are healthy for you, so you buy them as a set. Think of crypto indexes in the same way. When investing in them, you don't need to care about every single coin, you just need to know whether the entire cryptocurrency market is growing or not.

Main Reasons to Use Indexes
---------------------------

### Accessibility

Indices make the cryptocurrency market more accessible to non-crypto investors by simplifying the investment process. They can invest in an index rather than researching and selecting individual cryptocurrencies.

### Risk Mitigation

Crypto indices allow investors to diversify their portfolios by investing in a basket of cryptocurrencies rather than individual assets. This helps in spreading risk and reducing the impact of volatility associated with single cryptocurrencies.

### Benchmarking

Indices serve as benchmarks for the performance of individual cryptocurrencies or portfolios. Investors can compare their returns against the index to gauge their performance.

### Liquidity

The existence of indices can improve market liquidity by attracting more investors, including institutional ones, who prefer diversified investment options.

Who Can Leverage Crypto Indexes To Make A Profit?
-------------------------------------------------

Of course, the main stakeholders are institutional investors who can generate huge returns with limited risk. But there are more interested in cryptocurrency indices.

### Fund managers

Fund managers can create index-based products like exchange-traded funds (ETFs) and mutual funds, providing more investment options to their clients. Moreover, they use crypto indexes as benchmarks to:

* Measure the performance of their actively managed crypto portfolios
* Compare their fund's returns against the broader market or specific segments
* Justify management fees by demonstrating outperformance (alpha) relative to the index
* Provide context for investors to understand how well the fund is performing

### Researchers And Analysts

As said before, indexes provide valuable data for analyzing market trends and sentiment, identifying correlations between different crypto assets or market segments, and understanding historical perspectives, which is essential for backtesting and developing trading strategies. Crypto index data can be used in academic studies on:

* Market efficiency in the crypto space
* Behavioral finance aspects of crypto investing
* Comparisons between traditional and crypto financial markets

### Developers

Developers can leverage crypto index data in various ways to build innovative FinTech applications like index platforms that provide insights, analytics, and investment options based on indexed data. Using [Indexes API](https://www.coinapi.io/indexes-api), developers can easily integrate data into their platforms, enhancing functionality and user experience. This way, they can create apps that:

* Calculate Value at Risk (VaR) based on index volatility
* Provide portfolio stress testing using historical index data
* Offer risk scoring for different crypto assets based on their correlation with indexes

Of course, the number of applications is much wider.

### Crypto Exchanges

Exchanges offer index-based trading products, attracting more users and increasing trading volumes. Besides, they use indexed data to provide better market insights and analytics to their users.

Obtaining Data From Crypto Index Providers
------------------------------------------

The easiest way to acquire crypto index data is to use a suitable API provider, such as CoinAPI. This choice comes with several benefits:

### Comprehensive Market View

The Indexes API aggregates data from multiple sources, providing a broad overview of market conditions. Now, we give you access to 13 data sources and track 7702 indexes with 2252 assets. This is particularly useful for everyone who needs a comprehensive view of the cryptocurrency market.

### Historical Data

The Indexes API provides access to historical index values and compositions, allowing users to analyze past market trends and make informed decisions. Also, traders and researchers use historical data to backtest trading strategies and investment models. This helps in validating the effectiveness of strategies before risking real capital. For example, they can:

* Calculate historical volatility over different periods
* Identify periods of high and low volatility
* Analyze how crypto assets correlate with each other or with traditional assets over time
* Estimate recovery times from significant market drops
* Study extreme market events and their frequency
* Analyze historical trading volumes alongside index movements

### Real-Time Data

With CoinAPI, index values are updated every 100ms. This high-frequency update ensures you're always working with the most current data, critical for time-sensitive trading strategies like [high-frequency trading](https://www.coinapi.io/blog/high-frequency-treading-strategies-in-crypto) and [statistical arbitrage](https://www.coinapi.io/blog/3-statistical-arbitrage-strategies-in-crypto), and real-time market analysis.

### Detailed Metadata

Each index comes with detailed metadata, including descriptions and associated IDs, which helps in better understanding and utilizing the data.

### Custom Index Creation

The Indexes API allows you to create custom indexes based on your specific criteria, offering flexibility and customization to meet investment strategies or research needs. You can include only the assets that align with your criteria, such as DeFi tokens, stablecoins, or a particular sector within the cryptocurrency market. Then, you should apply custom weighting methods which can help in performance evaluation and comparison.

You might also use customization when developing your financial product to attract investors looking for diversified investment options. Additionally, creating branded indexes will enhance your brand’s visibility and credibility in the marketplace.

Crypto Index Calculation
------------------------

Crypto indexes, such as those provided by CoinAPI, are typically calculated by tracking a selection of cryptocurrencies based on specific criteria, such as market capitalization. The index value is derived from the prices of the included cryptocurrencies, which are weighted according to their market cap or other factors. This allows the index to reflect the overall performance of the selected cryptocurrencies.

Index Calculation Methodologies
-------------------------------

CoinAPI incorporates two methods of calculating crypto indices:

### PRIMKT (Principal Market Price) Index Methodology

The PRIMKT Index Methodology is designed to provide a comprehensive and accurate representation of the market price for a given asset. It aggregates price data from 11 leading crypto exchanges, ensuring a broad market view. The methodology involves calculating a weighted average of prices, where weights are determined by the trading volume on each exchange. This approach helps in minimizing the impact of outliers and provides a more stable and reliable index value.

The calculation methodology involves:

1. **Exchange filtering:** exchanges without any trades in the Activity Period are excluded.
2. **Data collection:** for each eligible symbol, volume and last price data are collected from the remaining exchanges over the Lookup Period.
3. **Principal market determination:** for each symbol, the exchange with the highest trading volume is designated as the principal market.
4. **Index value calculation:** the index value for each symbol is set to the last traded price on its principal market during the Lookup Period.

If you looking for more detailed information such as a list of exchanges and assets, please refer to [the documentation](https://docs.coinapi.io/indexes-api/index-calculation-methodologies/primkt-index-methodology).

### VWAP (Volume-Weighted Average Price) Index Methodology

The VWAP Index Methodology calculates the average price of an asset over a specific period, weighted by the volume of trades. This method provides a more accurate reflection of the asset's true market value by considering both the price and the volume of trades. The calculation involves summing the products of each trade's price and volume, then dividing by the total volume of trades. This approach helps traders understand the average price at which an asset has traded, offering insights into market trends and liquidity.

1. **Data collection:** for each eligible symbol, query the average price and volume data from the proper exchanges over the last 24 hours.
2. **Symbol grouping:** group symbols according to their base and quote assets. Symbols with the same pairs of base and quote assets are grouped, regardless of order.
3. **Group calculations:** for each group:
   * Calculate the volume-weighted average price expressed in units of one asset from the pair.
   * Sum up the volumes of trades into a total volume.
4. **Price conversion:** Convert prices calculated for each group to be expressed in reference asset units:
   * Construct a graph where vertices symbolize assets and edges symbolize cumulative trades between pairs of assets.
   * Launch a Breadth-First Search (BFS) algorithm from the reference asset vertex:
     1. Set the depth of assets (reference and stable coin assets have a depth of 0).
     2. For each vertex at depth "k", process edges to vertices at depth "k-1":
        1. Filter edges to include only those with prices within 3 standard deviations of the average.
        2. Convert prices to be expressed in reference assets.
        3. Calculate the weighted average price for the vertex.

To learn more detailed information about VWAP, [read our documentation](https://docs.coinapi.io/indexes-api/index-calculation-methodologies/vwap-index-methodology).

How To Create Your Crypto Index?
--------------------------------

When you choose our Indexes API's enterprise plan, you can create your own indices. The process of creation involves several steps. Here’s a general outline:

### 1. **Get an API Key**

First, you must sign up for an API key from CoinAPI (choose Indexes API). You can do this by visiting https://www.coinapi.io/ and registering for an account.

### 2. **Understand the API Documentation**

Familiarize yourself with the CoinAPI [Indexes API documentation](https://docs.coinapi.io/indexes-api/).

### 3. **Define Your Index Criteria**

Determine the criteria for your index, such as the cryptocurrencies to include, the weighting method, and the calculation frequency.

### 4. **Use the API to Create the Index**

Use the CoinAPI Indexes API to create your index. You will need to make a POST request to the appropriate endpoint with the necessary parameters, such as the list of assets and their weights.

***Here is a simplified example of how you might create an index (note: this is a conceptual example):***

```
1POST /v1/indexes
2Host: rest.coinapi.io
3X-CoinAPI-Key: YOUR_API_KEY
4Content-Type: application/json
5
6{
7  "name": "My Custom Index",
8  "assets": [
9    {"symbol_id": "BITSTAMP_SPOT_BTC_USD", "weight": 0.5},
10    {"symbol_id": "BITSTAMP_SPOT_ETH_USD", "weight": 0.3},
11    {"symbol_id": "BITSTAMP_SPOT_LTC_USD", "weight": 0.2}
12  ]
13}
```

Key Takeaways
-------------

1. Crypto indexes provide a simplified way to measure and invest in the overall cryptocurrency market performance.
2. They offer benefits such as accessibility, risk mitigation, benchmarking, and improved liquidity.
3. Crypto indexes can benefit various stakeholders, including investors, fund managers, researchers, developers, and exchanges.
4. API providers like CoinAPI offer comprehensive, real-time, and historical data for creating and analyzing crypto indexes.
5. Two main calculation methodologies are used: PRIMKT and VWAP, each offering different perspectives on market pricing.
6. Custom indexes can be created using API services, allowing for tailored investment strategies and market analysis.

Do you need the most accurate historical and real-time crypto index data? Read more about the Indexes API, and don't hesitate to contact us!

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