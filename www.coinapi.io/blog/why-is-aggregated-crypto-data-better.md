CoinAPI.io Blog - Why is Aggregated Crypto Data Better?

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

July 04, 2024

Why is Aggregated Crypto Data Better?
=====================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fd4bcdaf917de12fdc664a544d255449109902ce5-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

***Some time ago we wrote blog posts about [crypto data filtering](https://www.coinapi.io/blog/filter-your-crypto-data) and [crypto data standardization](https://www.coinapi.io/blog/crypto-data-standardization-the-key-to-making-insight-based-decisions) – now it’s time to tell you more about [crypto data](https://www.coinapi.io/blog/how-to-get-historical-and-real-time-crypto-data) aggregation. A great process that allows traders to have a better overview of the [crypto market and make](https://www.coinapi.io/blog/market-making-in-crypto) even better decisions and trades. Crypto [data aggregation](https://www.coinapi.io/learn/glossary/aggregated-data) plays a crucial role in the evolving landscape of decentralized finance.***

***A decentralized exchange (DEX) aggregator is a vital tool in DeFi, optimizing trading conditions by pooling liquidity from various decentralized exchanges to enhance price accuracy and reduce slippage, while maintaining user custody over funds. What is it exactly? What are its pros and cons? How’s CoinAPI’s [Market Data API](https://docs.coinapi.io/market-data/) dealing with it? Let’s dig into it!***

**What is Data Aggregation?**
-----------------------------

Simply put, it’s collecting and mixing data from many places. This aggregated data includes various digital assets, providing a comprehensive view of the cryptocurrency market. This creates a big picture that’s easy to understand. As a result, it helps with making decisions and creating reports.

Definition of Aggregated Crypto Data
------------------------------------

Aggregated crypto data refers to the process of collecting and combining data from various decentralized exchanges (DEXs) and [centralized exchanges](https://www.coinapi.io/learn/glossary/centralized-exchange-cex) (CEXs) to provide a comprehensive view of the cryptocurrency market. This data encompasses a wide range of market data, including prices, trading volumes, and liquidity, as well as other pertinent information such as news and events.

By [pooling liquidity](https://www.coinapi.io/learn/glossary/liquidity-pool) and data from multiple exchanges, aggregated crypto data offers a holistic perspective that is invaluable for investors, traders, and researchers. It enables them to gain deeper insights into the market dynamics and make well-informed decisions.

What are Crypto Data Aggregators?
---------------------------------

### Definition and Explanation

Crypto data aggregators are platforms designed to collect and combine market data from various decentralized exchanges (DEXs), centralized exchanges (CEXs), and other relevant sources. By leveraging advanced algorithms and smart contracts, these platforms provide users with a comprehensive view of the cryptocurrency market. This includes real-time market data, detailed analytics, and other essential information that aids in making informed investment decisions.

In the decentralized finance (DeFi) ecosystem, crypto data aggregators play a pivotal role by offering a single interface to access data from multiple exchanges and liquidity pools. This not only simplifies the user experience but also reduces the complexity associated with navigating various platforms. As a result, trading and investing in the crypto market becomes more efficient and streamlined.

**How does data aggregation work?**
-----------------------------------

First, we gather data from various sources. Next, we clean it up to make sure it’s accurate. Smart contracts can be used to automate the data aggregation process, ensuring accuracy and efficiency. Then, we combine all the data into one set. After that, we organize it for easy use. Finally, we sum it up to give useful insights.

Why is aggregated data from multiple exchanges better than single-source data?
------------------------------------------------------------------------------

* **Makes analysis easier:** Summarized data helps identify trends, patterns, and anomalies across many data sources. Consequently, it’s less likely to be false.
* **Improves decision-making:** Aggregated data provides a complete view, thus aiding informed decisions. Furthermore, it allows you to see the overview of the whole market. In contrast, a single data source could give out wrong data. Therefore, using aggregated data is safer for most. Additionally, aggregated data helps in analyzing transaction fees across various exchanges, aiding in cost-efficient decision-making.
* **Enhances reporting:** Aggregated data is perfect for reports and dashboards, thereby giving stakeholders a clear overview of key metrics.
* **Increases efficiency:** Managing a single, consolidated dataset is more efficient than dealing with multiple disparate sources.

Improved Market Insights
------------------------

Aggregated crypto data provides enhanced market insights by consolidating a vast array of data from multiple sources into a single, accessible platform. This comprehensive approach allows users to analyze market trends, identify patterns, and make more informed investment decisions.

With access to detailed analytics from various exchanges, users can pinpoint opportunities and assess risks more effectively. Additionally, staying up-to-date with the latest developments in the crypto world becomes easier, as aggregated data includes the latest crypto news and events, ensuring that users are always informed about the market’s pulse.

Increased Efficiency
--------------------

Aggregated crypto data significantly boosts efficiency by automating the collection and analysis of data from multiple sources. This automation not only saves time but also minimizes the risk of errors, allowing users to concentrate on making informed investment decisions.

By streamlining workflows, aggregated data helps users enhance their overall productivity. Instead of manually gathering and processing data from various exchanges, users can rely on a single, consolidated dataset that provides all the necessary information at their fingertips.

Crypto Market Data Aggregation
------------------------------

In crypto trading, we collect and organize data from many exchanges. DEX aggregators play a crucial role in consolidating [trading data](https://dataproducts.coinapi.io/products/coinapi-crypto-spot-data-global-spot-markets-trades-oh-coinapi) from various decentralized exchanges, providing traders with optimal trading conditions. As a result, this helps traders make informed choices based on solid information.

**Let us show you how crypto data is aggregated using our [Market Data API](https://www.coinapi.io/blog/how-to-use-the-market-data-api-for-analytics-and-financial-institutions) as an example.**

**CoinAPI's Market Data API Aggregation Process**
-------------------------------------------------

**1. Data Collection:** Firstly, our Market Data API connects to multiple cryptocurrency exchanges to collect market data. Subsequently, the raw market data is continuously ingested, including trades, quotes, and [order book](https://www.coinapi.io/learn/glossary/order-book) updates, from these exchanges in real time. Additionally, the API aggregates data from various liquidity pools, ensuring comprehensive market coverage.

**2. Data Normalization:** Secondly, the API converts raw data into a single, standardized format. This involves mapping different data structures and terminologies to a common schema. Then, it removes inconsistencies, duplicates, or errors to ensure accuracy and reliability.

**3. Timestamp Alignment:** Thirdly, Market Data API aligns timestamps from different exchanges to a common time standard (e.g., UTC) for accurate comparison and aggregation.

**4. Data Aggregation:** Data Aggregation: Next, the API computes aggregated metrics like average prices and total volumes. After that, it generates Open, High, Low, Close, and Volume ([OHLCV](https://www.coinapi.io/blog/understanding-ohlcv-in-market-data-analysis)) data for different time intervals.

**Some of the data types our Market Data API provides are:-Trades:** Individual transactions on the exchange. **-[Order Books](https://docs.coinapi.io/market-data/rest-api/order-book/):** Current buy and sell orders. **-[OHLCV](https://www.coinapi.io/learn/glossary/ohlcv):** Data showing the open, high, low, and close prices, and volume for a given period. **-Exchange Rates:** Rates between different asset pairs.

**5. Data Storage:** Furthermore, we store aggregated and normalized data in a structured database for efficient retrieval. Additionally, we don’t forget about historical data which is maintained as a comprehensive historical database to support backtesting and analysis.

**6. Data Distribution:** Market Data API provides access to aggregated data through various API endpoints (RESTful, WebSocket, FIX). We offer real-time streaming of market data for live updates, as well.

`💡 Batch Downloads:* Our Market Data API allows batch downloads of historical data for extensive analysis.*`

**7. Quality Assurance:** We constantly monitor data collection and aggregation processes to ensure data quality. Of course, we implemented robust error handling and recovery mechanisms to prevent any issues.

**Pros and cons of crypto data aggregation**
--------------------------------------------

### **Pros**

1. **Consistency:** Aggregating data from multiple sources and normalizing it ensures consistency and reliability.
2. **Error reduction:** Data cleaning processes remove inconsistencies, duplicates, and errors, leading to higher-quality data.
3. **Wide coverage:** Aggregating data from various exchanges provides a more comprehensive view of the market, capturing a broader range of trading activities.
4. **Detailed insights:** High-resolution data (e.g., tick-by-tick) offers detailed insights into market trends and behaviors.
5. **Time-saving:** Aggregated data saves users the time and effort required to collect and process data from multiple sources.
6. **Simplified integration:** Standardized data formats and protocols make it easier to integrate aggregated data into existing systems and workflows.
7. **Custom metrics:** Users can define custom aggregation metrics and time intervals, allowing for tailored analysis and insights.
8. **Historical data:** Access to comprehensive historical data supports backtesting, trend analysis, and other research activities.
9. **Live data:** Real-time streaming of aggregated data ensures that users have access to the most up-to-date market information.
10. **Immediate action:** Real-time data enables immediate decision-making and action, which is crucial for trading and other time-sensitive applications.

### **Cons**

1. **Data integration:** Aggregating data from multiple sources can be complex, requiring sophisticated data integration and normalization processes.
2. **Technical challenges:** Ensuring data quality, consistency, and synchronization across different sources can be technically challenging.
3. **Processing time:** The process of aggregating and normalizing data can introduce some [latency](https://www.coinapi.io/blog/importance-of-low-latency-in-cryptocurrency-trading), which may affect the timeliness of the data.
4. **Real-time constraints:** While real-time streaming is available, the initial aggregation process may still introduce slight delays.
5. **Infrastructure:** Maintaining the infrastructure required for data aggregation, storage, and distribution can be costly.
6. **Subscription fees:** Accessing high-quality aggregated data from providers like [CoinAPI](https://docs.coinapi.io/) may involve subscription fees.
7. **Volume:** Aggregating data from multiple sources can result in large volumes of data, which may be overwhelming for some users.
8. **Filtering:** Users may need to implement filtering mechanisms to extract relevant information from the aggregated data.
9. **Reliability:** Users are dependent on the reliability and accuracy of the data provided by the aggregation service.
10. **Vendor lock-in:** Switching providers can be challenging due to differences in data formats, protocols, and integration processes.

#### **In short, data aggregation has some challenges. However, it's very helpful for crypto traders. Want to learn more? Visit our [website](https://www.coinapi.io/market-data-api) or [talk](https://www.coinapi.io/contact-us) to our team!**

Data Quality and Security
-------------------------

While aggregated crypto data is subject to the same quality and security risks as any other type of data, reputable data aggregators implement stringent measures to ensure its integrity. These measures include robust data validation and verification processes, secure data storage, and transmission protocols.

Additionally, some data aggregators offer advanced features such as data encryption and access controls to further enhance data security. By prioritizing data quality and security, these aggregators provide users with reliable and trustworthy information, enabling them to make confident decisions in the crypto market.

Top Crypto Data Aggregators
---------------------------

### Examples of Popular Aggregators

Several crypto data aggregators have gained popularity for their comprehensive market data and user-friendly features. Here are some of the top platforms:

* **CoinMarketCap**: Known as a leading cryptocurrency data aggregator, CoinMarketCap provides real-time market data, detailed analytics, and essential information for crypto investors. It covers a wide range of digital assets and exchanges, making it a go-to resource for market insights.
* **CryptoCompare**: This platform aggregates data from various exchanges, offering users a broad spectrum of market data, analytics, and tools. CryptoCompare is valued for its extensive data coverage and detailed analytics, which help users make informed decisions.
* **CoinGecko**: A popular choice among crypto enthusiasts, CoinGecko aggregates data from multiple exchanges to provide real-time market data and detailed analytics. Its user-friendly interface and comprehensive data make it a valuable resource for tracking market trends.
* **TradingView**: Renowned for its advanced charting capabilities, TradingView aggregates data from multiple exchanges to offer real-time market data and detailed analytics. It is particularly favored by traders for its technical analysis tools and customizable charts.

Choosing the Right Crypto Data Aggregator
-----------------------------------------

### Factors to Consider

Selecting the right crypto data aggregator is crucial for accessing reliable market data and making informed investment decisions. Here are some key factors to consider:

* **Data Coverage**: Ensure the platform aggregates data from multiple exchanges, including both decentralized exchanges (DEXs) and centralized exchanges (CEXs). A wide data coverage provides a more comprehensive view of the market.
* **Data Accuracy**: Look for a platform that offers accurate and reliable data with minimal delays or errors. Accurate data is essential for making timely and informed decisions in the fast-paced crypto market.
* **User Interface**: Choose a platform with a user-friendly interface that is easy to navigate, even for beginners. A well-designed interface enhances the overall user experience and makes it easier to access and analyze data.
* **Analytics and Tools**: Consider a platform that provides detailed analytics, technical indicators, and other tools to help users make informed investment decisions. Advanced analytics and tools can offer deeper insights into market trends and opportunities.
* **Security**: Ensure the platform has robust security measures in place to protect user data and prevent hacking or other security breaches. Data security is paramount in the crypto world, where the stakes are high.
* **Customer Support**: Look for a platform with responsive customer support, including multiple channels for communication and a comprehensive knowledge base. Good customer support can help resolve issues quickly and provide valuable assistance when needed.

By considering these factors, users can choose a crypto data aggregator that meets their needs and provides them with the information and tools necessary to succeed in the crypto market.

Future of Aggregated Crypto Data
--------------------------------

The future of aggregated crypto data is poised to be shaped by the ongoing growth and evolution of the cryptocurrency market. As the market continues to expand, the demand for high-quality, reliable, and secure data will only increase. Aggregated crypto data will play a crucial role in meeting this demand, providing the necessary insights to support informed investment decisions.

Future developments may include the integration of artificial intelligence and machine learning to analyze and interpret data more effectively. Additionally, incorporating data from other sources, such as social media and news outlets, will further enrich the insights provided by aggregated crypto data. As data aggregators continue to innovate and enhance their services, they will be better equipped to meet the changing needs of the market and support the growing community of crypto investors and traders.

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