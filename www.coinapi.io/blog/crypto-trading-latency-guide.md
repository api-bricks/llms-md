CoinAPI.io Blog - How Fast is Fast Enough? Understanding Latency in Crypto Trading with CoinAPI

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

July 11, 2025

How Fast is Fast Enough? Understanding Latency in Crypto Trading with CoinAPI
=============================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F83f064b03669f83adfc7f1c4628205ed2db6f3c2-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

**Latency is one of the most misunderstood - and often overhyped - metrics in crypto trading. In a market where milliseconds can separate profits from losses, it's no wonder traders chase "ultra-low latency" like a holy grail. But what does latency actually mean in practice? How fast is fast enough? And what does CoinAPI deliver in real-world setups?**

In this article, we'll cut through the marketing noise and give you a trader-focused breakdown of how latency works, what limits it, and the infrastructure choices that actually matter.

Real-Time Crypto Data: What Actually Determines Speed
-----------------------------------------------------

When evaluating **real-time crypto data** providers, speed is just one factor. Here's what actually affects your trading performance:

### Data Freshness vs. Processing Speed

**Fresh data matters more than fast delivery of stale data**:

* Exchange A updates every 100ms, delivered in 10ms = 110ms total latency
* Exchange B updates every 10ms, delivered in 50ms = 60ms total latency
* Exchange B gives you newer information despite "slower" API

### Geographic Distribution

**Crypto trading speed** depends heavily on physical location:

* **US East Coast**: Fastest access to major exchange data centers
* **Europe**: Good connectivity to European venues
* **Asia**: Optimal for Asian exchange data
* **Other regions**: Higher baseline latency due to distance

### Protocol Efficiency

**Data delivery methods ranked by speed**:

1. **Binary protocols** (fastest, custom implementations)
2. **FIX API** (professional standard, minimal overhead)
3. **WebSocket** (good balance of speed and simplicity)
4. **REST API** (slowest, but easiest to implement)

**Key insight**: The fastest crypto API for your use case depends on your infrastructure, location, and technical requirements, not just marketing claims.

What is Latency and Why Does It Matter?
---------------------------------------

**Latency definition**: The delay between requesting data and receiving it.

In crypto trading, lower latency means:

* Faster reaction to price changes
* More precise execution timing
* Less slippage during volatile periods
* Competitive advantage in fast-moving markets

In highly competitive environments like perpetual futures arbitrage or delta-neutral hedging, every millisecond counts.

But here's the catch:

### **Latency is not a static number you can buy**

It's shaped by multiple factors, many outside any API provider's control:

* **Your server location** relative to the data centers
* **Exchange data latency** (some venues are inherently slower)
* **Network routing** and internet infrastructure
* **API gateway performance** and connection pooling
* **Data format and protocol overhead** (WebSocket vs FIX vs REST)
* **Your application architecture** and processing efficiency

Which brings us to a key point many traders miss:

**You can't just sign up for an API and expect nanosecond speed on shared cloud infrastructure. Achieving serious speed requires architectural design, infrastructure investment, and understanding the physics of data transmission.**

The Latency Reality Check: What's Actually Possible
---------------------------------------------------

### The Physics Problem

**Speed of light in fiber optic cable**: ~200,000 km/second. **New York to London**: ~5,500 km **Theoretical minimum latency**: ~27 milliseconds one-way

This means even with perfect infrastructure, you can't get sub-millisecond latency between continents. Geography matters.

### The Infrastructure Stack

Your total latency is the sum of:

1. **Exchange internal latency** (1-50ms depending on venue)
2. **Network transmission** (physics + routing)
3. **API processing** (parsing, normalization, delivery)
4. **Your application processing** (often the biggest bottleneck)

CoinAPI optimizes layers 2-3, but we can't fix slow exchanges or inefficient client code.

CoinAPI's Latency Tiers: Honest Numbers
---------------------------------------

At CoinAPI, we provide **the fastest technically achievable latency at each infrastructure level**. Here's what's actually possible:

![ ](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ffa37eff67b629a6eb921ff63cc37d9f5e8df7285-1848x582.png&w=1920&q=75)

* *Sub-millisecond performance requires client co-location and specialized infrastructure*

### Shared Infrastructure: Optimized for Accessibility

If you're using CoinAPI through standard plans on cloud-hosted infrastructure, you're getting the fastest possible response times for **shared, public infrastructure**.

**What this includes**:

* Optimized WebSocket connections
* Efficient data parsing and normalization
* Global CDN endpoints
* Best-effort routing

**What limits performance**:

