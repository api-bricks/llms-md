CoinAPI.io Blog - Crypto API Exchange Coverage: 380+ Exchanges & 1000+ Assets with Chain Addresses

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

July 07, 2025

Crypto API Exchange Coverage: 380+ Exchanges & 1000+ Assets with Chain Addresses
================================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ff26372928bccb401265feed340a34098e4ad0075-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

**Picture this: You're building a multi-venue arbitrage scanner, and you need to monitor BTC/USDT across 15 different exchanges simultaneously. Your code works perfectly on Binance, but when you try to expand to Kraken, Coinbase, and a few DeFi protocols, everything breaks. Different ticker formats, inconsistent timestamp precision, varying order book depths, and suddenly your elegant trading logic becomes a mess of exchange-specific if/else statements.**

This is the data integration nightmare that kills more crypto projects than market crashes. While traders obsess over alpha strategies, the real competitive advantage often lies in having clean, normalized data from the venues that actually matter for your use case.

Why Most Cryptocurrency APIs Fail at Exchange Coverage
------------------------------------------------------

In traditional finance, you have a handful of major exchanges per asset class. In crypto, you have thousands of active exchanges, each with its own API quirks, data formats, and reliability issues. The fragmentation isn't just inconvenient, but it's strategically critical.

Consider these real scenarios:

* **Institutional traders** need tier-1 CEX data (Binance, Coinbase Pro, Kraken) for compliance and liquidity
* **DeFi researchers** require DEX aggregators (Uniswap, SushiSwap, 1inch) for on-chain analysis
* **Arbitrage bots** must monitor both CEX and DEX simultaneously for cross-venue opportunities
* **Risk managers** need comprehensive coverage to avoid blind spots in portfolio exposure

Each group needs different venues, but they all need the same thing: normalized, reliable data that doesn't break their systems.

CoinAPI Crypto API Coverage: 380+ Exchanges for Spot, DEX, and Derivatives
--------------------------------------------------------------------------

CoinAPI aggregates data from **380+ exchanges** across every major asset class and venue type. Here's how that coverage breaks down:

### Centralized Exchanges (CEX)

**Tier 1:** Binance, Coinbase Pro, Kraken, Huobi, OKX, Bitfinex

**Regional Leaders:** Upbit (Korea), Bithumb (Korea), Bitflyer (Japan), Bitstamp (Europe), Bitso (Latin America)

**Emerging Markets:** (Note: WazirX and Coinsbit not supported—excluded)

### Decentralized Exchanges (DEX)

**Ethereum:** Uniswap V2/V3, SushiSwap, Curve, Balancer

**Multi-Chain:** PancakeSwap (BSC), Trader Joe (Avalanche), SpookySwap (Fantom)

**Layer 2:** Arbitrum DEXs, Optimism DEXs, Polygon DEXs

**Cross-Chain:** (THORChain - partial support), (Osmosis, Serum - historical or experimental only)

### Derivatives Exchanges

**Perpetuals:** Binance Futures, Bybit, dYdX, BitMEX, FTX (historical only)

