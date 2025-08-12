CoinAPI.io Blog - How crypto quant teams use CoinAPI Index API to build macro trading signals

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

June 04, 2025

How crypto quant teams use CoinAPI Index API to build macro trading signals
===========================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F30dc7c0d65965331b637e7258c7f5e7867e6cfc8-1000x503.png%3Frect%3D0%2C35%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

**Why are indexes not just benchmarks anymore? They're the starting point for building macro strategy in crypto.**

If you're analyzing sector flows, forecasting volatility, or standardizing portfolio exposure, raw token prices alone won’t cut it. You need structure, and in crypto, that structure comes from indexes. In traditional finance, indexes like the S&P 500 and VIX provide standardized references for macro analysis, allowing researchers and traders to evaluate sectors, volatility, and market sentiment over time. In crypto, the equivalent has often been missing or fragmented.

CoinAPI’s [Indexes API](https://www.coinapi.io/products/indexes-api) gives you a complete, normalized view across DeFi, stablecoins, Layer 1s, and more. It offers real-time updates and historical depth designed for research and signal generation.

You’ll get:

* Consistent benchmarks across 370+ exchanges
* Real-time feeds + multi-year backtest coverage
* Clean, reproducible index data for quant models and valuation logic

This article shows how crypto professionals use CoinAPI Indexes to detect market regimes, measure capital rotation, and build macro intelligence with actual data and use cases.

What are Indexes?
-----------------

**Indexes** are structured datasets that aggregate the performance of multiple assets into a single, standardized value. In both traditional finance and crypto, they serve as essential tools for:

* **Benchmarking performance** (e.g., comparing a portfolio to the market)
* **Tracking sector trends** (e.g,. DeFi vs Layer 1 performance)
* **Deriving macro insights** (e.g,. capital rotation, volatility clustering)

How crypto indices work
=======================

Instead of analyzing 50 individual token prices separately, an **index** combines those prices, often using weighting by volume or market cap to show how the entire group is performing. For example:

* A **DeFi Index** might track tokens like UNI, AAVE, and MKR.
* A **Stablecoin Index** might aggregate USDT, USDC, and DAI.
* A **Volatility Index** like CAPIVIX tracks expected volatility for BTC or ETH.

Why Indexes matter in crypto
============================

* Raw crypto price data is noisy and fragmented.
* Indexes offer a **normalized, noise-reduced lens** to detect meaningful trends.
* They help answer questions like:
  + “Is DeFi gaining strength relative to Layer 1s?”
  + “Is capital rotating into stablecoins, a sign of risk aversion?”
  + “Is volatility about to spike?”

Purpose and scope
-----------------

CoinAPI Indexes serve multiple purposes:

* To provide a standardized measure of cryptocurrency market performance
* To offer benchmarks for portfolio management and financial product creation
* To enhance market transparency and facilitate price discovery

Our index offerings currently include:

* **VWAP (Volume-Weighted Average Price) Index**
* **PRIMKT (Principal Market Price) Index**
* **CAPIVIX (CoinAPI Volatility Index)**

These indices are constructed using robust methodologies and high-quality data inputs to ensure they accurately represent the underlying markets they measure.

Historical research: Solving the “Data Drift” problem in crypto backtests
=========================================================================

When quants backtest strategies, *drift* is the silent killer:

* Reconstructed baskets don’t match how assets traded historically
* Symbols and tickers change mid-backtest
* Timestamps don’t align across sources

This leads to inaccurate signals and unreliable outcomes.

**CoinAPI Indexes solves these problems by design.** Every index includes:

✅ A stable, versioned asset basket

✅ Precision-aligned timestamps from CoinAPI’s core feed

✅ Normalization across venues and trading pairs

You’re no longer modeling against a retrofitted version of history, you’re working with the structure that actually existed.

### What you can do with historical indexes

CoinAPI’s Indexes API is not just a real-time feed, it’s a deep historical archive built for macro research:

* Rewind sector dynamics with **years of historical index data**
* Backtest **volatility and dispersion models** across DeFi, L1s, and stablecoins
* Compare index movements against macro triggers (Fed rates, FX, VIX)
* Build ML pipelines with **clean, timestamp-aligned features**

### How analysts use it in practice

When a volatility spike hits DeFi indexes while stablecoin indexes rise, macro desks interpret that as a **risk-off signal**. By tracking dispersion between indexes, they detect **correlation breakdowns,** early warnings of sentiment shifts.

This enables:

* Sector rotation strategies
* Smarter volatility hedges
* More responsive risk toggles

With CoinAPI Indexes, these signals aren’t theoretical. They’re **repeatable, auditable, and ready for production**.

🧾 Sample Data Breakdown: ETH/USD VWAP Index
-------------------------------------------

Here’s a real example of CoinAPI Index data for the 24-hour VWAP (Volume-Weighted Average Price) of ETH/USD from Binance:

```
1[
2    {
3        "time_period_start": "2024-05-01T00:00:00Z",
4        "time_period_end": "2024-05-02T00:00:00Z",
5        "time_open": "2024-05-01T00:00:00Z",
6        "time_close": "2024-05-01T23:59:00Z",
7        "value_open": 3011.47381333189,
8        "value_high": 3019.26244175799,
9        "value_low": 2817.90404019365,
10        "value_close": 2968.14400677062,
11        "value_count": 0
12    }
13]
```

### What does this data tell you?

* **`value_open`, `value_close`, `value_high`, and `value_low`** represent the volume-weighted price range of ETH across the day.
* **`volume_traded`** reflects liquidity behind the index; higher values indicate more reliable benchmarks.
* **`index_id`** identifies the index type, in this case, a VWAP calculation for ETH/USD on Binance.

### Who this helps

![Who This Helps ](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb6df4b0059e697615cd755449dcc29a3787bc8cc-1190x578.png&w=1920&q=75)

This single, timestamped JSON block becomes a reliable benchmark, training feature, or audit artifact, depending on the team using it.\*\* This index is often used as a trading benchmark or to compare actual trade execution quality against the market's average pricing. It also feeds into macro modeling by reflecting volume-weighted trends rather than raw price action.

Here’s what you get out of the box:

Feature Description **Sector & thematic indexes** Covering Layer 1s, DeFi, stablecoins, and more **Historical depth** Access index data across multiple years — no backfill hacks **Clean formatting** Unified schema across all exchanges — no remapping **Real-time updates** WebSocket + REST access, full timestamp fidelity **Normalized methodology** Transparent index construction, ideal for reproducibility

Each index aggregates multiple assets by theme, tracks weighted average price, and exposes both **price** and **volume signals** — the basis for macro insight.

Use case scenarios by role:
---------------------------

Building macro insight from historical index data
=================================================

Let’s say your research question is:

“*How do capital rotations between DeFi and Layer 1 assets correlate with volatility clusters in the broader market?”*

Here’s how you’d approach it using the Indexes API:

#### **Query historical DeFi Index and L1 Index returns**

* Use `/v1/indexes` endpoint with specific `index_id`
* Pull hourly or daily prices, depending on signal granularity

#### **Compute cross-index momentum differentials**

* e.g., 7-day rate of change (ROC) between DeFi and L1 indexes

#### **Overlay BTC or ETH volatility metrics**

* Use CoinAPI OHLCV endpoint for volatility proxies (e.g. ATR or stdev)

#### **Build a time series classification model**

* Regime: "Rotation into DeFi → risk-on"
* Regime: "Rotation out of L1s → de-risking phase"

#### **Backtest macro overlay signals**

* Use CoinAPI Indexes as filters for altcoin position sizing
* Or use them to flag regime shifts and reduce leverage in trend systems

This kind of analysis **isn’t feasible** with raw price data or exchange-specific tickers, it would take weeks of cleanup. With CoinAPI, it’s a single pipeline.

### For **Tax, Audit & Compliance teams**

*“We need reliable historical pricing for audits, tax reporting, and capital gains tracking.”*

CoinAPI Indexes offer:

* Time-aligned pricing from the principal market (PRIMKT) to comply with IFRS 13 and FASB ASC 820
* Daily VWAP data is usable as a fair market valuation benchmark for crypto asset accounting
* Backtestable index history for accurate cost basis reconstruction

**Use Case:** Use PRIMKT and VWAP indexes to provide tax authorities and auditors with standardized pricing for capital gains calculations and audit trails.

### For **DeFi protocol builders & oracles**

*“We want to reflect sector-wide movement in our smart contract logic.”*

With CoinAPI:

* Feed real-time DeFi Index data into smart contracts or governance dashboards
* Use indexes as oracle input for lending collateral ratios or treasury rebalancing
* Monitor index-level volatility or dispersion to trigger on-chain parameters

**Use Case:** Integrate the DeFi Index as a live oracle in protocol contracts to dynamically adjust liquidity incentives based on sector activity.

### For q**uant funds & macro researchers**

*“We need reproducible, clean macro inputs for signal engines.”*

CoinAPI Indexes help quant teams:

* Run cross-index regime modeling (e.g., Stablecoins vs DeFi momentum spread)
* Backtest volatility-switching strategies
* Create sector rotation models with dispersion and beta trees

**Use Case:** Use the DeFi Index vs L1 Index to predict regime transitions when dispersion spikes above 1.5σ.

**Why it works:** Dispersion leads to correlation. CoinAPI makes this measurable.

### For p**ortfolio valuation & risk teams**

*“We need defensible benchmarks to calculate NAV across fragmented exchanges.”*

With CoinAPI:

* Use FX Rates + Stablecoin Index to normalize NAV in USD
* Standardize portfolio valuation across DeFi, L1s, and stablecoins
* Generate internal benchmark curves for daily reconciliation

**Use Case:** Build a "crypto beta basket" using weighted indexes to compare portfolio drawdowns.

### For a**cademic researchers & ML/Data scientists**

*“We need clean, timestamp-aligned data to train models and publish research.”*

CoinAPI offers:

* Clean JSON/CSV output with consistent field naming
* Full index metadata and construction transparency
* REST + WebSocket feeds for reproducible time-series workflows

**Use Case:** Train a classifier to detect "altseason" using normalized index momentum ratios.

### For **DeFi analysts & protocol teams**

*“We want to understand how the market perceives our sector in real time.”*

With CoinAPI Indexes:

* Track your category (DeFi, L2s, Meme) in normalized price + volume terms
* Integrate into on-chain dashboards to show sector rotation flows
* Visualize correlation breakdowns to BTC or ETH as macro warning signs

**Use Case:** Use real-time WebSocket index feeds to show investor sentiment toward DeFi protocols during major governance events.

Research-Grade Construction = Better Signal Quality
===================================================

CoinAPI doesn’t just average prices.

Each index follows a documented construction method, which includes:

* Weighting by market cap or liquidity
* Unified pricing across venues
* Timestamp-aligned entries across assets

This eliminates common problems like:

* Token rebrand issues (e.g., ANT vs. ARAGON)
* Dead tickers in historical lookbacks
* “Phantom” data from illiquid markets

Result: You can reproduce research results and share signal logic with confidence — something academic and professional teams both require.

### What can you build next with CoinAPI indexes

Here are advanced research paths to explore:

Macro Objective Index-Based Method **Risk regime modeling** Track stablecoin index flows as a proxy for sidelining capital **Sector sentiment** Compute rolling Sharpe ratios across DeFi / Layer 2 / Layer 1 indexes **Volatility hedging** Trigger hedge-only rules when dispersion across sector indexes spikes **Market structure analysis** Use index-level correlations to detect clustering or fragmentation

You can combine this with CoinAPI’s [OHLCV](https://www.coinapi.io/) or [Tick data](https://www.coinapi.io/) products for full-stack backtesting, from idea to execution.

Here’s what serious quant teams are doing:

### 1. **Cross-Index dispersion as a volatility signal**

Just like equity long/short desks measure sector dispersion to predict volatility clusters, crypto quants are doing the same with CoinAPI Indexes.

Signal: When weekly return dispersion across thematic indexes widens beyond 1.5σ, expect short-term regime change (often followed by volatility contraction or expansion).

**Why it works**: Dispersion leads to correlation. When L1s are up 12% and DeFi is down 8%, someone is wrong. That misalignment often precedes reversion or structural break.

### 2. **Liquidity rotation detection via index volume normalization**

By normalizing index volumes (not just price) over rolling windows, teams are detecting capital rotation, especially **into or out of stablecoins**.

Signal: A 3-day rolling volume increase in the Stablecoin Index, while other risk indexes show outflow,s suggests rotation into “cash” — a macro bearish signal.

**Why it works**: Stablecoin flow data is a proxy for positioning and sentiment. Index-level normalization eliminates single-token noise.

This approach is especially useful when combined with CoinAPI’s stablecoin-specific volume data across chains.

### 3. **Macro beta forecasting using index correlation trees**

Rather than running correlation matrices across thousands of tokens, funds are aggregating them by index and building **correlation trees**.

Insight: When the DeFi index’s beta to BTC spikes while its correlation to Layer 2s drops, you’re likely entering a correlation breakdown phase — time to hedge sector-specific exposure.

CoinAPI’s normalized sector indexes let you run this analysis historically — no data cleaning nightmares, no custom symbol reconciliation.

### 4. **Beta-neutral relative value strategies across index pairs**

Indexes act as tradeable references, not just benchmarks. Quant desks are now running long/short sector rotations:

Strategy: Long Layer 1 Index / Short DeFi Index when momentum divergence exceeds 2σ and 14-day correlation is declining.

This would be operational hell if you tried it on token-by-token data. With CoinAPI, the index APIs offer unified history, consistent scale, and timestamp alignment.

### CoinAPI Indexes API vs. Competitors

![CoinAPI Indexes API vs. Competitors](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F427b0ea08c4440559e96429c48b39a572360529b-1706x1368.png&w=1920&q=75)

### Pricing & Enterprise Support

CoinAPI offers **transparent, usage-based pricing** with clear tiers that scale from research to production environments, unlike providers like Kaiko or Lukka, which often require custom quotes or costly commitments.

**Included with every plan:**

* Dedicated onboarding support for enterprise clients
* Support SLAs for production teams
* Full documentation and integration guidance

💬 *“We switched to CoinAPI because the data quality was matched by their responsiveness and flexibility. We got to production in days, not weeks.”* - Infrastructure Lead, institutional client

### TL;DR: Why CoinAPI wins for Index-based research

CoinAPI is the **only** provider in this group that delivers:

* **Unified real-time + historical index access**
* **Cross-exchange normalization with accurate symbol mapping**
* **Composability across market data, FX, and tick layers**
* **Transparent construction logic and metadata**
* **Research-grade formats that integrate directly into quant pipelines**

With seamless integration across CoinAPI’s FX, OHLCV, and tick data products, it becomes the **core data layer** for:

* Macro signal generation
* Backtestable sector and theme analysis
* Portfolio standardization across venues and chains
* Reproducible research without symbol drift or timestamp errors

Whether you’re tracking stablecoin flows, monitoring DeFi outperformance, or building volatility regime models, **CoinAPI Indexes are your clean, normalized, always-on macro lens** into the crypto economy.

### Ready to build?

🔍 Ready to turn raw price data into macro edge?

→ [Explore Indexes API](https://www.coinapi.io/products/indexes-api) or

→ [Talk to an expert](https://www.coinapi.io/contact-us)

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