* Shared bandwidth and processing
* Internet routing variations
* Geographic distance from data centers
* Exchange variations (Binance ≠ smaller venues)

**Perfect for**:

* Mid-frequency strategy monitoring
* Backtesting and research
* Portfolio dashboards and alerts
* Strategies with 1+ minute timeframes

**Not suitable for**:

* Microsecond-level arbitrage
* Ultra-high-frequency market making
* Latency-sensitive scalping strategies

### Enterprise Latency: Dedicated Performance

Enterprise tier removes the shared infrastructure bottlenecks:

**Technical upgrades**:

* Dedicated server instances
* Private API rate limits (no throttling from other users)
* FIX API protocol (minimal overhead)
* Regional optimization for your location
* Priority routing and connection pooling

**Realistic performance**: 5-50ms depending on:

* Your proximity to our data centers
* Which exchanges you're monitoring
* Data complexity (tick vs OHLCV vs order book depth)

**Ideal applications**:

* Cross-exchange monitoring strategies
* Options and futures hedging
* Basis or funding rate arbitrage
* Signal-based execution algorithms
* Professional portfolio management

### HFT-Grade Infrastructure: When Microseconds Matter

For operations requiring maximum speed, CoinAPI supports advanced connectivity:

**Technical solutions**:

* **VPC Peering** within AWS/GCP (eliminates internet routing)
* **Cloud Direct Connect** (dedicated fiber to cloud providers)
* **Physical cross-connects** at Equinix NY4, LD4, TY8, HK1
* **Custom FIX gateways** with binary protocols
* **Raw market data streams** (minimal processing)

**What's technically possible**:

* Sub-millisecond data delivery
* Microsecond-level synchronization
* Nanosecond-aware timestamping

**What it requires from you**:

* Co-location presence in same facilities
* Custom network infrastructure
* Specialized hardware (low-latency NICs, kernel bypass)
* Expert development team
* Significant ongoing investment ($50k-500k+ annually)

**Use cases**:

* Market-making operations
* Latency arbitrage strategies
* High-frequency statistical arbitrage
* Delta hedging under extreme time pressure

The Latency Trap: Common Misconceptions
---------------------------------------

### "I signed up for Pro. Why isn't everything instant?"

The most common misconception: expecting microsecond performance from standard cloud subscriptions.

**Reality check**: Microsecond speed isn't a software feature; it's a complete infrastructure solution requiring:

* Physical proximity to exchanges
* Dedicated network paths
* Specialized hardware and software
* Ongoing engineering optimization

### "Can't you just make the API faster?"

CoinAPI already delivers the fastest technically possible speeds at each tier. The limitations are:

1. **Exchange limitations**: Some venues have 10-50ms internal latency
2. **Geographic physics**: The Speed of light is a hard limit
3. **Shared infrastructure**: Multiple users = resource contention
4. **Client architecture**: Your code often adds more latency than network transmission

### "Other providers claim nanosecond latency."

Be skeptical of blanket latency claims. Ask providers:

* What specific infrastructure setup?
* Which exchanges and data types?
* What are the setup costs and requirements?
* What's included vs. what requires custom engineering?

Most "nanosecond" claims apply only to custom enterprise setups costing $100k+ annually.

How Exchange Choice Affects Your Latency
----------------------------------------

Not all exchanges are created equal. Here's what affects the speed of data from different venues:

### Tier 1 Exchanges (Consistently Fast)

* **Binance**: Optimized infrastructure, global presence
* **Coinbase**: Professional-grade systems
* **Kraken**: Reliable, well-engineered APIs

### Variable Performance Exchanges

* **Smaller venues**: Often higher latency, less reliable
* **Regional exchanges**: May prioritize local connectivity
* **New exchanges**: Infrastructure still maturing

### Exchange-Specific Factors

* **API architecture**: REST vs WebSocket vs FIX
* **Data center locations**: Geographic distribution
* **Load balancing**: How they handle traffic spikes
* **Internal processing**: Order matching engine efficiency

**Key insight**: CoinAPI can't make slow exchanges fast, but we ensure you get the best possible performance from each venue.

Building for Speed: Technical Recommendations
---------------------------------------------

### If You Need Standard Performance (50-500ms)

**Architecture**:

* Use CoinAPI WebSocket feeds
* Deploy on major cloud providers (AWS, GCP, Azure)
* Choose regions close to exchange data centers
* Implement proper connection pooling

**Code optimization**:

* Efficient JSON parsing
* Asynchronous processing
* Proper error handling and reconnection logic
* Minimal data transformation