**Options:** Deribit, [Bit.com](http://Bit.com), OKX Options, Hegic (DeFi)

**Structured Products:** Select protocols like Ribbon, Opyn, and Premia (support may vary)

### Specialized Venues

(NFT and prediction markets like OpenSea, Augur, Polymarket, and Omen have limited or no support, excluded)

Lending Protocols (e.g., Aave, Compound, MakerDAO) may be accessible through reference APIs, not direct integration.

Real Data, Real Differences
---------------------------

To understand why comprehensive coverage matters, let's examine how the same asset behaves across different venue types:

### BTC/USDT Across Venue Types

```
1// Binance (CEX)
2{
3    "symbol_id": "BINANCE_SPOT_BTC_USDT",
4    "time_exchange": "2025-07-07T07:45:14.4140000Z",
5    "time_coinapi": "2025-07-07T07:45:14.5352950Z",
6    "ask_price": 108958.00000000,
7    "ask_size": 2.81537000,
8    "bid_price": 108957.99000000,
9    "bid_size": 4.23987000,
10    "last_trade": {
11        "time_exchange": "2025-07-07T07:45:14.3520000Z",
12        "time_coinapi": "2025-07-07T07:45:14.4749938Z",
13        "uuid": "d8022321-f137-4404-9223-2a5e20c767ce",
14        "price": 108957.99000000,
15        "size": 0.00013000,
16        "taker_side": "SELL"
17    }
18}
19
20// Uniswap V3 (DEX)
21{
22  "symbol": "USDC/ETH",
23  "exchange": "uniswap_v3",
24  "bid": 0.000364271226313672,
25  "ask": 0.000364271226313672,
26  "spread": 0,
27  "volume_24h": 18289496.573245995,
28  "last_updated": "2025-06-10T14:10:47Z"
29}
30
31// Binance Futures (Derivatives)
32{
33  "symbol": "BTCUSDT-PERP",
34  "exchange": "binance_futures",
35  "bid": 43261.8,
36  "ask": 43262.1,
37  "spread": 0.30,
38  "funding_rate": 0.0001,
39  "volume_24h": 2800000000,
40  "last_updated": "2025-07-07T10:55:00Z"
41}
42
43
```

**Add This Section: "Asset Coverage: 1000+ Supported Assets with Chain Addresses"**
-----------------------------------------------------------------------------------

**Insert this after the "Real Data, Real Differences" section and before "Reading the Exchange Coverage Map".**

### **Asset Coverage: 1000+ Supported Assets with Chain Addresses**

Exchange coverage is only half the story. The other critical question we receive is: *"Which assets does CoinAPI support, and can I get blockchain-specific information?"*

#### **Comprehensive Asset Support**

CoinAPI currently supports **1000+ active assets** with complete metadata, including:

**Major Cryptocurrencies:**

* Bitcoin (BTC), Ethereum (ETH), and all top 100 market cap assets
* Layer 1 protocols: Solana, Cardano, Polkadot, Avalanche, Polygon
* DeFi tokens: UNI, AAVE, COMP, MKR, SNX, and emerging protocols

**Chain Address Information:**

* **Contract addresses** for ERC-20, BEP-20, and other token standards
* **Network identifiers** (Ethereum mainnet, BSC, Polygon, etc.)
* **Chain-specific metadata** for cross-chain assets

#### **Why Chain Addresses Matter**

Many professional applications need more than just price data—they need to verify on-chain activity:

```
1{
2  "asset_id": "ETH",
3  "name": "Ethereum", 
4  "type_is_crypto": 1,
5  "data_start": "2015-08-07",
6  "data_end": "2025-01-15",
7  "data_quote_start": "2015-08-07T14:50:38.1774950Z",
8  "data_quote_end": "2025-01-15T23:59:44.3542800Z",
9  "data_orderbook_start": "2015-08-07T14:50:38.1774950Z", 
10  "data_orderbook_end": "2025-01-15T23:59:44.3542800Z",
11  "data_trade_start": "2015-08-07T14:50:38.1774950Z",
12  "data_trade_end": "2025-01-15T23:59:44.3542800Z",
13  "chain_addresses": [
14    {
15      "chain_id": "ethereum-mainnet",
16      "network_id": "1", 
17      "address": "0x..."
18    }
19  ]
20}
```

#### **Asset Coverage by Category**

**Active Assets (1000+):**

* All assets with active trading and current chain address information
* Regular metadata updates for new token launches
* Cross-exchange symbol mapping for consistent identification

**Historical Assets:**

* Deprecated tokens and delisted assets maintain historical data
* No chain address removal ensures research continuity
* Complete data lineage for compliance and auditing

**Important Coverage Notes:**

* The `chain_addresses` field is **only available for active assets**
* Inactive or deprecated assets retain historical data but lose real-time chain information
* New assets are added regularly as they gain significant trading volume

#### **How to Access Asset Information**

**Get all supported assets:**

bashGET /v1/assets

**Filter for active assets with chain addresses:**

bashGET /v1/assets?filter\_data\_end=

**Find specific asset information:**

bashGET /v1/assets/BTC

#### **Asset Discovery and Mapping**

**Symbol Standardization:** CoinAPI maintains consistent asset IDs across all exchanges. Whether you're looking at BTC on Binance (BTC\_USDT) or Coinbase (BTC-USD), the underlying asset ID remains "BTC" with complete chain address information.

**Cross-Chain Asset Tracking:** Many assets exist on multiple blockchains. For example:

* USDC exists on Ethereum, Polygon, Avalanche, and other chains
* Each deployment has different contract addresses
* CoinAPI tracks all valid chain addresses for complete coverage

#### **Data Quality and Maintenance**

**Regular Updates:**

* New assets added as they gain significant trading volume
* Chain addresses verified against official sources
* Deprecated assets maintain historical accuracy

**No Survivorship Bias:** Unlike some providers, CoinAPI doesn't delist historical data. You can access complete trading history for assets that are no longer active, ensuring your backtests reflect reality.

#### **Coverage Limitations**

**Chain Address Availability:**

* Only available for **active assets** in current trading
* Historical/deprecated assets retain price data but lose chain information
* New blockchains added based on ecosystem adoption

**Supported Networks:**

* Ethereum mainnet and major EVM chains (Polygon, BSC, Avalanche)
* Bitcoin and Bitcoin-based networks
* Solana and other major Layer 1s
* Limited support for newer or experimental chains

#### **Getting Started with Asset Coverage**

**Check Coverage for Your Use Case:**

```
1# See all assets with chain addresses
2GET /v1/assets?filter_chain_addresses=true
3
4# Check specific asset availability  
5GET /v1/assets/YOUR_ASSET_ID
```

**For comprehensive asset mapping, also explore:**

* `/v1/symbols` - See all trading pairs across exchanges
* `/v1/exchanges` - Verify which exchanges trade specific assets
* Documentation includes complete asset ID reference

Reading the Exchange Coverage Map
---------------------------------

### What Signals Matter?

When evaluating exchange coverage for your use case, focus on these metrics:

**Volume Concentration**

* The top 10 exchanges typically represent 80%+ of total volume
* But the long tail matters for arbitrage and risk assessment
* Regional exchanges can be liquidity leaders for local pairs

**Venue-Specific Advantages**

* **CEX**: Speed, liquidity, institutional access
* **DEX**: Permissionless, composability, new token access
* **Derivatives**: Leverage, hedging, sophisticated strategies

**Common Pitfalls**

1. Volume ≠ Liquidity
2. DEX "price" ≠ Executable price
3. Mixing venue types without context

**Data Quality Indicators**

* Timestamp precision (milliseconds vs seconds)
* Order book depth (number of price levels)
* Trade granularity (individual trades vs aggregated)
* API reliability (uptime, rate limits, error handling)

Common Coverage Challenges
--------------------------

### The Fragmentation Problem

Every exchange has its own:

* **API structure**: REST endpoints, WebSocket channels, authentication
* **Data formats**: JSON schemas, field names, timestamp formats
* **Rate limits**: Requests per second, weight systems, burst allowances
* **Reliability**: Uptime, latency, error handling

### The Maintenance Burden

* APIs change without notice
* New exchanges launch weekly
* Existing exchanges modify data structures
* Rate limits and authentication requirements evolve

How CoinAPI’s Crypto Exchange API Delivers Normalized, Reliable Data
--------------------------------------------------------------------

### Unified Schema Across 380+ Venues

CoinAPI normalizes all exchange data into consistent formats:

```
1{
2  "symbol_id": "BINANCE_SPOT_BTC_USDT",
3  "exchange_id": "BINANCE",
4  "symbol_type": "SPOT",
5  "asset_id_base": "BTC",
6  "asset_id_quote": "USDT",
7  "price": 43250.12,
8  "size": 0.045,
9  "time": "2024-01-15T14:30:00.123Z",
10  "side": "BUY"
11}
```

Same structure for every exchange, every asset class, every venue type.

Multiple Access Methods
-----------------------

**Real-Time Streams:** Live market data with sub-second latency across hundreds of exchanges simultaneously. WebSocket connections handle reconnection and buffering automatically.

**REST API:** On-demand queries for current prices and historical data with flexible filtering. Perfect for periodic checks and portfolio valuation.

**Bulk Files:** Complete historical datasets for backtesting and research. Trade-by-trade data and OHLCV summaries organized by exchange and date.

Specialized APIs for Different Use Cases
----------------------------------------

[**Market Data API**:](https://www.coinapi.io/products/market-data-api) Core OHLCV, trades, order books

* Perfect for: Price feeds, basic analysis, charting
* Coverage: All 370+ exchanges, real-time + historical

[**Indexes API**:](https://www.coinapi.io/products/indexes-api) Calculated benchmarks and composite metrics

* Perfect for: Risk management, performance tracking, derivatives pricing
* Coverage: Major asset indexes, custom weighting options

**[Exchange Rates API:](https://www.coinapi.io/products/exchange-rates-api)** Exchange information, trading pairs, asset details

* Perfect for: Dynamic exchange selection, compliance filtering
* Coverage: Real-time exchange status, supported pairs, trading rules

What You Can Do Tomorrow
------------------------

**For Developers**: Start with CoinAPI's sandbox environment to test exchange coverage for your specific use case. The REST API includes a `/exchanges` endpoint that shows real-time status and capabilities for all 370+ venues.

**For Traders**: Use the WebSocket API to build a multi-exchange price monitor. Start with your top 5 exchanges and expand coverage as you identify opportunities.

**For Researchers**: Download sample historical data from the flat files endpoint. Compare price discovery, volume patterns, and arbitrage opportunities across different venue types.

**For Risk Managers**: Implement comprehensive position tracking across CEX and DEX using the unified schema. No more manual reconciliation between exchange-specific formats.

Ready to stop fighting with exchange APIs and start building with clean, normalized data? Explore CoinAPI's exchange coverage with a free tier, or dive into the documentation to see exactly which venues matter for your use case.

The alpha isn't in the strategy; it's in the data infrastructure that makes the strategy possible.

TL;DR
-----

**CoinAPI delivers normalized crypto data from 380+ exchanges, including top CEXs (Binance, Coinbase, Kraken), DEXs (Uniswap, PancakeSwap), and derivatives platforms (Bybit, Deribit). If you're building an arbitrage scanner, backtesting with OHLCV, or modeling risk across venue types, CoinAPI provides a clean, unified crypto API you can actually build on. Available via REST, WebSocket, and bulk download, with a free crypto API tier to get started.**

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