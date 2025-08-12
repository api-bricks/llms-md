CoinAPI.io Blog - How academics use coinAPI in crypto research: 3 real use cases

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

June 09, 2025

How academics use coinAPI in crypto research: 3 real use cases
==============================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fe7acd5543913a7b3256ad5805280ebe166864f38-1001x501.png%3Frect%3D0%2C34%2C1001%2C435%26w%3D920%26h%3D400&w=1920&q=75)

**In crypto research, access to data isn’t the problem; *quality* is. Crypto research is exploding. Universities, PhD candidates, and independent analysts all want to publish groundbreaking insights on how markets work or propose new DeFi innovations.**

But there’s one critical challenge few talk about: **the data**.

It’s messy. Incomplete. Hard to use.

One academic team shared how their study on trend detection collapsed:

* One data source stopped midway.
* Another had big gaps.
* A third? Used a different format.

Eventually, the project got stuck, not because the idea wasn’t great, but because the data couldn’t support it.

For too many researchers, this is the norm.

You can’t analyze markets with confidence if your inputs are broken. You need **a unified, research-ready data source**.

Whether you're an academic, an independent quant, or a post-PhD researcher without institutional backing, you've likely faced the same issues our customers report:

*“I spent more time cleaning the data than running the analysis.”*

*“The APIs I used didn’t align across exchanges, nothing was consistent.”*

*“I couldn’t reproduce my results three weeks later.”*

At CoinAPI, we’ve listened. And we’ve built for you.

Here’s how.

Why Academics struggle with crypto market data
----------------------------------------------

The crypto space generates massive amounts of data across thousands of assets and hundreds of venues, but most sources are fragmented, noisy, or poorly documented. For academic use, this creates serious challenges:

❌ Missing ticks or corrupted order books

❌ Inconsistent symbol mappings between exchanges

❌ Aggregated data with no transparency

❌ APIs that break mid-research

