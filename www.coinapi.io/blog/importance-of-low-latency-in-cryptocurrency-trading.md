CoinAPI.io Blog - The Role of Latency in Cryptocurrency Data

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

May 31, 2024

The Role of Latency in Cryptocurrency Data
==========================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb9615665d3c61ad707a1598a52c908969b4cb832-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

***Latency plays an important role in the world of cryptocurrency. Indeed, it impacts everything from the speed of trade execution to the accuracy of market data. This blog post is all about what latency is, why low latency is crucial in crypto, and how various factors influence it. Furthermore, we’ll explore how we, as a company ensure minimal latency in our [Market Data API](https://www.coinapi.io/market-data-api) and [EMS Trading API](https://www.coinapi.io/ems-api).***

What is latency?
----------------

[Latency](https://www.ibm.com/topics/latency) in simple words is the delay within a system. In the context of networks, latency measures the time it takes for data to travel from point A to point B. In the ideal situation the data transmission would happen instantly, but in reality, it’s slowed by many factors:

* **Distance**
* **Infrastructure**
* **Network congestion**

![A diagram illustrating network latency. It shows a laptop icon on the left, a server icon on the right, and a stopwatch icon in the center. Arrows indicate data transfer times of 800ms from laptop to server and 900ms from server to laptop, with a total latency of 1.7s.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F4018ed6781164ce13020c709825e7cf0d415d902-1024x512.png&w=1920&q=75)

*Source: [keycdn.com](https://www.keycdn.com/support/network-latency)*

### Data latency

[Data latency](https://www.earthdata.nasa.gov/learn/backgrounders/data-latency) refers to the delay between the time data is created and the time it is available for use. In the context of cryptocurrency, it is the time taken for price updates and market data to be transmitted from exchanges to traders. Consequently, low latency means faster data delivery, which is crucial for high-frequency trading strategies where every millisecond counts.

> “Information can’t travel faster than light. This is crucial for understanding data latency. For instance, data from an APAC exchange reaching the United States takes at least 200 milliseconds. This delay is an inherent limitation due to light speed and can’t be overcome. It’s physically impossible.”  
> **– Artur Pietrzyk, CEO @CoinAPI**

### Why is low latency so important in crypto?

There are areas of cryptocurrency trading and market analysis that could be directly influenced by high latency. Moreover, the speed of data transmission is one of the key factors in several situations.

1. [**High-frequency trading**](https://dydx.exchange/crypto-learning/high-frequency-trading) These traders rely on executing a large number of orders at extremely fast speeds. Thus, low latency ensures that they can gain on market inefficiencies and price discrepancies before other market participants do. The faster the network the more they earn.
2. [**Slippage**](https://www.investopedia.com/terms/s/slippage.asp) It occurs when there is a difference between the expected price of a trade and the actual executed price. Consequently, lower latency minimizes the chances of slippage, ensuring trades are executed at the desired prices. In cases like that fractions of a second matter.
3. [**Arbitrage trading**](https://www.coinbase.com/pl/learn/advanced-trading/what-is-crypto-arbitrage-trading) Traders exploiting arbitrage opportunities need to act on price differences across different exchanges quickly. Therefore, low latency enables them to make these trades before the price differences are gone.
4. [**Real-time data access**](https://en.wikipedia.org/wiki/Real-time_data)  
   Traders need real-time data to make the best decisions. Low latency means that they receive up-to-date information, allowing for better risk management and decision-making. **Top traders use the best real-time data insights via APIs like [WebSocket](https://docs.coinapi.io/market-data/websocket/) from single exchanges or even better based on aggregated [exchange rates](https://www.coinapi.io/blog/cryptocurrency-exchange-rates).**
5. [**Algorithmic trading**](https://www.coinapi.io/use-case/coinapi-for-algo-trading-crypto-bot) Many trading strategies are automated and depend on algorithms and bots that react to market changes in real time. Hence, low latency is essential for these algorithms to function fast on time, correctly, and profitably for the trader.
6. [**Liquidity providers**](https://www.coinapi.io/use-case/coinapi-for-crypto-index-providers) Market makers and liquidity providers rely on low latency to update their orders and spread quickly in response to market changes, ensuring they can offer tight spreads and maintain profitability.

### The consequences of high latency

High latency can have negative impacts on your crypto market actions:

1. **Delayed Market Data:** When market data is delayed, traders make decisions based on outdated information, which can lead to missed opportunities or suboptimal trades.
2. **Execution Delays:** Trades executed with high latency may miss the desired price points, leading to increased slippage and reduced profitability.
3. **Increased Risk:** Slower response times can result in higher risk, especially in volatile markets where prices change rapidly.

Latency measurement units
-------------------------

Latency, in the context of data transmission, is measured in terms of time delay. In the cryptocurrency market, latency is typically measured in nanoseconds (ns), microseconds (µs), and milliseconds (ms). Each unit represents a different scale of delay, which is crucial for traders, especially those using high-frequency trading strategies.

Let’s explore these measurements and their significance with examples from the cryptocurrency world.

1. **Milliseconds (ms) one-thousandth of a second**  
   This is common in broader trading applications. Although slower than the other units, it’s still considered very fast for most trading activities.
2. **Microseconds (µs) one-millionth of a second**  
   We often see this in scenarios requiring rapid data processing. In fact, many trading strategies rely on microsecond latency for their effectiveness.
3. **Nanoseconds (ns) one-billionth of a second**  
   High-frequency trading (HFT) environments typically use this measurement. Indeed, in the world of cryptocurrency, achieving nanosecond latency requires extremely sophisticated technology and infrastructure.

> “Most latency results from physical distance on Earth and indirect cable connections. Therefore, the farther data travels and the more intermediate points it passes through, the higher the latency. To minimize this, we use direct connections and optimized routing.”**– Artur Pietrzyk, CEO @CoinAPI**

How CoinAPI deals with latency
------------------------------

We know that low latency is one of the most important features for our clients. We are doing our best to keep it super-low. **How do we do it?** In order to deal with latency, first, you have to know how high it is.

### How do we measure and validate latency?

We measure and confirm latency using precise [timestamping](https://cpl.thalesgroup.com/faq/signing-certificates-and-stamping/what-time-stamping) methods at various stages in the data flow. This includes:

* **Network Time Protocol (NTP):** We synchronize clocks across servers to maintain accurate time measurements.
* **Packet Capture Tools:** We use tools like [Wireshark](https://www.wireshark.org/) to capture and analyze network packets.
* **Latency Monitoring Software:** We implement software solutions that constantly monitor and report latency metrics.

### How is our latency so low?

We take great pride in having one of the lowest data latencies in the crypto market. In fact, in some cases, we achieve data latency below 1 millisecond! To accomplish this as an API provider, we fulfill several key conditions:

* **Direct Connections:** Establishing direct connections to exchanges and data centers.
* **[AWS VPC Peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html):** Utilizing AWS VPC Peering for low-latency, high-bandwidth connections between our infrastructure and the customer’s.

![A diagram showing VPC peering connection between two VPCs (Virtual Private Clouds). VPC A and VPC B are represented by green boxes, each containing a subnet. They are connected by a central icon representing the VPC peering connection.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F61b23e596a039f09d5fad462e95f58abb86cb8db-499x161.webp&w=1920&q=75)

*Source: [docs.aws.amazon.com](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html)*

* **[GeoDNS Routing](https://gcore.com/blog/implementing-geodns/):** Using GeoDNS to direct traffic to the nearest data center.

![A flowchart depicting the DNS resolution process with GeoIP. It shows the flow of information between a Client, DNS resolver, Authoritative DNS, GeoIP database, and a Record Set, with numbered steps and IP addresses.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F389425ad33ad05cb751b8a92abb314a1da4b3390-1024x381.webp&w=1920&q=75)

*Source: [gcore.com](https://gcore.com/blog/implementing-geodns/)*

* **Optimized Network Paths:** Utilizing optimized network paths and low-latency routes.
* **High-Performance Hardware:** Deploying top-tier servers and network equipment.

### Is the latency always low?

Generally, latency is typically low, but it can increase during a [failover](https://danevo.net/en/news/failover/). Nevertheless, we have strategies to manage such situations.

![A comparison of Normal Mode and Disaster Mode in a data center setup. Normal Mode shows data flow between a user, primary datacenter, and failover datacenter. Disaster Mode shows the primary datacenter crossed out, with traffic redirected to the failover datacenter.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F7208b732bfd93740fb47a9a53250b9883135e353-674x300.webp&w=1920&q=75)

*Source: [danevo.net](https://danevo.net/en/news/failover/)*

### **How do we handle failovers?**

We have a comprehensive plan in place for these situations, and our goal remains the same – to maintain the lowest possible latency. Specifically, we employ the following methods:

* **Redundancy:** Firstly, we implement backup servers to enable quick regional switches.
* **Automated failover:** Secondly, we use automated systems to reduce downtime.
* **Load balancing:** Finally, we distribute traffic across multiple servers to ensure continuous service.

### **How does server load impact latency, and what mechanisms are in place to handle high traffic without degrading performance?**

Server load can undoubtedly impact latency by increasing processing times. To handle high traffic effectively, we use a multi-faceted approach:

* **Load Balancing:** First and foremost, we distribute traffic across multiple servers to prevent any single server from becoming overwhelmed.
* **Auto-Scaling:** Additionally, we automatically add resources during peak times to maintain performance.
* **Performance Monitoring:** Furthermore, we continuously monitor server performance and adjust resources as needed to ensure optimal operation.

> *💡 See SingAlliance case study where low latency of data was one of the most important factors → [Case study](https://www.coinapi.io/case-study/singalliance-leverages-coinapi-for-crypto-investment-analysis)*

Is there a difference in latency between self-hosted and managed cloud?
-----------------------------------------------------------------------

Indeed, there is a difference in latency between self-hosted and managed cloud solutions, though it is generally minimal. Let’s examine both options:

**Self-hosted**

* **Pros:**
  + Lower latency, optimized for specific use cases.
  + Greater control over configuration and performance.
* **Cons:**
  + Requires significant expertise and resources to manage.
  + Higher responsibility for maintenance and troubleshooting.

**Managed cloud**

* **Pros:**
  + Easier management with no client-side maintenance required.
  + Scalability and flexibility are provided by the cloud service.
* **Cons:**
  + Potential for slightly higher latency due to shared resources.
  + Limited control over specific optimizations.

### Manage cloud – CoinAPI’s server latency

We use a combination of:

* **[Equinix](https://www.equinix.com/):** For colocation services, providing high-performance, low-latency connections.
* **[AWS](https://aws.amazon.com/):** For scalable cloud infrastructure, offering flexibility and redundancy.

This hybrid approach allows us to leverage the strengths of both environments, thereby ensuring optimal performance and reliability.

> *💡 READ HOW COINAPI ENSURES DATA ACCURACY AND SPEED [HERE](https://www.coinapi.io/blog/how-coinapi-ensures-data-accuracy-and-speed)*

Client-side configurations and best practices for the lowest latency
--------------------------------------------------------------------

To achieve the best performance, clients should consider the following practices:

* **Optimized Network Configuration:** Ensuring network settings are configured for low latency.
* **Direct Connections:** Establishing direct connections to our data centers to minimize data travel time.
* **Efficient Code:** Writing efficient, low-latency code for data processing to reduce execution time.
* **Regular Updates:** Keeping software and hardware up to date to benefit from the latest performance improvements.

Latency comparison for CoinAPI’s plans
--------------------------------------

1. **[Enterprise Plan](https://www.coinapi.io/market-data-api/pricing):**
   * **Access Type:** Importantly, it is possible to have direct access to the sites or set up AWS VPC Peering.
   * **Latency:** Consequently, latency is possible below one millisecond due to direct access or VPC Peering.
   * **Example:** For instance, if you set up AWS VPC Peering, the latency between your infrastructure and CoinAPI’s infrastructure will be less than one millisecond.
2. **[Free, Startup, Streamer, and Professional Plans](https://www.coinapi.io/market-data-api/pricing):**
   * **Access Type:** In contrast, connections are established to the public endpoint with GeoDNS (routed to the closest site) (~20ms).
   * **Latency:** As a result, latency depends on the distance between your location and the site where the connection is routed, typically around 20 milliseconds.
   * **Example:** For example, if you are located in New York and the closest site is in Virginia, the latency will be approximately 20 milliseconds.

Conclusion
==========

In conclusion, do you want to be the best and gain an advantage over others? Well, there’s no other way around it, but to have the lowest latency data source possible – like Market Data API. Indeed, CoinAPI and our products are all about reliability and low-latency real-time data access.

If you want to learn more about how our low-latency solutions can benefit your trading strategies, don’t hesitate to contact our [sales team](https://www.coinapi.io/contact-us). Additionally, you can explore our comprehensive [documentation](https://docs.coinapi.io/) for technical details on implementing our APIs.

Remember, in the world of cryptocurrency trading, every millisecond counts. By choosing a low-latency solution like CoinAPI, you’re positioning yourself for success in this dynamic market.

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