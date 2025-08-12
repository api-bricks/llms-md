CoinAPI.io Blog - CoinAPI's Crypto Order Book Data: A Look at Tick-Level Information

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

July 19, 2023

CoinAPI's Crypto Order Book Data: A Look at Tick-Level Information
==================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F66d2803b7d0116701f989d51152979ea9de02c62-1200x671.png%3Frect%3D0%2C75%2C1200%2C522%26w%3D920%26h%3D400&w=1920&q=75)

***Today, we dive into the depths of CoinAPI’s tick-level [Order Book](https://www.coinapi.io/learn/glossary/order-book) data and how it enhances trading strategies across the board. From providing a holistic view of current market conditions with Level 1 (L1) data to the granular details of individual orders with Level 3 (L3) data, our is equipping traders with comprehensive tools to [navigate the crypto](https://www.coinapi.io/use-case/coinapi-for-crypto-investments) seas.***

***This comprehensive guide explores the advantages and use cases of CoinAPI’s tick-level order book data, setting the stage for informed decision-making and effective strategy implementation. Understanding how to obtain order book data is essential for uncovering market opportunities and optimizing trading strategies in a highly volatile market.***

Introduction to Order Books
---------------------------

Order books are a crucial component of cryptocurrency trading platforms, providing a real-time, dynamic list of buy and sell orders for a specific cryptocurrency, organized by price level. Understanding order books is essential for traders, analysts, and developers in the crypto market, as they offer insights into market dynamics and trends. By analyzing the order book, market participants can gauge the supply and demand for a cryptocurrency, identify potential price movements, and make informed trading decisions.

### What is an Order Book?

An order book is a continuously updated list of buy and sell orders for a specific cryptocurrency, organized by price level. It displays the number of tokens being bid on or offered at each price point, providing a snapshot of market supply and demand. Order books are central to nearly every trade, and accurate [crypto order book](https://www.coinapi.io/blog/order-book-data-in-crypto) data is crucial for predicting price movements and optimizing trading strategies. By examining the order book, traders can identify the levels at which there is significant buying or selling interest, helping them to anticipate potential support and resistance levels.

### Key Components of Order Book Data

Order book data consists of several key components, including:

* **Buy orders**: The number of tokens being bid on at each price point, indicating the demand side of the market.
* **Sell orders**: The number of tokens being offered at each price point, representing the supply side of the market.
* **Quantity of tokens available at each price point**: The total number of tokens available at each price level, providing a measure of [market depth](https://www.coinapi.io/learn/glossary/market-depth).
* **Market depth**: The total number of tokens available at each price level, offering insights into the liquidity of the market.
* **Spread**: The difference between the best bid and ask prices, indicating the cost of executing a market order.
* **Liquidity**: The ability to buy or sell a cryptocurrency without significantly affecting its price, crucial for large trades.

Understanding these components helps traders to assess the overall market conditions, identify potential trading opportunities, and manage their risk effectively.

Order Book Data Level 1: Bids and Asks Data
-------------------------------------------

At the most basic level (Level 1, L1), [CoinAPI](https://docs.coinapi.io/) provides traders with real time market data, including the best bid and best ask prices for a given trading pair’s order book. This real-time “quote” data is essential for understanding the current market conditions and the prices at which buyers and sellers are willing to transact. By subscribing to CoinAPI’s Level 1 quote data, traders gain access to real-time updates on the best bid and ask prices, along with the associated order amounts.

CoinAPI’s L1 data is accessible through their REST [API and WebSocket](https://docs.coinapi.io/market-data/websocket/), ensuring that traders can receive real-time updates in a format that suits their needs. Whether you prefer the simplicity of REST API or the efficiency of WebSocket, CoinAPI has you covered.

Order Book Data Level 2: Market Depth Data
------------------------------------------

While L1 data provides valuable insights into the best bid and ask prices, CoinAPI’s Level 2 (L2) data takes it further by offering a more granular view of the order book. L2 data includes all bids and asks at different price levels, providing traders with a comprehensive understanding of the market depth. Monitoring fluctuations in market orders is crucial to gauge liquidity and trading activity.

In cryptocurrency markets, market makers play a vital role by placing limit orders at price levels that differ from the current market price. CoinAPI’s L2 data aggregates all the bids and asks placed by these market makers, grouped by price level. This “depth of book” data allows traders to visualize the order book beyond the best bid and ask prices and gain insights into the buy and sell orders at various price levels.

**Order Book Data Level 3: Market by Order Data**
-------------------------------------------------

For the most sophisticated traders, CoinAPI offers Level 3 (L3) data, which provides even deeper insights into the order book. L3 data includes non-aggregated bids and asks placed by individual market makers, enabling traders to access every individual order and its associated amount.

L3 data can be used to analyze different trading pairs and their market dynamics, helping traders develop strategies by comparing order books across various exchanges. While L2 data aggregates bids and asks by price level, L3 data breaks down the order book into individual data points, resulting in a more detailed view of the market. This “market by order” data offers traders unparalleled visibility into the order book, allowing them to identify specific market dynamics and potentially gain an edge in their trading strategies.

It’s important to note that L3 data is typically used by advanced traders who require a high level of precision and detail. While L1 and L2 data may suffice for many traders, the availability of L3 data through CoinAPI demonstrates their commitment to catering to the needs of all market participants.

Cryptocurrency exchanges that CoinAPI offers Level 3 data from are:

* `BITSO`
* `COINBASE`
* `POLONIEXFTS`
* `SEEDCX`

Order Book Data Examples
------------------------

Below you'll find examples of Order Book Data records obtained from CoinAPI's Market Data API.

![CoinAPI's Tick-Level Order Book Data - example](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fc7ce5f5a53fc701beef99341b06884db1f32c2e5-768x727.webp&w=1920&q=75)

An example of an order book snapshot from [Binance](https://www.binance.com/). Asks section

![Order Book Data - example](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fc0f780b02160a135f4be17f050a3a719dd00da8b-768x723.webp&w=1920&q=75)

An example of an order book snapshot from Binance. Bids section

**CoinAPI's High-frequency Order Book Data**
--------------------------------------------

It is one thing to collect order book data, it is another to deliver it in the clearest and most accessible form possible. Here’s what we do at CoinAPI to make sure you get the data the way you like it.

### Collection of Historical Data

Ticks are gathered from each exchange’s L3 WebSocket or FIX channel. CoinAPI is sending a request to the REST API to get a current snapshot of the order book data. This snapshot represents a specific point in time and includes all current buy (bid) and sell (ask) orders in the market. Over time, as trades are executed, and new orders are added or old ones removed, the local version of the order book data can become out of sync with the real, current state of the market on the exchange.

[Historical order book data](https://docs.coinapi.io/market-data/rest-api/order-book/historical-data) is significant for backtesting trading strategies and analyzing market trends. This data, available since 2017, aids traders in making informed decisions based on past market behavior.

After retrieving the snapshot, CoinAPI updates its local version of the order book. They “replay” all the changes that happened since the last snapshot to bring the local order book back into sync with the actual state of the market on the exchange. This approach helps ensure that CoinAPI’s local order book data remains accurate and up-to-date, which is crucial for our customers who rely on this [data for their trading](https://dataproducts.coinapi.io/products/coinapi-crypto-spot-data-global-spot-markets-trades-oh-coinapi) strategies.

### **Data standardization**

We have opted to normalize the data because of the considerable formatting disparities among different exchanges. Each raw data packet collected comprises information about the individual bid or ask set by the market maker. CoinAPI format supports L2 and L3 data in the same file. This means that CoinAPI's data format can accommodate both Level 2 and Level 3 order book data in the same file. Level 2 data provides all the bids and asks at different price levels, while Level 3 data includes non-aggregated bids and asks placed by individual market makers.

The data file begins with a snapshot of the order book at a particular moment in time. The snapshot includes the current state of all open orders in the market. After the snapshot, the file includes updates to the order book. These updates represent changes to the order book after the snapshot was taken. Updates could include new orders being placed, existing orders being filled or canceled, and so on.

This format is beneficial because it allows the user to see the state of the order book at a specific moment (via the snapshot) and then track how the order book changes over time (via the updates). It provides a comprehensive view of the market dynamics, which can be useful for various trading strategies.

> Read more: [Crypto data standardization – the key to making insight-based decisions](https://www.coinapi.io/blog/crypto-data-standardization-the-key-to-making-insight-based-decisions)

### **File Structure**

CoinAPI organizes its data files based on the trading symbol and the day. This means that for each trading pair (like BTC-USD) and for each day, there's a unique data file. In each of these files, the data starts with a snapshot of the order book at the beginning of the day and then includes updates to the order book as they happen throughout the day. This format provides a detailed overview of how the order book changes over a day.

CoinAPI's advantage is that it combines the snapshot and the updates in one single file, rather than having them in separate files. This makes the data easier to manage and convert to different formats. Our competitors do not combine the snapshot and updates in one file but keep them separate. This can make the data more difficult to manage and analyze.

### **Delivery**

CoinAPI provides data daily, and this data is for the previous day's trading activity. The ‘day' for which data is provided is determined according to Coordinated Universal Time (UTC). This is important for standardizing the data across different geographical locations and time zones. There are various methods by which users can receive or access the data. Data is delivered through AWS, GCP, or S3 API.

Summarizing, unlike the competition, CoinAPI provides data that is already arranged in the correct order within each file. This makes the process of analyzing the data more straightforward because users do not need to piece together updates from different snapshot files. Instead, they can simply read a single file from start to finish to understand the chronological order of updates. This is a great advantage over other services, where updates

Accessing Order Book Data
-------------------------

Accessing order book data is crucial for traders, analysts, and developers in the crypto market. There are several ways to access order book data, including [exchange APIs](https://docs.coinapi.io/market-data/rest-api/exchange-rates/), third-party providers, and web scraping. Each method has its advantages and challenges, but the goal is to obtain accurate and reliable data to inform trading decisions.

### Cryptocurrency Exchange APIs and Third-Party Providers

Cryptocurrency exchanges, such as Binance and Coinbase, offer APIs that provide programmatic access to order book data. These APIs often offer real-time updates and historical data, allowing traders to monitor market conditions and backtest trading strategies. However, integrating with dozens or hundreds of exchanges separately can be costly and time-consuming. A more effective solution is to use third-party data providers, such as CoinAPI, which aggregate data from multiple exchanges and provide a single point of access for diverse market information. This approach simplifies order book data collection and ensures consistency across different sources.

Third-party data providers, such as CoinGecko and CryptoCompare, also offer access to order book data, providing a comprehensive view of market conditions and trends. These providers often offer historical data, allowing traders and analysts to backtest trading strategies and evaluate their effectiveness.

In addition to exchange APIs and third-party providers, web scraping can be an alternative method for collecting order book data from exchanges that do not provide APIs. However, this method involves extracting information directly from the exchange’s website and can be time-consuming and prone to errors.

Trading platforms, such as MetaTrader and TradingView, often integrate order book data for popular cryptocurrencies, providing a graphical interface for traders to analyze market conditions and trends.

Overall, accessing order book data is crucial for traders, analysts, and developers in the crypto market. By using exchange APIs, third-party providers, or web scraping, market participants can gain valuable insights into market dynamics and trends, and make informed decisions based on accurate and reliable data.

**CoinAPI's Tick-Level Order Book Data: Advantages**
----------------------------------------------------

CoinAPI's tick-level order book data provides several distinct advantages for traders:

* **Granularity:** With access to L1, L2, and L3 data, traders can choose the level of granularity that best suits their trading strategies. Whether you prefer a broad overview of market conditions or a deep dive into individual order details, CoinAPI has you covered.
* **Real-time Updates:** By leveraging CoinAPI's REST API or WebSocket, traders can receive real-time updates on order book data, ensuring that they have the most up-to-date information at their disposal. This real-time data is crucial for making informed trading decisions in fast-paced cryptocurrency markets.
* **Market Depth Analysis:** CoinAPI's L2 data allows traders to analyze the depth of the order book beyond the best bid and ask prices. By visualizing the buy and sell orders at different price levels, traders can identify areas of significant support or resistance, helping them determine optimal entry and exit points.

Trading Strategies for CoinAPI's Tick-Level Order Book Data
-----------------------------------------------------------

CoinAPI's tick-level order book data can be utilized in various trading scenarios:

* **Algorithmic Trading:** [High-frequency trading strategies](https://www.coinapi.io/blog/high-frequency-treading-strategies-in-crypto) can benefit from CoinAPI's tick-level data, as it allows for precise order placement and execution based on real-time market conditions.
* **Arbitrage Opportunities:** By analyzing the order book depth across different exchanges, traders can identify arbitrage opportunities and profit from price discrepancies.
* **Market Making:** Market makers can leverage CoinAPI's L2 data to assess market conditions, identify areas of liquidity, and optimize their order placement strategies.
* **Risk Management:** In volatile markets, having access to granular order book data can help traders manage their risk effectively. By monitoring changes in market depth, traders can adjust their positions accordingly and minimize potential losses.

**Conclusion**
--------------

Understanding order book data is essential for successful trading in cryptocurrency markets. Whether you prefer the simplicity of L1 quote data or the intricacy of L3 market-by-order data, CoinAPI offers a comprehensive solution to cater to traders of all levels.

**Dive deeper into the specifics of our data offerings by exploring [our detailed documentation.](https://docs.coinapi.io/market-data/rest-api/order-book) There you will find in-depth technical details that can further enhance your understanding and utilization of our data.**

**Ready to experience the power of CoinAPI firsthand? Take the next step and [try our API for free](https://www.coinapi.io/market-data-api/pricing). You'll get a firsthand experience of how our robust data can elevate your cryptocurrency trading strategies to new heights. Don't wait, start your journey with CoinAPI today!**

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