CoinAPI addresses this by providing **normalized, historical, and real-time crypto data** across 370+ exchanges delivered via [flat files](https://www.coinapi.io/products/flat-files), [REST](https://docs.coinapi.io/market-data/rest-api/), or [WebSocket](https://docs.coinapi.io/market-data/websocket/) APIs. When needed, every dataset includes precise timestamps, clean schemas, and full order book depth.

Structured research: Your work deserves a foundation
----------------------------------------------------

The first bottleneck most researchers face isn’t computing or math, it’s **data chaos**.

Crypto markets are fragmented. One exchange calls it `BTC-USD`, another says `XBT-USD`. Time intervals aren’t aligned. Depth data comes in one format here, another there. Most APIs? They weren’t built for structured academic workflows.

That’s why we built CoinAPI to serve as a **research-grade data platform,** not just a dev playground.

What researchers get:

* Normalized asset identifiers and symbol mapping
* Schema consistency across 370+ venues
* Unified timestamp formats for precise time-series alignment
* Full support for CSV/FlatFile bulk downloads and structured JSON responses

*“I finally stopped duct-taping multiple APIs together. CoinAPI gave me a stable base to build structured datasets.”*

Quantitative Finance PhD candidate, Europe

Whether you're studying price discovery, liquidity fragmentation, or cross-chain correlations, **structured data unlocks structured thinking.**

Granular data: Go beyond surface-level analysis
-----------------------------------------------

Every candlestick hides thousands of micro-decisions: quotes, cancellations, fills, slippage.

If you’re only analyzing [OHLCV](https://www.coinapi.io/blog/ohlcv-data-explained-a-practical-guide-for-traders-and-quants), you’re studying **the output, not the behavior**.

CoinAPI gives you **granular access to what happens in the market.**

Researchers can access:

* Tick-by-tick trade data with full metadata
* L2 and L3 order book snapshots and deltas
* Millisecond-level quote frequency
* Trade and quote sequencing for impact analysis

*“I was finally able to model trade execution dynamics across multiple exchanges. That just wasn’t possible with public APIs.”*

Postdoctoral researcher, machine learning + market microstructure

One research team used CoinAPI data to simulate execution slippage across 5 exchanges over 6 months, modeling different liquidity tiers and detecting how certain altcoins behave under wash trading pressure.

That’s not data you can scrape from CoinGecko.

The importance of reproducibility in crypto research
----------------------------------------------------

Publishing results is one thing. Publishing **reproducible methods** is another.

Too many crypto research papers, even peer-reviewed ones, rely on opaque sources or privately collected datasets. That makes it nearly impossible to validate findings or expand on them.

We believe that **transparency in data access is the foundation of credible research.**

Here’s how CoinAPI helps:

* Clear, versioned documentation of all endpoints
* Transparent normalization logic
* Public schemas for every dataset
* Static dataset exports for long-term archival access

*“When we submitted our paper, reviewers didn’t question the data source once. The CoinAPI dataset and documentation spoke for themselves.”*

Blockchain research lab, North America

Your methodology deserves to be trusted. Clean, documented data makes that possible.

Academic use cases
==================

Let’s look at 3 ways academic researchers are using CoinAPI today.

Use Case 1: Order book analysis for liquidity modeling
------------------------------------------------------

**Use Case**: A research group at a European university is analyzing the price impact of large trades on BTC/USDT order books across multiple exchanges.

**How CoinAPI Helps**:

* Tick-by-tick trade data with millisecond timestamps
* Full L2 order book snapshots for depth reconstruction
* Consistent symbol mapping across Binance, Kraken, Coinbase, and others

**Research Output**:

A peer-reviewed paper quantifying slippage, spread decay, and liquidity fragmentation across the top 10 centralized exchanges.

Use Case 2: Backtesting arbitrage strategies with historical data
-----------------------------------------------------------------

**Use Case**: A PhD candidate is evaluating the performance of a momentum-based crypto arbitrage strategy over the past 3 years.

**How CoinAPI Helps**:

* Access to flat file datasets with historical tick data
* Clean, gap-free OHLCV and quote streams
* Reproducible tests thanks to schema stability and versioned datasets

**Research Output**:

A thesis chapter demonstrating risk-adjusted returns of inter-exchange arbitrage strategies using real market conditions and execution simulation.

Use Case 3: Monitoring stablecoin flows across chains
-----------------------------------------------------

**Use Case**: A policy-focused researcher is tracking the growth of stablecoin usage across different blockchain ecosystems to evaluate systemic risk.

**How CoinAPI Helps**:

* Normalized volume data across multiple assets and chains (e.g., USDT on Tron vs Ethereum)
* Cross-chain analytics via standardized schemas
* Real-time anomaly detection for flow surges

**Research Output**:

A policy report mapping stablecoin volume spikes to geopolitical events and exchange listings, used by a central bank research team.

Why CoinAPI is academic-ready (vs public APIs)
----------------------------------------------

Academic institutions aren't the only ones pushing crypto research forward. Independent analysts, data scientists, and early-career researchers often face similar roadblocks, and many of them choose CoinAPI to break through.

Here are three common challenges we hear from users in the research space:

### 1. **“Where can I get complete, reliable data for my research?”**

Many users come to us after struggling with fragmented or incomplete data from public APIs.

What they need is:

* Historical and real-time depth
* Consistent formats across exchanges
* Documentation that makes data *usable*

CoinAPI delivers this with normalized schemas, extensive historical archives, and access to real-time and [tick-level data](https://www.coinapi.io/blog/tick-data-vs-order-book-snapshots-which-one-will-give-you-the-trading-edge) from over 370 venues.

### 2. **“How do I make my research reproducible and shareable?”**

For academic publishing or even posting a public methodology on GitHub, reproducibility is everything.

CoinAPI’s versioned datasets, consistent endpoints, and timestamped records allow researchers to:

* Build transparent workflows
* Share code that doesn’t break
* Validate results across teams or over time

### 3. **“Can I apply ML, anomaly detection, or network models on this data?”**

Advanced analytics require more than just price and volume. Researchers ask for:

* Depth of the book
* Trade sequencing
* Cross-asset relationships

Our customers are building models for alpha detection, volatility clustering, stablecoin flow, and more — all powered by clean, structured data that supports complex pipelines.

### What Makes a Crypto Research Source Trustworthy?”

When it comes to crypto research, one of the most common questions we hear from users is: *“What data can I trust?”*

Here’s what most serious researchers look for:

* **Consistent data across time and venues**
* **Precise timestamps** for sequencing and latency modeling
* **Clear documentation** and versioning for reproducibility
* **Transparency in how the data is generated or normalized**

CoinAPI users tell us that these are non-negotiable when conducting credible research, whether for peer-reviewed publication or internal analysis.

Experienced researchers know that *whitepapers can promise anything,* but market behavior tells the truth.

Our users often ask:

* “Is this project being traded organically across exchanges?”
* “Are volumes real or inflated?”
* “Does the token have sustained liquidity, or just a pump-and-dump profile?”

Using CoinAPI’s normalized market data, researchers can:

* Compare real-time price and volume movements across multiple exchanges
* Evaluate trade frequency and book depth
* Detect unusual quote activity or coordinated volume spikes

These insights go far beyond social sentiment. They help filter hype from substance, a crucial step for anyone analyzing crypto projects.

Our research community consistently looks for tools that offer:

* Deep, structured market data (beyond just price)
* Easy export options for backtesting and modeling
* Strong documentation and consistent API behavior
* Transparent methodology and clean schemas

One of the most common pain points we hear?

“Other tools are fine for charts, but we need research-grade data we can trust.”

CoinAPI addresses these needs by providing programmatic access to:

* Tick-by-tick trade data
* Full L2 and L3 order book snapshots
* Timestamped OHLCV and quote feeds
* A normalized schema across 370+ venues

Get started: Access academic datasets from CoinAPI
--------------------------------------------------

CoinAPI isn’t just built for traders, it’s designed for **anyone who needs high-integrity, granular crypto data**. Academic institutions choose CoinAPI because it offers:

✅ Transparent, well-documented schema

✅ Historical datasets for long-term analysis

✅ Tick-level granularity across trades, quotes, and order books

✅ One API for 370+ exchanges (no patchwork integrations)

✅ Support for CSV, REST, and WebSocket access

Whether you’re publishing papers, running simulations, or building academic dashboards, CoinAPI helps researchers focus on insights, not data cleanup.

Final thought: We see you, researchers
--------------------------------------

You’re trying to build something rigorous in a fast-moving, noisy, often hype-driven ecosystem.

And too often, the infrastructure makes it harder, not easier.

We built CoinAPI because we *felt that pain too*.

We saw the gap between academic needs and crypto tooling.

So, whether you're publishing to a journal, testing a model, or building an open research repo, these are the pillars that support you:

✅ **Structured research** because consistency matters

✅ **Granular data** because the signal lives in the details

✅ **Transparent methodology** because truth demands clarity

You bring the insight.

We’ll bring the infrastructure.

Want to Try It?
---------------

Because in research, your results are only as good as your data. And that data? It should be your **strongest foundation,** not your biggest risk.

Want to explore our flat files or access datasets for academic use?

👉 [Get started with CoinAPI](https://www.coinapi.io/contact) or request sample data today.

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