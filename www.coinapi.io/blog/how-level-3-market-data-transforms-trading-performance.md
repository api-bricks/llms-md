CoinAPI.io Blog - How Level 3 Market Data Transforms Trading Performance

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

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F864140657bd92584430501b573b01ae0314cbc3d-800x800.png&w=96&q=75)Ada

August 05, 2025

How Level 3 Market Data Transforms Trading Performance
======================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fab2a315d6528b49cda3fd200b418af97ce48894f-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

**What if you could see every individual order placement, modification, and cancellation happening in real-time across crypto exchanges? Most traders trade blind, relying on basic price feeds that show aggregated snapshots. Meanwhile, sophisticated algorithmic traders and institutional investors access something far more powerful: [Level 3 market data.](https://www.coinapi.io/learn/glossary/level-3-data)**

This granular, order-by-order market intelligence reveals the true DNA of market microstructure. Every bid, ask, and modification gets tracked with unique identifiers, giving you visibility into orderbook crypto movements that 99% of traders never see.

Here's what makes this critical: CoinAPI currently provides Level 3 market data coverage for only four select exchanges: [BITSO](https://bitso.com/) and [COINBASE](https://www.coinbase.com/pl). This limited availability creates a significant information advantage for those who understand how to access and interpret orderbook data at this granular level.

After working with thousands of Level 3 market data users over the years, we've watched brilliant developers burn through six-figure budgets learning lessons the hard way. We've seen promising strategies collapse not from bad ideas, but from fundamental misunderstandings about how orderbook crypto data works in practice.

Today, we're sharing the painful truths that separate successful Level 3 market data professionals from expensive beginners. These aren't theoretical concepts; they're battle-tested insights from the CoinAPI community that could save you months of frustration and thousands in wasted infrastructure costs.

If you're serious about Level 3 market data, buckle up. We're going deep.

What is Level 3 Market Data?
----------------------------

Level 3 market data represents the most granular form of financial market information available, providing order-by-order visibility into exchange trading activity. Unlike Level 1 data (best bid/ask prices) or Level 2 data (aggregated order book depth), Level 3 market data reveals every individual order with unique identifiers, timestamps, and complete lifecycle tracking from placement to execution or cancellation.

**The Three Levels of Market Data Explained:**

**Level 1:** Shows only the best bid and ask prices with volume **Level 2:** Displays aggregated order book depth at each price level

**Level 3:** Reveals individual orders with unique IDs and complete order lifecycle data

**For a deeper dive into how these different data levels work together, check out our comprehensive guide on** [Level 1 vs Level 2 vs Level 3 market data and reading crypto order books](https://www.coinapi.io/blog/level-1-vs-level-2-vs-level-3-market-data-how-to-read-the-crypto-order-book).

In cryptocurrency markets, Level 3 data captures critical order information including:

* **Unique Order Identifiers:** Each order receives a distinct ID for precise tracking
* **Update Types:** ADD, DELETE, UPDATE, and SUBTRACT operations for every order modification
* **Precise Timestamps:** Microsecond-level timing for each order event
* **Order Lifecycle:** Complete journey from placement to final execution or cancellation
* **Market Maker vs. Taker Identification:** Understanding who provides vs. consumes liquidity

This granular visibility transforms how sophisticated traders approach market analysis. While most retail traders operate with basic price feeds, Level 3 data users can identify institutional order patterns, detect hidden liquidity through iceberg orders, and build advanced algorithms that capitalize on market microstructure inefficiencies.

The scarcity of Level 3 data makes it particularly valuable. Most exchanges don't provide this level of transparency due to technical complexity and competitive concerns. Currently, CoinAPI offers Level 3 market data coverage for only four select exchanges: BITSO, COINBASE, POLONIEXFTS, and SEEDCX.

What Makes Level 3 Market Data Different
----------------------------------------

Level 3 data tracks individual order lifecycles from placement to execution or cancellation. Each order carries a unique identifier, update type (ADD, DELETE, UPDATE, SUBTRACT), and precise timestamps. This detail enables you to:

* **Track institutional order patterns** by analyzing large order placements and modifications
* **Identify hidden liquidity** through iceberg orders and dark pool activity
* **Detect market manipulation** via coordinated order placement schemes
* **Build sophisticated arbitrage models** with precise execution timing data
* **Optimize market making strategies** using order flow imbalance predictions

Consider this real Level 3 data example from Coinbase:

```
1{
2  "type": "book_l3",
3  "symbol_id": "COINBASE_SPOT_BTC_USD",
4  "sequence": 2323346,
5  "time_exchange": "20200826T123604.3464706Z",
6  "asks": [
7    {
8      "id": "520269d4-c08547ed-88256d787af90800",
9      "price": 43201.50,
10      "size": 1.81940502,
11      "update_type": "ADD"
12    }
13  ]
14}
```

Notice how each order has a unique ID and specific update type. This granular information separates amateur trading strategies from institutional-grade approaches.

**Level 3 Data Providers: Complete Market Comparison**
------------------------------------------------------

The Level 3 market data landscape is surprisingly limited. While dozens of providers claim to offer "granular" market data, true order-by-order tracking with unique identifiers remains rare. Here's how the major players actually stack up when you need genuine Level 3 capabilities:

|  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- |
| Provider | Level 3 Market data | Exchanges Covered | Data Delivery | Key Strengths | Limitations |
| CoinAPI | ✅ True L3 | 2 exchanges: BITSO, COINBASE. | REST, WebSocket, FIX | Individual order IDs, complete order lifecycle tracking, unified API across all exchanges | Limited exchange coverage for L3 |
| Kaiko | ❌ L2 Only | 100+ exchanges | REST, CSV, WebSocket | Extensive exchange coverage, institutional-grade data quality, historical depth from 2013 | No true Level 3 data - aggregates L3 to L2 |
| Tardis.dev | ✅ Tick-level | 40+ exchanges | API, CSV downloads | Historical tick-level data, comprehensive coverage, good for backtesting | Primarily historical focus, limited real-time L3 |
| Coin Metrics | ⚠️ L2 Aggregated | Major exchanges | REST, WebSocket | Strong on-chain analytics, normalized data formats | Converts L3 to L2 before storage |
| Polygon.io | ❌ No L3 | Limited crypto coverage | REST, WebSocket | Ultra-low latency (nanosecond), primarily focused on traditional markets | No crypto L3 data, limited crypto coverage |
| Amberdata | ❌ L2 Focus | Major exchanges | API, Cloud services | DeFi and CeFi coverage, institutional compliance | No individual order tracking |
| CryptoCompare | ❌ L2 Only | 200+ exchanges | REST, WebSocket | Extensive free tier, broad exchange coverage | Aggregated data only, no order-level granularity |

Complete Level 3 Exchange Coverage Breakdown
--------------------------------------------

CoinAPI supports Level 3 market data from four exchanges, each serving different market segments and use cases.

### [COINBASE](https://www.coinbase.com/): The Institutional Gateway

**Coverage:** Comprehensive spot trading pairs

Coinbase represents the largest US-regulated crypto exchange, making its L3 data invaluable for understanding institutional trading flows and retail sentiment in regulated markets. The platform provides:

* Full order-by-order visibility across major cryptocurrency pairs
* Real-time updates with microsecond timestamps
* High-frequency data suitable for algorithmic trading
* Comprehensive coverage of both major coins and altcoins

**Strategic Application:** Use Coinbase L3 data to detect when large institutional orders execute across multiple price levels, providing early signals for significant price movements.

### [BITSO](https://bitso.com/): Latin American Market Intelligence

**Coverage:** Latin American focused cryptocurrency pairs

BITSO dominates Latin American cryptocurrency trading, offering unique insights into emerging market behaviors. Key features include:

* Order-level granularity for Mexican and regional markets
* High correlation with peso-denominated trading patterns
* Regional arbitrage opportunity identification
* Emerging market microstructure insights

**Strategic Application:** Identify arbitrage opportunities between US dollar and Mexican peso markets during currency volatility periods.

Real-World Applications That Drive Results
------------------------------------------

### Advanced Arbitrage Detection

Traditional arbitrage strategies miss hidden opportunities that Level 3 data reveals. Consider this scenario:

Surface-level data shows minimal price differences:

* Exchange A: $43,200
* Exchange B: $43,195

This appears to offer minimal arbitrage potential. However, Level 3 data reveals the complete picture:

* Exchange A has only $50,000 liquidity at surface price
* Exchange B has $500,000 liquidity at its price

This depth analysis completely changes arbitrage calculations and execution strategies.

**Want to master crypto arbitrage strategies? Read our [comprehensive guide to crypto arbitrage opportunities in 2025](https://www.coinapi.io/blog/crypto-arbitrage-explained-coinapi-profit-opportunities-2025) to discover proven profit techniques, or explore our [crypto arbitrage use case](https://www.coinapi.io/use-case/crypto-arbitrage) to see how CoinAPI powers professional arbitrage systems.**

### Institutional Order Pattern Recognition

Level 3 data helps identify institutional trading through:

**Order Size Analysis:** Consistently large orders appearing and disappearing suggest institutional activity.

**Timing Patterns:** Orders placed in specific sequences or intervals often indicate algorithmic strategies.

**Price Level Clustering:** Multiple orders at psychologically significant levels may signal coordinated positioning.

### Market Making Optimization

Professional market makers use Level 3 data to:

* Identify optimal spread positioning
* Detect adverse selection risks
* Adjust quote sizes based on order flow imbalances
* Minimize inventory risk through predictive modeling

**Learn more about professional market making strategies in our [comprehensive guide to crypto market making](https://www.coinapi.io/blog/market-making-in-crypto).**

Why Level 3 Data Remains Exclusive
----------------------------------

You might wonder why all exchanges don't provide Level 3 data. Several factors limit availability:

**Technical Complexity:** Publishing order-level data requires significant infrastructure and bandwidth capabilities.

**Competitive Concerns:** Exchanges view granular order data as proprietary information providing competitive advantages.

**Regulatory Considerations:** Different jurisdictions have varying requirements around market data transparency.

**Business Models:** Many exchanges monetize Level 3 data separately or reserve it for premium clients.

This limited availability makes CoinAPI's Level 3 coverage particularly valuable for serious traders and developers.

Getting Started With Level 3 Data
---------------------------------

The key to success isn't just accessing Level 3 data; it's knowing how to interpret and act on the insights it provides. Whether you're building sophisticated arbitrage systems, developing institutional market-making strategies, or seeking deeper market understanding, Level 3 coverage opens opportunities most traders never see.

Frequently Asked Questions
--------------------------

**What's the difference between Level 2 and Level 3 market data?** Level 2 shows aggregated order book depth at each price level, while Level 3 reveals individual orders with unique identifiers, allowing order-by-order tracking and analysis.

**Which exchanges currently support Level 3 data through CoinAPI?** CoinAPI provides Level 3 market data coverage for BITSO and COINBASE.

**How much does Level 3 market data cost?** Pricing follows a tiered model with Level 3 data included in Professional subscriptions, starting at 512 GB Tier 1 data daily allocation.

**Can I use Level 3 data for algorithmic trading?** Yes, Level 3 data is specifically designed for sophisticated algorithmic strategies, providing the granular information needed for advanced market making, arbitrage, and execution algorithms.

**What technical requirements are needed for Level 3 data?** You need WebSocket API integration capabilities, efficient data processing systems, and sufficient bandwidth to handle high-frequency order updates.

**How does Level 3 data improve trading performance?** Level 3 data provides visibility into institutional order patterns, hidden liquidity, and market microstructure, enabling better timing, improved arbitrage detection, and superior risk management.

Ready to unlock Level 3 market intelligence?
--------------------------------------------

[Sign up for CoinAPI](https://www.coinapi.io/products/market-data-api/pricing) and start exploring order-level data today. With proper implementation and analysis, Level 3 data could become your competitive advantage in cryptocurrency trading.

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