### If You Need Professional Performance (5-50ms)

**Upgrade to Enterprise**:

* Dedicated infrastructure
* FIX API protocols
* Regional optimization
* Priority support for architecture design

**Technical requirements**:

* Dedicated servers (not shared hosting)
* Business-grade internet (not residential)
* Geographic proximity to CoinAPI data centers
* Professional development practices

### If You Need HFT Performance (Sub-millisecond)

**Custom solutions required**:

* Co-location presence
* Direct network connections
* Specialized hardware
* Expert engineering team

**Typical implementation**:

1. **Assessment phase**: Analyze your latency requirements and budget
2. **Infrastructure design**: Custom architecture for your use case
3. **Co-location setup**: Physical presence in exchange data centers
4. **Network optimization**: Direct connections and routing
5. **Software optimization**: Custom protocols and processing
6. **Ongoing maintenance**: Continuous monitoring and optimization

Choosing Your Latency Strategy
------------------------------

### Questions to Ask Yourself

**What's your actual latency requirement?**

* Portfolio monitoring: 1-5 seconds is fine
* Medium-frequency trading: 100-500ms works
* Professional arbitrage: 5-50ms needed
* HFT operations: Sub-millisecond required

**What's your budget reality?**

* Shared infrastructure: $29-500/month
* Enterprise solutions: $2,000-10,000/month
* Custom HFT setup: $15,000-100,000+/month

**What's your technical capability?**

* Basic integration: Use standard WebSocket/REST
* Professional setup: Enterprise FIX API
* Custom solutions: Requires dedicated engineering team

### Recommendation Framework

**For most trading strategies**: Start with shared infrastructure to validate your approach, then upgrade based on proven profitability.

**For professional operations**: Go directly to Enterprise tier to avoid shared resource limitations.

**For HFT requirements**: Contact CoinAPI's solutions team for custom architecture design.

The Truth About Trading Speed
-----------------------------

### Speed vs. Strategy Quality

**Reality check**: Most profitable trading strategies don't require microsecond latency. Success depends more on:

* Market insight and analysis
* Risk management discipline
* Capital allocation optimization
* Systematic execution consistency

**When speed matters most**:

* Market making (providing liquidity)
* Latency arbitrage (pure speed plays)
* Delta hedging large positions
* High-frequency statistical strategies

### Cost-Benefit Analysis

**Before investing in ultra-low latency**:

* Quantify the value of each millisecond saved
* Calculate infrastructure and maintenance costs
* Consider operational complexity increases
* Evaluate competitive landscape

Many successful trading operations use "fast enough" infrastructure rather than "fastest possible."

Working with CoinAPI: Setting Realistic Expectations
----------------------------------------------------

### What We Guarantee

**At each tier, CoinAPI delivers**:

* The fastest technically achievable performance
* Consistent, reliable data delivery
* Transparent pricing and capabilities
* Professional support for optimization

### What We Can't Control

**External factors affecting your latency**:

* Exchange internal processing speeds
* Geographic distance limitations
* Internet routing variations
* Your application architecture efficiency

### How We Help You Optimize

**CoinAPI's optimization support**:

* Architecture consultation for your use case
* Best practices for integration
* Performance monitoring and troubleshooting
* Custom solutions for serious operations

Getting Started: Your Latency Roadmap
-------------------------------------

### Phase 1: Understand Your Requirements

* Define your actual latency needs
* Identify budget constraints
* Assess technical capabilities
* Evaluate exchange requirements

### Phase 2: Start with Appropriate Tier

* **Learning/Testing**: Shared infrastructure
* **Professional trading**: Enterprise tier
* **HFT operations**: Custom consultation

### Phase 3: Optimize and Scale

* Monitor actual performance
* Identify bottlenecks in your stack
* Upgrade infrastructure based on profitability
* Consider custom solutions for competitive advantage

Final Word: Transparency Over Hype
----------------------------------

We don't believe in misleading latency marketing. What CoinAPI offers is **a clear path to the lowest technically achievable latency**, tailored to your infrastructure level and trading requirements.

**The honest truth**:

* Shared infrastructure can't deliver microseconds
* Professional performance requires dedicated resources
* HFT speeds demand serious engineering investment
* Your application architecture often matters more than API speed

Whether you're backtesting strategies on standard infrastructure or deploying nanosecond-optimized market-making systems, CoinAPI's architecture can support your growth, from prototype to production.

**Ready to optimize your trading infrastructure?** [Contact our team](https://coinapi.io/contact) to discuss your latency requirements and get honest recommendations for your use case.

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